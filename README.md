# tflix-redirect

[TFLIX](https://github.com/TomasTNunes/tflix) moved from `tflix.nunesnetwork.com` to **[tflix.stream](https://tflix.stream/)**.
This repo keeps the old address working: it's a GitHub Pages site on `tflix.nunesnetwork.com`
whose only page sends visitors on to the new domain.

- **Every path redirects**, keeping path and query, e.g.
  `tflix.nunesnetwork.com/stream/?type=movie&id=550` → `tflix.stream/stream/?type=movie&id=550`.
  `404.html` is an exact copy of `index.html`, so GitHub Pages serves it for any path.
- **Guests' saved data comes along.** Browsers keep localStorage per domain, so the page passes
  My List (`tflix_mylist`) and the chosen server (`tflix_server`) in the URL fragment
  (`#import=<base64url JSON>`), which never leaves the browser. The new site imports it once.
- **Old app versions** only allow their window to stay on the old domain, so the redirect is
  blocked there. After a moment the page shows a "TFLIX has moved, update the app" message whose
  download link opens in the system browser.

## Editing

Change `index.html`, then copy it over `404.html` so both stay identical.

## Retiring

Once old links and app versions are no longer in use, this repo can be deleted (or replaced by a
Cloudflare redirect rule for `tflix.nunesnetwork.com`).
