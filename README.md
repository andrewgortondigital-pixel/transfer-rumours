# Transfer Tracker

A Progressive Web App that lists the latest Premier League transfer rumours, ranked by
likelihood of happening.

## Hosting
The app is the static folder `app/`. It's deployed on Netlify, linked to this repo, so
every push redeploys automatically. See `netlify.toml` for the publish settings.

## Daily refresh
The rumour data lives in `app/index.html`. When it's refreshed, committing and pushing
the change triggers a new Netlify deploy automatically — no manual re-upload needed.

## Add to your iPhone
See `app/INSTALL.md`.
