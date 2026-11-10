# API bajo presión

A Spanish-language, room-based classroom minigame about API attack surfaces and defense in depth. Students join from their phones; the host view displays votes live.

## Firebase setup

The game uses Firebase Authentication with anonymous sign-in and Realtime Database. It is configured for project `presentacion-d0a1f`; the client configuration is in `firebase-config.js`, and database rules are in `database.rules.json`.

The browser config is public by design. The database rules restrict room updates to the host and allow joined players to submit one vote per round. Do not switch the database to public read/write test rules.

## Run locally

Serve over HTTP because the Firebase SDK uses JavaScript modules:

```sh
python3 -m http.server 8000
```

Open `http://localhost:8000`. Firebase must be configured for multiplayer rooms to work.

## Deploy

GitHub Actions deploys the static site to GitHub Pages whenever a commit is pushed to `main`.
