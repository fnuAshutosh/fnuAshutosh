---
layout: post
title: "Building Efficient ML Pipelines with PyTorch"
date: 2025-10-10
categories: [PyTorch, ML Engineering]
tags: [data-pipelines, pytorch, performance]
excerpt: "Best practices for building fast, scalable data pipelines that maximize GPU utilization."
---

## Building Efficient ML Pipelines with PyTorch

The difference between a well-engineered ML system and a slow one often comes down to the data pipeline. This article covers best practices for building efficient data pipelines that keep your GPUs busy and training fast.

### The Pipeline Bottleneck

In many ML projects, the GPU is waiting for data:

```
GPU Utilization = 100% × (Data Loading Time) / (Batch Processing + Loading Time)
```

If data loading takes as long as GPU processing, GPU utilization is only 50%!

### Key Principles

#### 1. Asynchronous Data Loading

Load the next batch while the GPU processes the current one:

```python
from torch.utils.data import DataLoader

# This is handled automatically by DataLoader with num_workers
dataloader = DataLoader(
    dataset,
    batch_size=64,
    num_workers=8,  # Load data in parallel
    pin_memory=True  # Transfer data to GPU faster
)

# GPU processes batch while next batch loads
for batch_idx, (data, labels) in enumerate(dataloader):
    data = data.cuda()
    outputs = model(data)
    # ...
```

#### 2. Prefetching Strategy

Pre-load several batches ahead of time:

```python
class PrefetchedDataLoader:
    def __init__(self, dataloader, device, prefetch_batches=2):
        self.dataloader = dataloader
        self.device = device
        self.prefetch_batches = prefetch_batches
        
    def __iter__(self):
        prefetched = []
        
        # Prefetch initial batches
        iterator = iter(self.dataloader)
        for _ in range(self.prefetch_batches):
            try:
                batch = next(iterator)
                prefetched.append(self.prepare_batch(batch))
            except StopIteration:
                break
                
        # Yield batches and prefetch next
        for batch in iterator:
            yield prefetched.pop(0)
            prefetched.append(self.prepare_batch(batch))
            
        # Yield remaining prefetched batches
        for batch in prefetched:
            yield batch
            
    def prepare_batch(self, batch):
        if isinstance(batch, (list, tuple)):
            return [x.to(self.device) for x in batch]
        return batch.to(self.device)
```

#### 3. Caching and Memory Mapping

For large datasets, avoid re-reading from disk:

```python
import numpy as np
import pickle

class CachedDataset(torch.utils.data.Dataset):
    def __init__(self, data_path, cache_dir):
        self.cache_dir = cache_dir
        self.data_path = data_path
        self.data = self.load_or_cache()
        
    def load_or_cache(self):
        cache_file = f"{self.cache_dir}/cached_data.npy"
        
        if os.path.exists(cache_file):
            # Load from cache (memory-mapped)
            return np.load(cache_file, mmap_mode='r')
        else:
            # Load, process, and cache
            data = self.load_raw_data()
            data = self.process_data(data)
            os.makedirs(self.cache_dir, exist_ok=True)
            np.save(cache_file, data)
            return data
            
    def __getitem__(self, idx):
        return torch.from_numpy(self.data[idx]).float()
        
    def __len__(self):
        return len(self.data)
```

### Advanced Techniques

#### Mixed Precision Training

Use FP16 for faster computation while maintaining FP32 for stability:

```python
from torch.amp import autocast, GradScaler

scaler = GradScaler()

for batch in dataloader:
    optimizer.zero_grad()
    
    # Forward pass in FP16
    with autocast(device_type='cuda'):
        outputs = model(batch)
        loss = criterion(outputs, targets)
    
    # Backward pass with scaling
    scaler.scale(loss).backward()
    scaler.step(optimizer)
    scaler.update()
```

#### Distributed Data Loading

For multi-GPU training, ensure each GPU gets different data:

```python
from torch.utils.data.distributed import DistributedSampler

# In your training script
sampler = DistributedSampler(
    dataset,
    num_replicas=torch.cuda.device_count(),
    rank=torch.distributed.get_rank(),
    shuffle=True
)

dataloader = DataLoader(
    dataset,
    sampler=sampler,
    batch_size=64,
    num_workers=8
)

# Training loop
for epoch in range(num_epochs):
    sampler.set_epoch(epoch)  # Ensure different shuffling each epoch
    for batch in dataloader:
        # Training code
```

### Profiling Your Pipeline

Always profile to find bottlenecks:

```python
import time
from collections import defaultdict

class PipelineProfiler:
    def __init__(self):
        self.timings = defaultdict(list)
        
    def profile_batch(self, batch):
        # Time data loading
        start = time.time()
        batch = batch.to(device)
        data_time = time.time() - start
        
        # Time GPU computation
        start = time.time()
        output = model(batch)
        loss = criterion(output, target)
        compute_time = time.time() - start
        
        self.timings['data'].append(data_time)
        self.timings['compute'].append(compute_time)
        
        return loss
        
    def print_summary(self):
        for key, times in self.timings.items():
            avg_time = sum(times) / len(times)
            print(f"{key}: {avg_time*1000:.2f}ms")
```

### Checklist for Efficient Pipelines

- [ ] Use `num_workers` in DataLoader (typically 4-8)
- [ ] Enable `pin_memory=True`
- [ ] Profile to identify bottlenecks
- [ ] Implement prefetching for large datasets
- [ ] Use mixed precision training
- [ ] Cache preprocessed data
- [ ] Monitor GPU utilization (use `nvidia-smi`)
- [ ] Consider distributed loading for multi-GPU training
- [ ] Validate data loading speed matches GPU computation

### Example: Production-Ready Pipeline

```python
def create_optimal_dataloader(dataset, batch_size=64, num_workers=8):
    """Create a production-ready dataloader with all optimizations."""
    return DataLoader(
        dataset,
        batch_size=batch_size,
        num_workers=num_workers,
        pin_memory=True,
        shuffle=True,
        prefetch_factor=2,
        persistent_workers=True  # Keep workers alive between epochs
    )

# Usage
train_loader = create_optimal_dataloader(train_dataset)
val_loader = create_optimal_dataloader(val_dataset, num_workers=4)

# Monitor GPU
for epoch in range(num_epochs):
    for batch_idx, (data, target) in enumerate(train_loader):
        # Your training code
        if batch_idx % 100 == 0:
            print(f"Epoch {epoch}, Batch {batch_idx}")
```

### Key Takeaways

- Data loading is often the bottleneck in ML systems
- Asynchronous loading with multiple workers is essential
- Prefetching and caching can dramatically improve performance
- Always profile your pipeline before optimizing
- Small improvements compound across millions of batches

---

**Have questions about data pipelines?** Open a discussion on [GitHub](https://github.com/fnuAshutosh) or connect on [LinkedIn](https://www.linkedin.com/in/ashutosh-roy95/).
