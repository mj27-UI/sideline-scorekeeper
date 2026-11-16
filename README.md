# Sideline Scorekeeper

Offline-first football scorekeeper PWA. No account, cloud database, analytics, external runtime libraries, or paid APIs.

## Features
- Stores player profiles, games, play events, and scoring rules in IndexedDB on this device.
- Tracks passing, rushing, receiving, interceptions, sacks, defensive touchdowns, and manual point adjustments.
- Calculates fantasy totals from the play log, so editing, deleting, or undoing a play recalculates stats and scoreboard.
- Tracks two real-life team scores. A passing touchdown awards fantasy points to both passer and receiver but adds six to the team score only once.
- Includes game history, season leaderboard, editable scoring, and JSON backup/restore.
- Caches the app shell with a service worker for offline launch after first successful online load.

## Publish with GitHub Pages
1. Open repository **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/ (root)`, then Save.
4. Wait for deployment. The URL will be `https://mj27-UI.github.io/sideline-scorekeeper/`.

## Install on iPhone
1. Open the published URL in Safari while online.
2. Wait for the status to say **Offline ready**.
3. Tap **Share → Add to Home Screen**. Enable **Open as Web App** if shown, then Add.
4. Launch the Home Screen icon once while online.
5. Test Airplane Mode: open the app, add a temporary player and game, record a test play, close/reopen, and confirm the data remains.

## Important data notes
- Game data is local to this browser/app installation. It does not sync to another phone.
- Export a JSON backup regularly from **More → Settings → Export backup**.
- Importing a backup replaces current local app data after confirmation.
- Clearing Safari website data or removing app data can remove the local database. Keep backups somewhere safe.
- When a new app version is published, open it while online first so the service worker can cache the updated files.

## Development
Run a local HTTP server; do not open `index.html` through `file://` because service workers require HTTPS or localhost.

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.