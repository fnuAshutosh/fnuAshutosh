# ⚡ Quick Reference - GitHub Profile Setup

## 🎯 Top 5 Things to Do First

1. **Update `_config.yml`** with your info:
   ```yaml
   title: YOUR NAME
   email: your.email@example.com
   linkedin_username: your-linkedin
   ```

2. **Update `README.md`** - Change email and verify links

3. **Edit `about.html`** - Add your photo and story

4. **Update `cv.html`** - Replace sample experience with yours

5. **Push to GitHub**:
   ```bash
   git add .
   git commit -m "Add professional website"
   git push origin main
   ```

---

## 📋 Files You Have

| File | Purpose | Priority |
|------|---------|----------|
| `README.md` | GitHub profile | 🔴 HIGH |
| `_config.yml` | Site config | 🔴 HIGH |
| `about.html` | About page | 🟡 MED |
| `cv.html` | Resume page | 🟡 MED |
| `index.html` | Homepage | 🟢 LOW |
| `projects.html` | Projects showcase | 🟡 MED |
| `blog/` | Blog listing | 🟢 LOW |
| `_posts/` | Blog posts | 🟢 LOW |
| `_layouts/` | Page templates | 🟢 LOW |

---

## 🎨 Customization Quick Links

| Element | Location | Change To |
|---------|----------|-----------|
| Site Title | `_config.yml` | Your name |
| Email | `_config.yml` | Your email |
| Colors | All HTML files | Your brand colors |
| LinkedIn | `_config.yml`, `README.md` | Your profile |
| CV Content | `cv.html` | Your experience |
| About Text | `about.html` | Your story |
| Projects | `projects.html` | Your work |
| Blog Posts | `_posts/` | Your articles |

---

## 🚀 Deploy Checklist

```bash
# Step 1: Update files (all personalization done)
cd /workspaces/fnuAshutosh

# Step 2: Check status
git status

# Step 3: Add changes
git add .

# Step 4: Commit
git commit -m "Personal GitHub website and blog"

# Step 5: Push (make it live!)
git push origin main
```

✅ Your site is now live at: `https://fnuashutosh.github.io`

---

## 📝 Blog Post Template

```markdown
---
layout: post
title: "Your Title Here"
date: 2025-01-15
categories: [Category1, Category2]
tags: [tag1, tag2]
excerpt: "One-line summary of the post"
---

# Your Heading

Your content here...

## Code Example

\`\`\`python
print("Hello World")
\`\`\`

## Math Support

Use $x = y$ for inline math or $$ \frac{1}{2} $$ for display math.
```

---

## 🎯 Success Metrics

Your GitHub presence should show:
- ✅ Professional profile README
- ✅ Live personal website
- ✅ 3+ blog posts
- ✅ Project showcase
- ✅ Professional CV
- ✅ Mobile responsive
- ✅ Good SEO

---

## 📞 Need Help?

See detailed guide in: `IMPLEMENTATION_GUIDE.md`

For Jekyll help: https://jekyllrb.com/docs/

