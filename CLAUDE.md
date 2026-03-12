# CLAUDE.md — AI Assistant Guide for `analytics`

This file provides context for AI assistants (Claude Code and others) working in this repository.

---

## Project Overview

This is a **static multi-page web project** hosted on GitHub Pages with a custom domain (`mmdc.oyag.com`). It showcases modern CSS/HTML techniques and contains a data analytics report for an e-commerce store redesign. There is no build system, no backend, and no external dependencies.

- **Custom domain**: `mmdc.oyag.com` (configured via `CNAME`)
- **Hosting**: GitHub Pages (static files served directly from the repo)
- **Content language**: Traditional Chinese (zh-TW) throughout all pages

---

## Repository Structure

```
analytics/
├── CNAME                  # Custom domain for GitHub Pages → mmdc.oyag.com
├── CLAUDE.md              # This file
├── index.html             # Root landing page — navigation hub to all sub-pages
├── docs/
│   └── index.html         # Minimal docs entry linking to web1 and web2
├── web1/
│   └── index.html         # E-commerce analytics report (primary content, 932 lines)
├── web2/
│   └── index.html         # Dynamic gradient/animation demo page
└── web3/
    └── index.html         # Starfield and wave animation demo page
```

**Adding new pages**: Create a new folder `webN/` with an `index.html` inside, then add a navigation card to the root `index.html`.

---

## Tech Stack

| Layer        | Technology                       |
|--------------|----------------------------------|
| Markup       | HTML5                            |
| Styling      | CSS3 (inline `<style>` blocks)   |
| Scripting    | Vanilla JavaScript (inline)      |
| Dependencies | None — zero external libraries   |
| Build tools  | None — no npm, webpack, etc.     |
| Backend      | None — fully static              |
| Testing      | None — no test infrastructure    |

All CSS and JavaScript is written inline within each `index.html` file. There are no shared stylesheets or shared script files.

---

## Page Descriptions

### `index.html` — Landing Hub
- Presents three web-page cards in a responsive grid
- Glassmorphism card design with purple-blue gradient background
- Smooth hover animations; links to `web1/`, `web2/`, `web3/`
- Displays aggregate stats: 3 test pages, 100% responsive, 0 external dependencies

### `web1/index.html` — E-commerce Analytics Report
- The most complex page (932 lines)
- Reports on ECstore website redesign impact (March 2024 – January 2025, 48 weeks)
- Tabbed navigation (JavaScript tab-switching with `data-section` attributes)
- Key sections: Executive Summary, Statistical Analysis, Timeline Analysis, Confounding Factors, Risk Assessment, Business Insights, Action Recommendations, Conclusion
- Sticky header, right-side scroll-indicator dots, progress bars with shimmer animation
- Key finding: overall conversion efficiency increase of 0.9%, p < 0.001, credibility score 70%

### `web2/index.html` — Animation Demo
- Continuously shifting gradient background (8s CSS keyframe loop)
- Pulsing emoji logo, stats cards, navigation buttons to web1 and web3

### `web3/index.html` — Starfield Demo
- 50 twinkling stars generated via JavaScript on load (`generateStars()`)
- Glowing animated title, wave animation bars, glassmorphism feature cards
- Navigation cards linking back to other pages

### `docs/index.html`
- Three-line minimal page with raw anchor links to web1 and web2

---

## Design Conventions

All pages share these visual/code conventions:

1. **Glassmorphism**: `background: rgba(255,255,255,0.1); backdrop-filter: blur(10px);`
2. **Dark gradient backgrounds**: Deep purple/blue linear-gradient on `body`
3. **CSS animations**: Defined as `@keyframes` blocks, applied with `animation:` shorthand
4. **Responsive breakpoints**: Single breakpoint at `max-width: 768px` using `@media` queries
5. **No external fonts**: System fonts or `font-family: 'Segoe UI', sans-serif`
6. **Inline everything**: All CSS lives in `<style>` tags; all JS lives in `<script>` tags within the same HTML file
7. **Traditional Chinese copy**: All user-facing text is in zh-TW

---

## Development Workflow

### Making Changes

1. Edit the relevant `index.html` file directly — no compilation step needed.
2. Preview locally by opening the file in a browser (`file://...`) or using any static file server (e.g., `python3 -m http.server 8080`).
3. Commit and push to the appropriate branch.

### Git Workflow

```bash
# Check current branch
git branch

# Stage and commit
git add <file>
git commit -m "Descriptive message"

# Push to remote
git push -u origin <branch-name>
```

- **Default branch**: `master`
- **Feature branches**: Use descriptive branch names; Claude Code uses `claude/<task-id>` prefixed branches.
- **Do not** push directly to `master` without review if working on a feature branch.

### Local Preview

```bash
# Simple HTTP server (Python 3)
python3 -m http.server 8080
# Then open http://localhost:8080
```

No npm install, build step, or environment setup is required.

---

## No Tests, No CI/CD

- There are **no automated tests** in this project.
- There are **no CI/CD pipeline files** (no `.github/workflows/`, no `Dockerfile`, etc.).
- GitHub Pages deploys automatically from the `master` branch on every push.

---

## Conventions for AI Assistants

- **Edit existing files**: Prefer `Edit` over rewriting whole files. Each page is self-contained.
- **Keep styles inline**: Do not extract CSS into separate `.css` files unless explicitly asked.
- **Keep scripts inline**: Do not extract JS into separate `.js` files unless explicitly asked.
- **Maintain language**: All user-visible text must remain in Traditional Chinese (zh-TW).
- **No dependencies**: Do not add npm packages, CDN links, or external frameworks unless explicitly requested.
- **No build tooling**: Do not introduce `package.json`, webpack, or similar unless explicitly requested.
- **Preserve design language**: New pages/components should follow the glassmorphism + dark gradient aesthetic already established.
- **Adding a new page**: Create `webN/index.html`, add a navigation card to root `index.html`, and update the stats counter if appropriate.
- **Commit messages**: Use clear imperative-style messages, e.g., `Add web4 page with timeline chart`.

---

## Key File Locations (Quick Reference)

| Purpose                        | Path                        |
|--------------------------------|-----------------------------|
| Root landing page              | `index.html`                |
| Analytics report (primary)     | `web1/index.html`           |
| Animation demo                 | `web2/index.html`           |
| Starfield demo                 | `web3/index.html`           |
| Docs entry                     | `docs/index.html`           |
| Custom domain config           | `CNAME`                     |
