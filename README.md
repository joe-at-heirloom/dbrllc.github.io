# Design Build & Renovate LLC

Single-page marketing site for Ian O'Ray's carpentry studio in St. Clair Shores, MI.

## Stack

Plain HTML, CSS, and a small bit of vanilla JS — no build step. Deploys to GitHub Pages from the root.

- `index.html` — the entire site
- `logo.svg`, `wordmark.svg` — brand marks
- `og-image.jpg` — 1200×630 share card
- `favicon-32.png`, `apple-touch-icon.png`, `icon-192.png`, `icon-512.png` — favicon set
- `site.webmanifest` — PWA manifest
- `sitemap.xml`, `robots.txt` — SEO basics
- `CNAME` — custom domain for GitHub Pages
- `images/projects/` — project photography (WebP for featured photos, JPG/WebP originals)
- `images/portrait/` — portrait of Ian

## Local preview

```sh
python3 -m http.server 4322
# open http://127.0.0.1:4322/
```

## Deployment

GitHub Pages is configured to serve from `main` branch root. Pushes to `main` deploy automatically within ~1 minute.

### Custom domain

The `CNAME` file points GitHub Pages at `designbuildrenovate.com`. To activate:

1. At your DNS provider, add an A record (apex) or CNAME (subdomain) pointing at GitHub Pages:
   - Apex: A records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www`: CNAME to `joe-at-heirloom.github.io`
2. In repo Settings → Pages, enter the domain and check **Enforce HTTPS** once the certificate provisions.

If using a different domain, edit the `CNAME` file and the canonical/og-url meta tags in `index.html`.

## Form

The contact form posts to **Formspree** at `https://formspree.io/f/xbdwgggg`. First submission triggers a confirmation email to the inbox associated with that endpoint — confirm before going live.

To get a Slack/SMS/Discord notification on each submission, set up a Zapier or Make integration on the Formspree side (no code change here).

## Analytics

[Plausible](https://plausible.io) is wired up via a defer script tag — no cookies, no banner needed. Sign up at plausible.io, add `designbuildrenovate.com` as a site, and the existing script tag will start reporting.

## Outstanding items

Search the file for `TODO_IAN` for items needing input from Ian:

- Builder license number for footer
- Insurance carrier name
- About / bio paragraph
- Additional verified testimonials (full client names)
- Hi-res photo replacements (currently FB-quality)
- Confirmed founding year (default: 2019)
- Finalized domain (default: designbuildrenovate.com)
- Studio portrait at higher resolution
