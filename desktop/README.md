# Detangler Desktop

Electron wrapper that runs the Detangler web app as a native desktop application.

## What it does

Opens the deployed Detangler web app (`mikellemon-workspace.replit.app`) in a native desktop window — no browser chrome, Start menu shortcut, proper app icon.

## Building locally (requires a Windows/Mac/Linux machine)

```bash
cd desktop
npm install
npm run build:win    # Windows .exe installer
npm run build:mac    # macOS .dmg
npm run build:linux  # Linux AppImage
```

Output goes to `desktop/dist/`.

## Building via GitHub Actions (recommended)

Push this repo to GitHub, then either:

**Option A — Push a version tag to trigger a release:**
```bash
git tag v1.0.0
git push origin v1.0.0
```
GitHub Actions builds all three platforms and creates a GitHub Release with download links.

**Option B — Manual trigger:**
Go to your GitHub repo → Actions → "Build Desktop App" → Run workflow.

## Changing the URL

If your deployed URL changes, edit `desktop/main.js` line 3:
```js
const APP_URL = "https://mikellemon-workspace.replit.app";
```

## Adding a custom icon

Place your icon files in `desktop/build/`:
- `icon.ico` — Windows (256×256 recommended)
- `icon.icns` — macOS
- `icon.png` — Linux (512×512 recommended)

Online converters like [icoconvert.com](https://icoconvert.com) can convert a PNG to .ico.
