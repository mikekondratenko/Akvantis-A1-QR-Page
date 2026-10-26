# Akvantis — QR Box Demo

One page for a presentation: the code printed on the A1 carton, alone on black. A phone
pointed at the screen opens the product page (Digital-Passport-Landing-Page). Static, no
build step: `public/` is the site.

```
public/
  index.html        the page — the code on a white plate, the Akvantis mark and the A1 mark
  assets/qr.svg     the code itself, a picture (2026-10-07). ⚠ It encodes https://qrco.de/digital-passport —
                    a short link of an outside service that forwards to the product page
  favicon.png  apple-touch-icon.png
```

## Where the code leads

`TARGET` in `index.html`, one line. Now:
`https://akvantis-digital-passport-landing-page.michaelkondratenko.com/`. The carton's real
address is `https://id.akvantis.com/01/04270005511009` — put it there the day that host is
live. The encoder holds 84 bytes; a longer address is shown as text instead of a code.

The code is black on a white plate on purpose: an inverted (white on black) QR is not read by
many phone cameras.

## Run / deploy

`./serve.sh` → http://localhost:8092/. Opened from disk (double click) it works too.
Deploy as the other projects (`../DEPLOY.md`): a repository, Cloudflare → Import a
repository, root `public/`, worker `akvantis-a1-qr-page`. Not in `ui-kit/sync.mjs` — the page
uses nothing from the kit.
