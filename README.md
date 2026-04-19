# BuildStack.AI

A single-page marketing site for **BuildStack.AI**—a dark, high-contrast landing page focused on software development and automation. All markup, styles, and client-side behavior live in one file, so there is no build step or package manager.

## What’s in the project

- **`index.html`** — Complete site: layout, embedded CSS, and JavaScript.
- **Hero** with headline, CTAs, stats, and a decorative terminal panel (hidden on small screens for layout).
- **Sections** for services, process, metrics (bento-style grid), enquiry forms, and a CTA footer.
- **Three.js** (via CDN) for an optional particle / wireframe background; the page still works if the script fails to load.
- **EmailJS** (via CDN) for enquiry form submissions; forms validate in the browser before sending.
- **Responsive layout** with a mobile navigation drawer and breakpoints for tablets and phones.
- **External link** in the nav: “Visit My Portfolio” (configurable URL in the HTML).

Fonts and some scripts are loaded from the public internet (Google Fonts, cdnjs, jsDelivr). You need a network connection for those assets to load as designed.

## Requirements

- A modern desktop or mobile **browser** (Chrome, Safari, Firefox, or Edge).
- **Python 3** is optional but recommended for local preview over HTTP (see below).

No Node.js, npm, or bundler is required.

## How to run locally

### Option A — Local HTTP server (recommended)

From the repository root:

```bash
cd /path/to/BuildStack.AI
python3 -m http.server 8080 --bind 127.0.0.1
```

Open in your browser:

**http://127.0.0.1:8080/index.html**

Stop the server with **Ctrl+C** in the terminal.

If you omit `--bind 127.0.0.1`, the server listens on all interfaces; `8080` can be changed to any free port.

### Option B — Open the file directly

On macOS:

```bash
open index.html
```

Or use your browser’s **File → Open** and choose `index.html`. Some features behave more predictably when served over `http://` (Option A), but static viewing usually works.

## Configuring enquiry email (EmailJS)

Form submission uses [EmailJS](https://www.emailjs.com/). Keys and template IDs are defined in `index.html` in the script block labeled **EMAILJS CONFIG**. Replace them with your own EmailJS public key, service ID, and template ID if you deploy your own instance.

## Deploying

Upload `index.html` (and any future assets you add) to any static host—GitHub Pages, Netlify, Vercel, S3, or your own web server. Ensure HTTPS if you rely on third-party scripts without mixed-content issues.

## File layout

```
BuildStack.AI/
├── index.html    # Entire site
└── README.md     # This file
```

---

© BuildStack.AI — see the footer in `index.html` for the displayed copyright year.
