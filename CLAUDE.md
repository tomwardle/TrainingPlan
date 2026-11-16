# Service worker cache version

This is a PWA with a hand-written service worker ([sw.js](sw.js)) that caches files cache-first. Installed phones only pick up changes when the cache name changes.

Every time you change any cached file (index.html, manifest.webmanifest, icons, sw.js), bump the `CACHE` constant at the top of sw.js to the next semantic version (MAJOR.MINOR.PATCH), e.g. `Training-v0.0.1` -> `Training-v0.0.2`. Do this in the same edit, without being asked.

- PATCH: fixes and small tweaks.
- MINOR: new features (e.g. adding a nav item or page).
- MAJOR: breaking or major redesigns. Stay on 0.x.x until the first real release.

Also keep the `?v=` on the manifest link in index.html matching the same version, so Chrome re-fetches the manifest.

If you add a new file the app needs offline, also add it to the `ASSETS` list in sw.js.
