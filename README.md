# Operator Gold Rush Overlay

Animated dashboard overlay for the collection ops dashboard.

## Files

- `digging-overlay-animated.html` - local preview and main source file.
- `operator-gold-rush-overlay.js` - Chrome console/local server overlay script.
- `operator-gold-rush-overlay-standalone.js` - large self-contained backup script with images embedded.
- `chrome-console-loader.js` - small script to paste into Chrome console.
- `build-operator-gold-rush-overlay.mjs` - rebuilds the generated overlay scripts from the HTML source.
- `operator-gold-rush-overlay-test.html` - local test page.
- `operation-gold-rush-assets/` - image assets used by the overlay.

## Run Locally

From this folder:

```bash
cd /Users/clifton.buckley/Documents/operator-gold-rush-overlay
python3 -m http.server 8765
```

Then open the work dashboard and paste this into Chrome console:

```js
(() => {
  const s = document.createElement("script");
  s.src = "http://127.0.0.1:8765/operator-gold-rush-overlay.js?v=" + Date.now();
  document.body.appendChild(s);
})();
```

## Update Names

The locker list is in `digging-overlay-animated.html` under:

```js
const lockerRoster = [
```

After changing the roster or overlay code, rebuild:

```bash
node build-operator-gold-rush-overlay.mjs
```

Then rerun the Chrome console loader.

## GitHub

Use this whole folder as the GitHub repo folder. Keep the repo private because the roster is work-related.
