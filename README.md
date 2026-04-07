# fourthlinellc.com

Single-page website for Fourth Line LLC. Built with [Astro](https://astro.build/), deployed to GitHub Pages.

## Project Structure

```
/
├── public/
│   ├── favicon.ico             # Site favicon
│   ├── img/
│   │   ├── logo.png            # Fourth Line LLC logo
│   │   └── bg-mobile-fallback.jpg  # Background image for mobile devices
│   └── mp4/
│       └── bg.mp4              # Background video
├── src/
│   └── pages/
│       └── index.astro         # Single-page site (all CSS inlined)
├── astro.config.mjs            # Astro config
└── .github/
    ├── dependabot.yml          # Weekly npm dependency updates
    ├── lighthouse/
    │   └── lighthouserc.json   # Lighthouse audit thresholds
    └── workflows/
        ├── deploy.yml          # Build + deploy to GitHub Pages on push to main
        ├── verify.yml          # Build check on pull requests
        ├── lighthouse.yml      # Lighthouse audit on pull requests
        └── link-checker.yml    # Weekly broken link check
```

## Development

```sh
npm install        # Install dependencies
npm run dev        # Start dev server at localhost:4321
npm run build      # Build production site to ./dist/
npm run preview    # Preview production build locally
```

## Deployment

The site deploys automatically to GitHub Pages when changes are pushed to `main`. The workflow is defined in `.github/workflows/deploy.yml`.

Pull requests run:
- **Build check** (`verify.yml`)
- **Lighthouse audit** (`lighthouse.yml`) — warns if performance, accessibility, or best practices scores drop below 0.9; errors if SEO drops below 0.9

A weekly **link checker** (`link-checker.yml`) scans for broken links every Monday.

**Dependabot** checks for npm dependency updates weekly.
