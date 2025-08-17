# Mathematics Work Blog - Setup Guide

A daily work log for tracking mathematics PhD preparation progress.

## 🚀 Quick Start

### 1. Fork/Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/math-blog.git
cd math-blog
```

### 2. Install Jekyll (Local Development)

```bash
# Install Ruby (if not already installed)
# On macOS:
brew install ruby

# On Ubuntu:
sudo apt-get install ruby-full build-essential

# Install Jekyll and dependencies
bundle install
```

### 3. Run Locally

```bash
bundle exec jekyll serve
# Visit http://localhost:4000
```

## 📁 Project Structure

```
.
├── _config.yml          # Site configuration
├── _posts/              # Daily work logs
│   └── 2025-08-17-sheaf-cohomology.md
├── _weekly/             # Weekly reviews
│   └── week-33.md
├── _layouts/            # Page templates
│   ├── default.html
│   ├── post.html
│   └── weekly.html
├── _includes/           # Reusable components
│   ├── header.html
│   ├── stats.html
│   └── mathjax.html
├── assets/              # CSS, JS, images
│   ├── css/
│   └── js/
├── index.html           # Homepage
└── Gemfile             # Ruby dependencies
```

## ✍️ Creating a New Post

### Daily Work Log

1. Create a new file in `_posts/` with format: `YYYY-MM-DD-brief-title.md`
2. Copy the template front matter:

```yaml
---
layout: post
title: "Your Title Here"
author: jorys  # or tanguy
date: 2025-08-17 21:45:00 +0200
categories: [main-topic, sub-topic]
tags: [tag1, tag2, tag3]
hours: 5.5
math: true
resources:
  - name: "Resource Name"
    url: "https://..."
summary: "Brief summary for the homepage"
---
```

3. Write your content in Markdown
4. Use `$$...$$` for display math and `$...$` for inline math

### Weekly Review

1. Create a new file in `_weekly/` named `week-XX.md`
2. Use the weekly template format
3. Include reflections from both authors

## 🔢 Mathematics in Posts

### Inline Math
```markdown
The equation $e^{i\pi} + 1 = 0$ is beautiful.
```

### Display Math
```markdown
$$
\int_{\partial M} \omega = \int_M d\omega
$$
```

### Aligned Equations
```markdown
$$
\begin{align}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\epsilon_0} \\
\nabla \cdot \mathbf{B} &= 0
\end{align}
$$
```

## 🎨 Customizing Styles

Edit `assets/css/main.css` to modify:
- Color scheme (currently dark theme)
- Author colors (Jorys: purple, Tanguy: pink)
- Typography and spacing

## 📊 Updating Statistics

Statistics can be updated in `_config.yml`:

```yaml
stats:
  total_hours_jorys: 127
  total_hours_tanguy: 134
  current_streak: 12
  total_posts: 48
```

For automatic updates, create a GitHub Action or script.

## 🚢 Deployment

### GitHub Pages

1. Push to a repository named `USERNAME.github.io` (for user site) or any repo (for project site)
2. Go to Settings → Pages
3. Source: Deploy from branch
4. Branch: main (or master)
5. Folder: / (root)

The site will be available at:
- User site: `https://USERNAME.github.io`
- Project site: `https://USERNAME.github.io/REPO_NAME`

## 📝 Writing Tips

### For Daily Posts
- Keep entries focused on what you learned
- Include specific theorem numbers, page references
- Add code snippets for computational work
- Link to previous related posts
- Note questions and stuck points

### For Weekly Reviews
- Synthesize the week's learning
- Identify patterns and connections
- Celebrate achievements
- Plan for the next week
- Include cross-pollination insights

## 🛠️ Useful Commands

```bash
# Create a new post with today's date
./new_post.sh "Title of Your Post"

# Build the site
bundle exec jekyll build

# Serve with live reload
bundle exec jekyll serve --livereload

# Check for broken links
bundle exec htmlproofer ./_site
```

## 📚 Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [KaTeX Documentation](https://katex.org/)
- [Markdown Guide](https://www.markdownguide.org/)

## 🤝 Collaboration Workflow

1. **Daily Posts**: Each author commits their own posts
2. **Weekly Reviews**: Collaborate on a shared document, then one person commits
3. **Pull Requests**: For major changes to site structure
4. **Issues**: Track bugs, feature requests, and ideas

## 📈 Analytics (Optional)

Add Google Analytics or Plausible by including the tracking code in `_includes/analytics.html`:

```html
<!-- Plausible -->
<script defer data-domain="yourdomain.com" 
        src="https://plausible.io/js/script.js"></script>
```

## 🐛 Troubleshooting

### Math not rendering
- Ensure `math: true` in front matter
- Check for conflicting $ symbols in code blocks

### Build failures on GitHub Pages
- Check Gemfile compatibility with GitHub Pages
- Verify all plugins are whitelisted

### Local server not starting
- Run `bundle update`
- Check Ruby version compatibility

## 📧 Contact

- **Jorys**: [your-email]
- **Tanguy**: [tanguy-email]

---

*Happy blogging and good luck with your PhD applications! 🎓*
