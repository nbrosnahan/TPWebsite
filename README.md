# Tumbling Potato — Website

The official website for [tumblingpotato.org](https://tumblingpotato.org).

A 90s-style "under construction" splash page built with [Hugo](https://gohugo.io), deployed to GitHub Pages.

## Local Development

Requires Hugo extended v0.157.0+.

```bash
hugo server
```

The site will be available at `http://localhost:1313`.

## Build

```bash
hugo --minify
```

Output goes to `./public/`.

## Deployment

Push to `main` — GitHub Actions builds and deploys to GitHub Pages automatically.
