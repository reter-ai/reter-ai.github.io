# Codeine Website

GitHub Pages website for [codeine.ai](https://codeine.ai)

## Setup

This repository should be named `codeine-ai.github.io` on GitHub for automatic GitHub Pages deployment.

## Local Development

1. Install Ruby and Bundler
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Run the development server:
   ```bash
   bundle exec jekyll serve
   ```
4. Open http://localhost:4000

## Deployment

The site is automatically deployed to GitHub Pages when changes are pushed to the main branch.

To use a custom domain (codeine.ai):
1. Add a `CNAME` file with `codeine.ai`
2. Configure DNS to point to GitHub Pages

## Structure

```
codeine-ai.github.io/
├── _config.yml          # Jekyll configuration
├── _layouts/            # HTML layout templates
│   ├── home.html        # Homepage layout
│   ├── page.html        # Static page layout
│   └── doc.html         # Documentation page layout
├── _docs/               # Documentation collection
│   ├── getting-started.md
│   ├── features.md
│   └── examples.md
├── assets/css/          # Stylesheets
│   └── modern.scss      # Main theme
├── index.md             # Homepage
├── about.md             # About page
├── Gemfile              # Ruby dependencies
└── README.md            # This file
```

## Theme

The site uses a custom theme based on the minima Jekyll theme with modern styling.
