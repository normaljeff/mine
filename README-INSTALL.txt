# Pitch to Legend — phone app package

This package wraps the original Pitch to Legend 2.0.1 game as an installable, offline-friendly Progressive Web App (PWA). The game logic is kept in `index.html`; the added manifest, icons, and service worker enable installation and offline loading.

## Important: first setup is required

A PWA must be served from an HTTPS website (or localhost) for Android/Chrome to install it and use its service worker. Opening `index.html` directly from a file manager will run the game in a browser, but will **not** enable proper PWA installation/offline caching.

## Easiest free setup with GitHub Pages

1. On your phone or computer, sign in to GitHub and create a new public repository, for example `pitch-to-legend`.
2. Upload **all** files and folders in this package. Keep `index.html`, `manifest.webmanifest`, and `sw.js` in the repository root; keep both icons inside the `icons` folder.
3. In the repository, open **Settings → Pages**. Set the deployment source to **Deploy from a branch**, select `main` and `/(root)`, then save.
4. Wait for GitHub Pages to publish the site. Open the published HTTPS address on your Android phone in Chrome.
5. Let the page finish loading while online. Open Chrome's menu and choose **Install app** or **Add to Home screen**.
6. Launch **Pitch to Legend** from the new home-screen icon. After the first successful load, the game shell can open offline. Career saves continue using the browser's local storage.

## Notes

- The game is still a web app installed to your home screen, not a native APK. It opens in its own app-like window and does not need an internet connection after it has cached successfully.
- Do not clear Chrome's site data if you want to keep the saved career. For safety, use the game's own save/export options if present before clearing browser data or changing browsers.
- If you update the game files later, the service worker cache version can be changed in `sw.js` to force a fresh cache.
