# Agarwal Textiles ERP — PWA

Installable mobile/desktop app version of your `erp-demo (3).html`. Same design, same data,
same screens — now a **Progressive Web App**: it installs to the home screen, runs full-screen
(no browser bar), works offline, and has a proper mobile layout with a slide-out menu.

## Files
- `index.html` — the app (your original, + PWA hooks + mobile responsive CSS + hamburger nav)
- `manifest.webmanifest` — app name, icons, theme, standalone display
- `sw.js` — service worker (offline caching)
- `icon.svg`, `icon-192.png`, `icon-512.png`, `icon-maskable.png` — app icons

## Run it (a server is required — PWAs don't work from file://)

From this folder:
```bash
# pick any one
npx serve .            # Node
python -m http.server  # Python
```
Then open the printed URL (e.g. http://localhost:3000). On the **same Wi-Fi**, open that URL
on your phone — it works immediately, and you can install it.

## Install as an app
- **Android (Chrome):** tap the **Install app** button (bottom-right), or ⋮ → *Install app* /
  *Add to Home screen*.
- **iPhone (Safari — must be Safari):** Share button → *Add to Home Screen* → Add.
- **Desktop (Chrome/Edge):** the **Install app** button, or the install icon in the address bar.

After installing it opens full-screen with the clay "A" icon — looks and behaves like a native app.

## Demo shortcuts
Deep-link straight into any role/screen with URL params (handy on stage):
`?role=CEO` · `?role=MANAGER` · `?role=FIELD&tab=field` · `?role=CHECKPOST&tab=alteration`
Roles: CEO, HR, ACCOUNTS, MANAGER, CHECKPOST, FIELD. Add `&tab=<name>` for a specific module.

## What changed vs the original HTML
Nothing was removed. Added only:
- PWA manifest + service worker + iOS/Android meta tags + icons (installable, offline)
- A `@media (max-width:820px)` block so phones get single-column layouts, scrollable tables,
  and a **hamburger ☰ → slide-out sidebar** (desktop keeps the fixed sidebar)
- An **Install app** button that appears when the browser allows installing
- A `?role=` deep-link for demos

Your original `Downloads/erp-demo (3).html` is untouched.
