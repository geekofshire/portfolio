# Rohan Jha - Portfolio

A single-page portfolio built with Hugo and deployed through GitHub Pages.

## Requirements

- Hugo Extended 0.158 or newer
- Git

## Local development

Start the development server:

```bash
hugo server --buildDrafts
```

Open `http://localhost:1313/portfolio/`.

Create a production build:

```bash
hugo --gc --minify
```

The generated site is written to `public/`.

## Project structure

```text
.
├── assets/
│   ├── css/main.css
│   └── js/main.js
├── content/_index.md
├── data/portfolio.yaml
├── layouts/home.html
├── static/
│   ├── favicon.svg
│   └── images/
├── .github/workflows/hugo.yaml
└── hugo.yaml
```

## Updating content

Portfolio content is stored in `data/portfolio.yaml`. The file contains profile
details, experience, projects, skills, education, and external links.

The categorized skills reference is available in [`docs/SKILLS.md`](docs/SKILLS.md).

## Profile image

Add a square portrait at:

```text
static/images/profile.jpeg
```

A photo of at least 1000 × 1000 pixels is recommended. The template displays the
`RJ` monogram until this file exists.

## Deployment

The workflow in `.github/workflows/hugo.yaml` builds and deploys the site whenever
changes are pushed to `main`. In the GitHub repository settings, set the Pages
source to **GitHub Actions**.

The workflow supplies the correct GitHub Pages base URL during the build. The
configured `baseURL` can be replaced when a custom domain is connected.
