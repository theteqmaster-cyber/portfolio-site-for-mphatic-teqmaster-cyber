# Portfolio site — Mphatic Teqmaster Cyber

A professional, simple, and clean portfolio website for **Sir Mphatic** (aka **Teqmaster Cyber** / **Hydramnt**). Heavy frontend, static multi-page site built with HTML, CSS, and React (CDN).

## Goal

Produce a website that shows everything about Mphatic: who you are, what you offer, your skills, projects, and how to get in touch — with a polished, modern look and multi-page structure.

## Tech stack

- **HTML** — Semantic markup, multi-page structure
- **CSS** — One shared `styles.css`: dark gradient, glow blobs, cards, buttons, responsive breakpoints, reduced-motion support
- **React (CDN)** — Used only on the homepage (`index.html` + `app.js`) for sticky nav, mouse-reactive hero, and section previews

No build step: open `index.html` in a browser or serve the folder with any static server.

## Run locally

1. Clone or download this repo.
2. **Option A — open in browser:**  
   Open `index.html` in your browser. For full behavior (no `file://` CORS issues with React), use a local server.
3. **Option B — local server (recommended):**
   ```bash
   # Python 3
   python3 -m http.server 8000

   # or Node (npx)
   npx serve .
   ```
   Then visit `http://localhost:8000` (or the port shown).

## File structure

```
├── index.html          # Homepage (React app: hero, preview sections, footer)
├── app.js              # React SPA for homepage (sticky nav, mouse-reactive hero, CTAs)
├── styles.css          # Global styles (dark theme, layout, cards, responsive)
├── about.html          # About page
├── services.html       # Services page
├── skills.html         # Skills page
├── projects.html       # Projects page
├── contact.html        # Contact page
├── hydra-space.html    # Hydra Space — extra page linked from hero
└── README.md           # This file
```

## Multi-page structure

- **Homepage** (`index.html`): React-driven landing with sticky nav, hero (mouse tilt + spotlight), short previews for About / Services / Skills / Projects, contact CTA, and footer. Nav and hero buttons link to the separate pages.
- **Content pages** (`about.html`, `services.html`, `skills.html`, `projects.html`, `contact.html`): Static HTML with the same header, footer, and `styles.css`. Each has a page header and content area.
- **Hydra Space** (`hydra-space.html`): Linked from the hero (“Hydra Space” button). Same layout; use it for a blog, links, or any extra hub.

## Editing content (comment-based workflow)

Each content page includes **inline HTML comments** (`<!-- EDIT: ... -->`) so you can find where to add or change data:

- **about.html** — Intro and “Details” section (paragraphs, lists).
- **services.html** — Service cards; duplicate one card block to add a new service.
- **skills.html** — Skill items (card blocks); copy one `<li class="card">` to add a skill.
- **projects.html** — Project cards; duplicate a card and set title, description, and optional link.
- **contact.html** — Contact details (email, social/GitHub links).
- **hydra-space.html** — Whatever you want Hydra Space to be (text, cards, links).

Search for `EDIT` in any of these files to jump to the editable spots.

## Features (from spec)

- Sticky navigation with links to About, Services, Skills, Projects, Contact
- Hero with **mouse-reactive** tilt and spotlight on the “Sir Mphatic — Teqmaster Cyber” card; resets on mouse leave
- **Animated gradient shimmer** on the hero name/title
- **Dark gradient** background and **animated glow blobs** (no plain white)
- **Reduced-motion**: respects `prefers-reduced-motion` (animations/transitions disabled for that preference)
- Responsive layout and mobile breakpoints
- Shared visual system across all pages (cards, buttons, section bands)
