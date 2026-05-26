# Hannes's Tech Portfolio & Blog

[![GitHub Pages](https://img.shields.io/badge/deployed-GitHub%20Pages-blue)][live-site]&nbsp;
[![Jekyll](https://img.shields.io/badge/built%20with-Jekyll-red.svg)][jekyll]&nbsp;
[![Chirpy Theme](https://img.shields.io/badge/theme-Chirpy-orange)][chirpy]&nbsp;
[![License](https://img.shields.io/github/license/hanmad95/hanmad95.github.io)][license]

## About

This is a personal technical portfolio and blog built with [Jekyll](https://jekyllrb.com/) and the [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) theme. The site showcases my coding projects, technical articles, and experience as a developer.

**Live Site**: [https://hanmad95.github.io](https://hanmad95.github.io)

### Features

✨ **Technical Blog** - In-depth articles on web development, best practices, and tools  
📂 **Project Showcase** - Highlighted personal and professional projects  
📝 **Categories & Tags** - Organized content for easy navigation  
⚡ **High Performance** - Static site generation for fast load times  
📱 **Responsive Design** - Works seamlessly on desktop, tablet, and mobile  
🔍 **SEO Optimized** - Automatic sitemap and metadata  
🚀 **Auto-Deploy** - GitHub Actions CI/CD pipeline
`_data`, `_layouts`, `_includes`, `_sass` and `assets`, as well as a small part of options of the `_config.yml` file
from the theme's gem. If you have ever installed this theme gem, you can use the command
`bundle info --path jekyll-theme-chirpy` to locate these files.

The Jekyll team claims that this is to leave the ball in the user’s court, but this also results in users not being
able to enjoy the out-of-the-box experience when using feature-rich themes.

To fully use all the features of **Chirpy**, you need to copy the other critical files from the theme's gem to your
Jekyll site. The following is a list of targets:

```shell
.
├── _config.yml
├── _plugins
├── _tabs
└── index.html
```

To save you time, and also in case you lose some files while copying, we extract those files/configurations of the
latest version of the **Chirpy** theme and the [CD][CD] workflow to here, so that you can start writing in minutes.

## Project Structure

``` text
_posts/          # Blog posts (YYYY-MM-DD-title.md)
_tabs/           # Navigation pages (About, Archives, Categories, Tags)
_data/           # Site metadata (contact, social)
_plugins/        # Custom Jekyll plugins
assets/          # Images, CSS, JavaScript
.github/         # GitHub Actions workflows
_config.yml      # Site configuration
```

## Writing Posts

Create files in `_posts/` with format: `YYYY-MM-DD-title.md`

```markdown
---
title: My Article
date: 2025-05-26 10:30:00 +0100
categories: [Web Development]
tags: [jekyll, tutorial]
---

# My Article

Content here...
```

## Updating Dependencies

```bash
bundle update              # Update all gems
bundle outdated            # Check for updates
bundle add gem-name        # Add new gem
```

## Troubleshooting

**Port already in use?**

``` bash
bundle exec jekyll serve --port 5000
```

**Changes not showing?**

``` bash
bundle exec jekyll clean
bundle exec jekyll serve
```

**Build fails?**

- Check `.github/workflows/pages-deploy.yml`
- Review Actions tab on GitHub
- Run `bundle install` locally

## Resources

- [Jekyll Docs](https://jekyllrb.com/docs/)
- [Chirpy Theme](https://github.com/cotes2020/jekyll-theme-chirpy)
- [GitHub Pages](https://docs.github.com/en/pages)

## License

Published under [MIT License][license].

---

**Built with ❤️ using Jekyll & Chirpy**

[live-site]: https://hanmad95.github.io
[jekyll]: https://jekyllrb.com/
[chirpy]: https://github.com/cotes2020/jekyll-theme-chirpy/
[license]: LICENSE
