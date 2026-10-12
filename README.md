# Diamond Matchup — Editorial Light

A single-page, static MLB team matchup comparison site featuring Ryan's statistical scoring model.

## Site structure

- `index.html` — **the live homepage** at the root GitHub Pages URL; includes all layout and interaction code.
- `scores.js` — team score data generated from the provided CSVs.
- `build_scores.py` — reproducible Python script to regenerate `scores.js` (standard library only).
- `source/` — Ryan's original Jupyter notebook and supplied batting / pitching datasets.
- `.nojekyll` — keeps GitHub Pages serving the site as static files.

There are **no** `v1/`, `v2/`, or design-selection pages. This package is the complete V2-only repository content and should be extracted **directly into the repository root**, not into an extra subfolder.

## Publish on GitHub Pages

1. Push the files to the repository's default `main` branch.
2. In GitHub, open **Settings → Pages**.
3. Set **Source** = **Deploy from a branch**, **Branch** = `main`, **Folder** = `/(root)` and save.
4. The public site is at `https://YOUR_USERNAME.github.io/YOUR_REPOSITORY/` for an ordinary project repository.

## Recalculate the model data

```powershell
python .\build_scores.py
```

The website requires no backend, build tooling, or paid hosting. It works with the data snapshot in `scores.js`. The percentages shown are **relative normalized scoring shares**, not validated baseball win probabilities.

## Attribution and public sharing

The original model and notebook were developed by Ryan; the website was implemented with assistance. Obtain Ryan's approval before publishing the notebook/data publicly. GitHub Pages hosting from a public repo exposes its committed files.
