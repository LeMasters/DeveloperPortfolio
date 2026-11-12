# Developer Portfolio: student template (test)

A multi-page portfolio site for games students: Home, About, Portfolio (one page per project), Blog and Contact. It's a Hugo site, edited through Pages CMS forms, published free on GitHub Pages. Students never install anything or edit code.

Every text field starts with a description of what belongs in it, and the images are labelled placeholders showing the recommended size. Replace each one, or switch a section off (or delete its entries) to hide it.

**Theme:** [Developer Portfolio](https://github.com/samrobbins85/hugo-developer-portfolio) by Sam Robbins, MIT License (see `themes/hugo-developer-portfolio/LICENSE`). Copied unmodified from commit `9feb68b` (15 Oct 2025). All changes are site-level overrides, listed below. The theme's `exampleSite/` is not used.

## Getting started

1. Make your own copy of this repository.
2. **Settings → Pages → Source: GitHub Actions.** Then, in the **Actions** tab, re-run the first "Publish site" run, which fails until Pages is turned on.
3. Sign in at app.pagescms.org with GitHub, give Pages CMS access to the repository, and open it.
4. Fill in the forms. Each save rebuilds the site in one to two minutes.

## What's where

| Path | What it is | Edited through |
|---|---|---|
| `themes/hugo-developer-portfolio/` | The theme, unmodified | Nobody |
| `layouts/` | Site-level overrides of theme files (see below). Hugo uses these in place of the theme's files of the same name. | Template author |
| `config/_default/hugo.toml` | Technical settings and the menu | Template author |
| `config/_default/params.yaml` | Name, description, sharing image, email, location | Pages CMS → Profile |
| `data/homepage.yml` | Every homepage section | Pages CMS → Homepage |
| `data/about.yml` | Leadership and teamwork (About page) | Pages CMS → About page – Leadership and teamwork |
| `data/portfolio.yml` | Filter buttons on the Portfolio page | Pages CMS → Portfolio filters |
| `content/about/_index.md` | About page text and photo | Pages CMS → About page |
| `content/portfolio/*.md` | One file per project | Pages CMS → Projects |
| `content/blog/*.md` | One file per post | Pages CMS → Blog |
| `content/contact/_index.md` | Contact page text | Pages CMS → Contact page |
| `static/images/` | Uploaded images | Pages CMS image fields |
| `.pages.yml` | Defines the Pages CMS forms | Template author |
| `.github/workflows/hugo.yml` | Builds and publishes the site after every change (Hugo 0.147.0) | Template author |

## Overrides of the theme

| File | Change from the theme |
|---|---|
| `partials/url.html` | New helper. Makes every link and image field work when the site lives in a subfolder (`username.github.io/repository/`), and adds `https://` to addresses typed without it. |
| `partials/social-url.html` | New helper. Social links accept a username or a pasted full address. |
| `_default/_markup/render-image.html`, `render-link.html` | Images and links inside write-ups and posts go through the same helper. |
| `partials/head.html` | Page titles built from the student's name; sharing image works in a subfolder; stylesheets fingerprinted so browsers fetch new versions; UIkit loaded directly. Removed: favicon links to files not shipped, the mailgo pop-up script. |
| `partials/header.html` | Home and menu links work in a subfolder; active-page highlight fixed (the theme marked every item active in a subfolder); Blog and Portfolio hidden from the menu when empty. Removed: Google Analytics hook. |
| `partials/footer.html` | Location as plain text (theme: Google Maps pop-up needing an API key); plain copyright line (theme: a Creative Commons BY badge licensing every student's work); empty fields hidden. |
| `index.html` | Homepage. All images and links through the helper; no broken-image icons; itch.io and YouTube links added; "Hackathons" retitled "Game jams"; featured-project link text editable; Publications no longer depend on Education being switched on. Certifications and Publications still work but have no student forms. |
| `_default/single.html` | Project and post pages. Team, website and GitHub buttons independent of each other; website button text editable (e.g. "Play it on itch.io"); main image shown under the title; GitHub icon from UIkit (theme: an image on the theme author's account). |
| `_default/list.html` | Blog page, newest first. |
| `portfolio/list.html` | Portfolio page, newest first; filter buttons only when filters exist; no broken-image icons. |
| `about/list.html` | About page photo and logos through the helper; empty sections hidden. |
| `contact/list.html` | Contact page shows the student's text and an email button (theme: a form that sends nothing without a Formspree account). |
| `404.html` | A "Page not found" page (the theme's file is empty). |
| `assets/css/style.css`, `index.css`, `hexagon.css` | Copies of the theme's stylesheets with its font settings removed, so every page uses the visitor's system font (UIkit's default). The theme named fonts it never loaded (Cantarell, Raleway) and downloaded two from Google Fonts it barely used (Roboto, Playfair Display), so typefaces changed from place to place and from computer to computer. Headings and tables in `_default/single.html` lose their font settings for the same reason. |
