# MLB Matchup Predictor — two design versions

A **single, static GitHub Pages site** with two live versions of Ryan's MLB team matchup predictor. Both versions use the same model-derived `scores.js` file.

## Links after publishing

For a repository named `mlb-predictor` belonging to GitHub user `YOUR_USERNAME`:

- Comparison / selection page: `https://YOUR_USERNAME.github.io/mlb-predictor/`
- **Version 1 (dark dashboard):** `https://YOUR_USERNAME.github.io/mlb-predictor/v1/`
- **Version 2 (editorial):** `https://YOUR_USERNAME.github.io/mlb-predictor/v2/`

Replace `YOUR_USERNAME` with the account that currently owns the repository. After transferring the repository to Ryan, use Ryan's username in those links.

## Publish / update an existing repository

1. Copy **the contents** of this folder into the root of your existing local Git repository (not the folder itself). If prompted, overwrite `index.html`, `scores.js`, and `README.md`. Leave the `.git` folder alone.
2. In VS Code PowerShell terminal, from that repository directory:

   ```powershell
   git status --short
   git add -A
   git commit -m "Add two live design versions"
   git push
   ```

3. On GitHub, open your repository → **Settings → Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, **Branch** to `main`, **Folder** to `/(root)`, then Save. If Pages is already configured this way, nothing further is needed.
4. Open the three URLs above, **using the owner of the repo**.

For a **new repository**, publish an empty `mlb-predictor` repository first, extract the folder, then run `git init`, `git add -A`, `git commit`, `git branch -M main`, `git remote add origin ...`, `git push -u origin main`.

## How it works

```text
index.html       review landing page (links to both versions)
v1/index.html    original dark dashboard
v2/index.html    refined light/editorial version
scores.js        shared, precomputed team-strength scores
build_scores.py  produces scores.js from supplied source data
assets/          static preview screenshots for landing page
source/          Ryan's original notebook and CSV inputs
.nojekyll        prevents unneeded Jekyll processing
```

The pages under `/v1/` and `/v2/` each load `../scores.js` from the repo root, so both use **identical** prediction data. No Python server, API, or paid hosting needed.

If you regenerate scores from the supplied source data, run `python build_scores.py` in the repository root, commit the updated `scores.js`, and both live versions update together.

## Accuracy and attribution

This project's model calculates weighted scores from batting and pitching statistics (55% offense, 45% pitching). The head-to-head percentages are **relative model score shares**, not validated probabilities of winning games. Attribute the original model and notebook to Ryan; website implementation assistance should be credited separately if appropriate. Confirm Ryan consents before publicly publishing any source material.

## Repository transfer

You can build and deploy under your own account, then transfer the entire repository to Ryan in **Settings → General → Danger Zone → Transfer ownership**. After the transfer, GitHub Pages URLs are based on Ryan's account. Verify and re-share the new URLs because the old Pages URLs may not redirect.
