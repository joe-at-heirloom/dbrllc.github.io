# Design Build & Renovate LLC

Single-page marketing site for Ian O'Ray's carpentry studio in St. Clair Shores, MI.

## Stack

Plain HTML, CSS, and a small bit of vanilla JS — no build step. Deploys to GitHub Pages from the root.

- `index.html` — the entire site
- `logo.svg`, `wordmark.svg` — brand marks
- `images/projects/` — project photography
- `images/portrait/` — portrait of Ian

## Local preview

```sh
python3 -m http.server 4322
# open http://127.0.0.1:4322/
```

## Outstanding items

Search the file for `TODO_IAN` for items needing input from Ian (license number, insurance carrier, additional testimonials, hi-res photo replacements, confirmed founding year, finalized domain).
