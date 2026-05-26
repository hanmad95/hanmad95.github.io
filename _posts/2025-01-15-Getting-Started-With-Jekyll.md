---
title: Getting Started With Jekyll
date: 2025-01-15 10:30:00 +0100
categories: [Web Development, Static Site Generators]
tags: [jekyll, static-site, tutorial, ruby]
---

# Getting Started With Jekyll 🚀

Jekyll is a powerful static site generator that transforms your plain text into beautiful static websites. It's perfect for blogs, portfolios, and documentation sites.

## Why Jekyll?

- **Simple**: Write in Markdown, Jekyll handles the rest
- **Fast**: No database needed, just static HTML files
- **Secure**: Host anywhere, no server-side vulnerability concerns
- **GitHub Pages Integration**: Deploy directly from GitHub for free

## Installation

```bash
gem install jekyll bundler
jekyll new my-awesome-site
cd my-awesome-site
bundle exec jekyll serve
```

Visit `http://localhost:4000` in your browser to see your new site!

## Directory Structure

``` text
.
├── _config.yml          # Site configuration
├── _posts/              # Blog posts (YYYY-MM-DD-title.md)
├── _layouts/            # HTML templates
├── _includes/           # Partial templates
├── assets/              # CSS, images, JavaScript
└── _site/               # Generated output (don't edit!)
```

## Writing Your First Post

Create a new file in `_posts/` with the naming convention: `YYYY-MM-DD-title.md`

```markdown
---
title: My First Post
date: 2025-01-15 10:00:00 +0100
categories: [Getting Started]
tags: [jekyll, blogging]
---

# My First Post

Your content goes here...
```

## Front Matter Essentials

The YAML section at the top of each post is called "Front Matter":

- `title`: Post title
- `date`: Publication date and time
- `categories`: Organize posts by topic
- `tags`: Label your content for easy navigation

## Next Steps

- Choose a Jekyll theme (Chirpy, Minimal, etc.)
- Customize `_config.yml` with your site details
- Create more posts and pages
- Deploy to GitHub Pages for free hosting

Happy blogging! 📝
