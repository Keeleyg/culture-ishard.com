# culture-ishard.com

Single-page static marketing site for **Culture Is Hard** by Gavin Keeley (Vidimus, 2026), the companion to *Lead On Purpose*. Hosted on GitHub Pages with a custom domain.

It is the third of three sibling sites, all built the same way:

- [lead-onpurpose.com](https://lead-onpurpose.com) — the companion book's site
- [gavinkeeley.com](https://gavinkeeley.com) — the author's hub
- **culture-ishard.com** — this repo

## What's here

| File | Purpose |
| --- | --- |
| `index.html` | The entire page (semantic HTML, anchor sections, tiny vanilla JS for smooth scroll and sticky nav). |
| `styles.css` | All styling. Dark, structural identity: warm near-black base, off-white text, muted rust/ochre accent, Fraunces + Inter, strata dividers. |
| `favicon.svg` | Monochrome stratified-rock motif. |
| `book-cover.png` | The cover art. **Not yet added** — until it exists, a CSS-styled placeholder renders in its place so the layout never breaks. |
| `CNAME` | Declares the custom domain `culture-ishard.com` to GitHub Pages. |
| `.nojekyll` | Tells Pages to serve files as-is, no Jekyll build. |

No framework, no build step, no npm, no analytics, no trackers. Google Fonts are loaded via `<link>`.

## Editing content

All copy lives directly in `index.html`, in document order:

1. **Hero** — eyebrow, title, the lead hook quote, sub-line, buttons.
2. **The Argument** (`#argument`) — the 84% statistic and the "residue does not lie" pull quote.
3. **What Changed** (`#changed`) — the two cards (AI and the courts) and the closing line.
4. **The Book** (`#book`) — description, "What you'll find" list, buy buttons.
5. **About the Author** (`#author`) — bio and credential strip.
6. **Further Reading** (`#reading`) — the four related books.
7. **CTA banner + footer** — closing line, links, copyright.

Colours, fonts and spacing are CSS custom properties at the top of `styles.css` (`:root`). Change the accent in one place via `--accent`.

## Outstanding TODOs

Search the codebase for `TODO` to find these in context:

- **ISBN** — placeholder comment in the `<head>` of `index.html`.
- **Amazon URL** — the "Coming to Amazon" badge in the `#book` section. Replace the `<span class="coming-soon-badge">` with the commented-out `<a ... class="btn btn-accent">` once the link exists.
- **book-cover.png** — drop the real cover art into the repo root as `book-cover.png`. The placeholder disappears automatically once the file is present.

## Local preview

No server strictly required (it is plain files), but to match Pages behaviour:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

On Windows: `python -m http.server 8000`.

## Hosting: GitHub Pages + custom domain

The repo is published with GitHub Pages serving from the **root of `main`**. The `CNAME` file sets the custom domain to `culture-ishard.com`.

### DNS records to create at the registrar

Point the apex (`culture-ishard.com`) at GitHub Pages with these four A records:

```
A   @   185.199.108.153
A   @   185.199.109.153
A   @   185.199.110.153
A   @   185.199.111.153
```

And the `www` subdomain as a CNAME to the GitHub Pages target:

```
CNAME   www   keeleyg.github.io.
```

(Optionally add the four `AAAA` records for IPv6: `2606:50c0:8000::153`, `...8001::153`, `...8002::153`, `...8003::153`.)

### Enforce HTTPS

Once DNS resolves to GitHub and the certificate provisions (can take up to 24 hours), tick **Settings → Pages → Enforce HTTPS** in the repo. It is intentionally left off at launch because the certificate cannot be issued until DNS points at GitHub.

## Voice and copy rules

If you edit copy, keep the house style: no em dashes, straight quotes only, British/Australian spelling (organisation, recognise, colour), no AI-vocabulary filler. The back-cover quotes are verbatim and should not be reworded.

---

© 2026 Gavin Keeley. All rights reserved.
