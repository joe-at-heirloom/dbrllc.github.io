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

### Custom domain (not set up yet)

No domain has been purchased. The site currently serves at the GitHub Pages URL.

When a domain is purchased:

1. Create a `CNAME` file at the repo root containing the domain on a single line.
2. At the DNS provider, add either an A record (apex) or CNAME (subdomain) pointing at GitHub Pages:
   - Apex: A records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www`: CNAME to `joe-at-heirloom.github.io`
3. In repo Settings → Pages, enter the domain and check **Enforce HTTPS** once the certificate provisions.
4. Update the `canonical`, `og:url`, and Plausible `data-domain` references in `index.html` to match.

## Form

The contact form posts to **Formspree** at `https://formspree.io/f/xbdwgggg`. First submission triggers a confirmation email to the inbox associated with that endpoint — confirm before going live.

To get a Slack/SMS/Discord notification on each submission, set up a Zapier or Make integration on the Formspree side (no code change here).

## Analytics

[Plausible](https://plausible.io) is wired up via a defer script tag — no cookies, no banner needed. The `data-domain` attribute currently references the placeholder `designbuildrenovate.com`. Once a real domain is set up, update that attribute, sign up at plausible.io, add the domain as a site, and the script will start reporting.

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
