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

## Tech

- React 18 + ReactDOM (UMD) and Babel Standalone, loaded from CDN
- SheetJS (`xlsx`) for Excel import
- `html2canvas` for PNG report generation
- Firebase Firestore for cloud sync
