# Personal Site — Jekyll + GitHub Pages

A minimal academic portfolio and writing site built with Jekyll.

## Local development

You'll need Ruby installed. Then:

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000` in your browser.

## Deploy to GitHub Pages

1. Create a new GitHub repo named `yourusername.github.io`
2. Push this folder to the `main` branch
3. Go to repo Settings → Pages → Source: Deploy from branch → `main` → `/ (root)`
4. Your site will be live at `https://yourusername.github.io` within a minute or two

## Customise

- **`_config.yml`**: Set your name, description, URL, email, social links
- **`index.md`**: Your homepage intro
- **`research.md`**: Papers and research interests
- **`writing.md`**: Auto-populated from `_posts/`
- **`_layouts/default.html`**: Footer links (email, GitHub, Scholar)
- **`assets/css/main.css`**: All styles in one file

## Adding a post

Create a file in `_posts/` named `YYYY-MM-DD-your-title.md` with this frontmatter:

```markdown
---
layout: post
title: "Your Post Title"
date: 2026-04-24
---

Your content here...
```

## Adding a paper

Edit `research.md` and duplicate the `<li class="paper-item">` block.

## Custom domain (optional)

1. Add a `CNAME` file at the root with just your domain: `yourdomain.com`
2. Point your domain's DNS to GitHub Pages (see GitHub docs)
