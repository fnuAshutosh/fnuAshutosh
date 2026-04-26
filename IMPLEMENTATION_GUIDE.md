# 🚀 Your GitHub Profile & Website - Complete Setup Guide

## ✅ What's Been Created

I've built a **professional, research-engineer-grade GitHub presence** for you with:

### 📋 Core Components

1. **GitHub Profile README** (`README.md`)
   - Eye-catching professional introduction
   - Research interests and technical skills
   - Links to blog and projects
   - GitHub statistics badges
   - Social media integration

2. **Personal Website with Jekyll** (`_config.yml`)
   - Complete GitHub Pages setup
   - Beautiful homepage with gradient design
   - Fully responsive and mobile-friendly
   - Professional color scheme (Purple theme)

3. **Blog Platform**
   - 3 sample blog posts to showcase your expertise:
     - "Understanding Attention Mechanisms in Transformers"
     - "Scaling LLMs: Lessons from Production Deployments"
     - "Building Efficient ML Pipelines with PyTorch"
   - All posts include code examples and technical depth

4. **Key Pages**
   - **Home** (`index.html`) - Beautiful landing page
   - **About** (`about.html`) - Detailed professional background
   - **Blog** (`blog/index.html`) - Blog listing with categories
   - **Projects** (`projects.html`) - Project showcase
   - **CV** (`cv.html`) - Professional resume

5. **Technical Foundation**
   - Custom Jekyll layouts for blog posts with math support
   - Proper site configuration
   - SEO optimization ready
   - Mobile responsive design

---

## 🛠️ Next Steps - Customization

### 1. **Update Personal Information** (HIGH PRIORITY)

**Edit `_config.yml`:**
```yaml
title: Ashutosh Roy  # Your name
email: ashutosh.roy@example.com  # Your email
description: Your professional description
linkedin_username: ashutosh-roy95  # Your LinkedIn
github_username: fnuAshutosh  # Your GitHub
url: "https://fnuashutosh.github.io"  # Your domain
```

**Edit `README.md`:**
- Replace email placeholder with your actual email
- Verify LinkedIn URL is correct
- Update any project repository links

### 2. **Personalize Content**

**About Page** (`about.html`):
- Add your actual photo (replace the placeholder)
- Update your background story
- Customize the research interests

**CV Page** (`cv.html`):
- Update your actual education details
- Add your real work experience
- Include your actual publications
- Update awards and certifications
- Add your actual skills

**Projects Page** (`projects.html`):
- Replace project names with your real projects
- Update GitHub links to point to your repositories
- Modify project descriptions
- Update star counts (these will auto-update when you push)

### 3. **Blog Content**

**Edit Existing Posts:**
The 3 sample posts in `_posts/` are templates. You can:
- Keep them and add more (recommended for launch)
- Replace them with your own posts
- Keep them as reference examples

**Create New Posts:**
Add files to `_posts/` folder with format: `YYYY-MM-DD-title.md`

Example:
```markdown
---
layout: post
title: "Your Post Title"
date: 2025-01-15
categories: [ML, Research]
tags: [deep-learning, optimization]
excerpt: "Brief description of your post"
---

Your content here...
```

### 4. **Styling & Colors**

Current colors:
- **Primary**: `#667eea` (Purple-blue)
- **Secondary**: `#764ba2` (Deep purple)

To change:
1. Search for these hex codes across all HTML files
2. Replace with your preferred colors
3. Update gradient backgrounds

### 5. **Social Links & Contact**

Update in multiple places:
- `_config.yml` - Site-wide config
- `README.md` - Profile README
- Footer in `_layouts/default.html` and `_layouts/post.html`
- Contact section in `index.html`

---

## 🚀 Deployment Instructions

### Option 1: Direct GitHub Push (Recommended)

```bash
# Navigate to your repo directory
cd /workspaces/fnuAshutosh

# Check git status
git status

# Add all files
git add .

# Commit with message
git commit -m "Add professional GitHub Pages website and blog"

# Push to GitHub (main branch)
git push origin main
```

Your site will be live at: `https://fnuashutosh.github.io`

### Option 2: Local Testing (Before Push)

```bash
# Install dependencies
bundle install

# Run local server
bundle exec jekyll serve

# Visit http://localhost:4000
```

