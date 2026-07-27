# Get the Transfer Tracker on your iPhone

This folder is a **Progressive Web App (PWA)**. Once it's online, you add it to your
home screen and it behaves like a normal app — its own icon, full screen, works offline.
No App Store, no Apple Developer account, no review.

## What's in this folder
- `index.html` — the app
- `manifest.webmanifest` — app name, icon, colours
- `sw.js` — service worker (offline support)
- `icon-180/192/512/1024.png` — app icons

All four icon files, the manifest and `sw.js` must stay in the **same folder** as `index.html`.

---

## Step 1 — Put the folder online (one-time, ~2 minutes)

You need the folder served over HTTPS. Easiest free option:

**Netlify Drop** (no setup, no card)
1. Go to https://app.netlify.com/drop
2. Drag this whole `app` folder onto the page.
3. It gives you a URL like `https://something-random.netlify.app`. That's your app.
   (Free Netlify account lets you rename it to e.g. `andrew-transfers.netlify.app`.)

Other equally good free options: **GitHub Pages**, **Cloudflare Pages**, **Vercel**.
Any static host works — there's no server-side code.

## Step 2 — Add it to your home screen
1. Open the URL in **Safari** on your iPhone (must be Safari, not Chrome).
2. Tap the **Share** button (square with an arrow).
3. Tap **Add to Home Screen**.
4. Name it (e.g. "Transfers") and tap **Add**.

Done — tap the icon and it opens full screen like an app.

---

## Keeping it up to date
Claude refreshes the rumour data every morning and rewrites `index.html` in this folder.
For your phone app to pick up the new data, the folder needs to be **re-deployed** after each refresh:

- **Netlify/Vercel/Cloudflare:** connect the host to a GitHub repo containing this folder.
  Then ask Claude to push updates to the repo and the host redeploys automatically.
- **Manual:** just re-drag the folder onto Netlify Drop whenever you want the latest.

Ask Claude to "wire up auto-deploy for the transfer app" and it'll walk you through
connecting GitHub + Netlify so the daily refresh flows straight to your phone.

## Want the real App Store version later?
That needs a paid Apple Developer account ($99/yr), a backend that ingests and scores
rumours on its own, data licensing, and Apple's review (plus gambling-content rules if
betting odds are shown). The PWA above gives you ~90% of the experience for free.
