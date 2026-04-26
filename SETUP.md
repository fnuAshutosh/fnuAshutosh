# GitHub Pages Website & Blog Setup

A beautiful, professional GitHub Pages website showcasing your research engineering expertise with an integrated blog.

## 🚀 Getting Started

This repository contains:
- **Professional Profile README** - Eye-catching GitHub profile
- **Personal Website** - Beautiful landing page
- **Blog Platform** - Technical articles and insights
- **Projects Showcase** - Featured projects and work
- **CV Page** - Professional resume

## 📋 Features

✨ **What's Included:**
- Responsive, modern design
- SEO optimized pages
- Blog with categories and tags
- Projects portfolio
- CV/Resume page
- Social media integration
- Beautiful typography and layout
- Mobile-friendly design
- Fast load times

## 🛠️ Local Development

### Prerequisites
- Ruby 2.7 or higher
- Bundler (`gem install bundler`)

### Setup

1. Clone this repository
```bash
git clone https://github.com/yourusername/yourusername.github.io.git
cd yourusername.github.io
```

2. Install dependencies
```bash
bundle install
```

3. Run Jekyll server
```bash
bundle exec jekyll serve
```

4. Open in browser
```
http://localhost:4000
```

## 📝 Customization

### Update Your Information

1. **Profile README** (`README.md`)
   - Update name, title, and bio
   - Update LinkedIn URL
   - Add your skills and interests

2. **Site Configuration** (`_config.yml`)
   - Update title, email, description
   - Update social media links
   - Customize baseurl and url

3. **Homepage** (`index.html`)
   - Update about section
   - Modify skills list
   - Add/edit projects

4. **CV** (`cv.html`)
   - Update education and experience
   - Add publications
   - Update awards and certifications

5. **Projects** (`projects.html`)
   - Add your actual projects
   - Update GitHub links
   - Add project descriptions

### Add Blog Posts

Create new markdown files in the `_posts` directory with the naming convention:
```
_posts/YYYY-MM-DD-post-title.md
```

Example front matter:
```yaml
---
layout: post
title: "Your Post Title"
date: 2025-12-15
categories: [Category1, Category2]
tags: [tag1, tag2]
excerpt: "Short description of your post"
---
```

### Colors & Styling

The current color scheme uses a gradient purple theme. To customize:

1. Find color values: `#667eea` (primary) and `#764ba2` (secondary)
2. Replace with your preferred colors in HTML files
3. Update CSS gradients and hover states

## 🌐 Deploy to GitHub Pages

1. Commit your changes
```bash
git add .
git commit -m "Update profile and website"
```

2. Push to main branch
```bash
git push origin main
```

3. Your site will be live at: `https://yourusername.github.io`

## 📁 Project Structure

```
.
├── _config.yml           # Jekyll configuration
├── _posts/              # Blog posts (markdown files)
├── index.html           # Homepage
├── blog/                # Blog index page
├── projects.html        # Projects showcase
├── cv.html              # CV/Resume page
├── Gemfile              # Ruby dependencies
├── README.md            # GitHub profile
└── assets/              # Images and CSS
```

## 🎨 Customization Tips

- **Change colors**: Search and replace hex colors in HTML files
- **Update fonts**: Modify CSS font-family properties
- **Add sections**: Copy existing component structure
- **Images**: Add to assets/ folder and reference with `/assets/image-name.jpg`

## 📚 Content Ideas

**Blog Post Topics:**
- Technical deep dives into your research
- Implementation tutorials
- Tool reviews and comparisons
- Project retrospectives
- Industry insights

**Projects to Showcase:**
- GitHub repositories
- Research papers
- Open-source contributions
- Side projects

## 🔗 Links & Resources

- [Jekyll Documentation](https://jekyllrb.com/)
- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub Pages Docs](https://pages.github.com/)
- [KaTeX (Math Rendering)](https://katex.org/)

## ✅ Pre-Launch Checklist

- [ ] Update name and bio in README.md
- [ ] Update LinkedIn profile URL
- [ ] Create 3-5 blog posts
- [ ] Update CV with your experience
- [ ] Add your actual projects
- [ ] Customize colors to your preference
- [ ] Test locally with `jekyll serve`
- [ ] Push to GitHub main branch
- [ ] Verify site loads at `yourusername.github.io`

## 📧 Contact & Support

For customization help or questions:
- Check Jekyll docs: https://jekyllrb.com/docs/
- Review GitHub Pages: https://pages.github.com/
- Open an issue in this repo

## 📄 License

This template is open source and available under the MIT License.

---

**Built with ❤️ for Research Engineers**

Happy blogging! 🚀