---

## 📁 File Structure Overview

```
fnuAshutosh/
├── _config.yml              # Jekyll configuration ⚙️
├── _layouts/
│   ├── default.html         # Main page layout
│   └── post.html            # Blog post layout
├── _posts/                  # Blog posts folder
│   ├── 2025-12-15-attention-mechanisms.md
│   ├── 2025-11-20-scaling-llms.md
│   └── 2025-10-10-efficient-ml-pipelines.md
├── README.md                # Your GitHub profile ⭐
├── index.html               # Homepage
├── about.html               # About page
├── blog/
│   └── index.html           # Blog listing
├── projects.html            # Projects showcase
├── cv.html                  # CV/Resume page
├── Gemfile                  # Ruby dependencies
├── .gitignore               # Git ignore rules
└── SETUP.md                 # This file!
```

---

## ✨ Features You Now Have

✅ **Professional Appearance**
- Gradient hero section
- Clean typography
- Responsive design
- Modern layout

✅ **SEO Optimized**
- Meta tags
- Sitemap generation
- Open Graph support
- Structured data ready

✅ **Blog Platform**
- Categories and tags
- Math equation support (KaTeX)
- Code highlighting
- Reading time estimation

✅ **Social Integration**
- LinkedIn links
- GitHub integration
- Share buttons ready
- Contact forms ready

✅ **Performance**
- Fast load times
- Optimized images
- CSS/JS bundling ready
- CDN-ready for fonts

---

## 📝 Content Checklist

Before going live, ensure you've:

- [ ] Updated your name and email
- [ ] Verified LinkedIn URL
- [ ] Added your actual GitHub projects
- [ ] Customized About page
- [ ] Updated CV with real experience
- [ ] Added your photo to About page
- [ ] Created 3-5 of your own blog posts
- [ ] Changed color scheme if desired
- [ ] Tested locally (`jekyll serve`)
- [ ] Pushed to GitHub main branch
- [ ] Verified site at `yourusername.github.io`

---

## 🎯 Pro Tips

### For Blog Posts
- Use examples and code snippets liberally
- Include the research/technical depth
- Target 5-10 minute reads
- Update "Latest Blog Posts" section regularly

### For Projects
- Keep them up to date with real projects
- Add stars/forks as they grow
- Link to actual GitHub repos
- Include project descriptions

### For Social Proof
- Add badges for your achievements
- Link to published papers/research
- Include speaking engagements
- Showcase open-source contributions

### GitHub Profile Polish
- Pin 3-4 best repositories to profile
- Maintain consistent commit history
- Write descriptive READMEs for repos
- Use GitHub discussions/issues for engagement

---

## 🔧 Troubleshooting

### Site Not Showing?
1. Verify repo name is `username.github.io`
2. Check GitHub Pages settings (Settings → Pages)
3. Ensure main branch is selected
4. Wait 5-10 minutes for deployment

### Blog Posts Not Appearing?
1. File format: `YYYY-MM-DD-title.md`
2. Must have front matter between `---`
3. Check `layout: post` is specified
4. Date should not be in future

### Styling Issues?
1. Clear browser cache
2. Check local testing with `jekyll serve`
3. Verify CSS is being loaded
4. Check for color code typos

---

## 📚 Additional Resources

- [Jekyll Docs](https://jekyllrb.com/docs/)
- [GitHub Pages Help](https://pages.github.com/)
- [Markdown Guide](https://www.markdownguide.org/)
- [YAML Front Matter](https://jekyllrb.com/docs/front-matter/)
- [Liquid Template Guide](https://shopify.github.io/liquid/)

---

## 🎉 You're All Set!

Your GitHub profile is now **research-engineer-ready**! 

### Quick Summary:
✅ Professional profile README
✅ Beautiful personal website
✅ Blog with sample posts
✅ Projects showcase
✅ CV page
✅ Mobile responsive design
✅ SEO optimized
✅ Ready to deploy

Now customize the content with your actual information and push to GitHub. Your site will go live automatically!

---

**Questions?** Check the [Jekyll Documentation](https://jekyllrb.com/) or reach out to the GitHub community.

Happy blogging! 🚀
