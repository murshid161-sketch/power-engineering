# Power Engineering

Universal DPR (Daily Progress Report) web application.

A single-page app (React via CDN + Babel standalone) for tracking construction
activity progress across segments and towers, with a to-do list, Excel import,
PNG report export, and Firebase-backed sync.

## Usage

Open `index.html` in a browser, or serve it statically:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

### GitHub Pages

This repo can be published with GitHub Pages (Settings → Pages → deploy from
branch `main`, root). The app will then be available at
`https://murshid161-sketch.github.io/power-engineering/`.

## Auto-update / cache busting

The page carries a `BUILD` string (in the inline `<script>` at the top of
`index.html`) and there is a matching `version.json` with the same `v` value.
On load the page fetches `version.json` (no-store) and, if the published `v`
differs from its own `BUILD`, it silently reloads the fresh copy with a
cache-busting `?v=` query — so users always end up on the latest version.

**On every deploy, bump BOTH to the same new value:**
- `index.html` → `var BUILD="...";`
- `version.json` → `{ "v": "..." }`

## Tech

- React 18 + ReactDOM (UMD) and Babel Standalone, loaded from CDN
- SheetJS (`xlsx`) for Excel import
- `html2canvas` for PNG report generation
- Firebase Firestore for cloud sync
