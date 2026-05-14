# Utzi1's Portfolio Website

Welcome to my GitHub Pages portfolio! This site is built with **Markdown**, **Jekyll**, and **GitHub Pages**.

## 📖 Site Structure

- **`index.md`** — Home page
- **`about.md`** — About me and my background
- **`projects.md`** — Overview of my projects
  - **`projects/biotech.md`** — Biotechnology research
  - **`projects/ml.md`** — Machine learning & AI
  - **`projects/tools.md`** — Tools and utilities
- **`blog/`** — Blog posts
  - **`blog/neovim-setup.md`** — Neovim configuration guide
  - **`blog/vae-intro.md`** — Variational Autoencoders introduction
  - **`blog/data-analysis.md`** — Data analysis best practices
- **`resources.md`** — Useful links and tools
- **`_config.yml`** — Jekyll configuration

## 🚀 Quick Start

### Local Testing (Optional)

If you want to test this site locally:

```bash
# Install Ruby and Jekyll
gem install bundler jekyll

# In the repo directory
bundle install
bundle exec jekyll serve
```

Then visit `http://localhost:4000`

### Updating the Site

1. Edit any `.md` file
2. Commit and push to `main` branch
3. GitHub Pages automatically rebuilds your site
4. Visit `https://utzi1.github.io` to see changes

## 📝 Adding Content

### Create a New Blog Post

```bash
# Create file: blog/my-new-post.md
---
# Post title in markdown
# Posted: [date]

Your content here...
```

### Create a New Project Page

```bash
# Create file: projects/new-project.md
# Add link from projects.md
```

### Update Navigation

Edit `index.md` to add links to new pages:

```markdown
- [New Page](new-page.md)
```

## 🎨 Customization

### Change Theme

Edit `_config.yml`:

```yaml
theme: jekyll-theme-minimal  # or another theme
```

Other themes:
- `jekyll-theme-cayman`
- `jekyll-theme-leap-day`
- `jekyll-theme-merlot`
- `jekyll-theme-slate`
- `jekyll-theme-dinky`

### Add Custom Styling

Create `assets/css/style.scss`:

```scss
---
---
@import "{{ site.theme }}";

body {
  background-color: #f5f5f5;
}
```

## 📚 Resources

- [Markdown Guide](https://www.markdownguide.org/)
- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Docs](https://docs.github.com/en/pages)

## 🔗 Links

- 🏠 **Website**: https://utzi1.github.io
- 🐙 **GitHub**: https://github.com/Utzi1
- 📬 **Issues & Feedback**: GitHub Issues

---

**Built with ❤️ using GitHub Pages & Markdown**

Last updated: 2026-05-14
