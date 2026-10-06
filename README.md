# Connecticut Benefits Tracker — simple edition

A static dashboard comparing municipal SNAP and selected Medicaid assistance-category counts against July 2025. Includes a program toggle, municipality and month selectors, three indicators, a clickable map and monthly chart.

**Working draft:** a generic CT draft logo incorporating “some research / some action.” No real organization logo or personal author names are included.

## Publish on GitHub Pages

1. Create a new **public** GitHub repository (for example, `benefits-tracker`).
2. Extract this package. Upload the **contents** of this folder to the repository root, with `index.html` at the top level. Include `.github/workflows/pages.yml` if using the workflow below. Do not upload only the ZIP.
3. Open **Settings → Pages**. Under **Build and deployment**, select **GitHub Actions** as the source.
4. Open **Actions → Publish GitHub Pages → Run workflow**, choosing `main`. Future pushes to `main` deploy automatically.
5. When the workflow completes, find the public link under **Settings → Pages** or in the deployment result.

If you cannot upload hidden folders, use the simpler alternative: under Settings → Pages select **Deploy from a branch**, choose `main` and **/(root)**, and save. The site has no build step. Use one publishing method, not both.

GitHub documentation: https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages

No API keys, package installation, database or paid hosting service is required. Relative asset links support repository Pages URLs as well as a custom domain. No repository has been created or published by preparing this package.

## Local use

Open `index.html` in a browser. All data and map geometry are bundled; the site requires no network calls to render. Source links require internet access. The separate standalone HTML deliverable contains the same site in one file.

## Files

- `index.html`: layout, draft wordmark and concise explanation.
- `style.css`: blue/burgundy styling using system fonts; no external font dependencies.
- `app.js`: filters, map, chart and calculations.
- `data.js`: saved enrollment snapshot and municipal boundaries.
- `favicon.svg`: generic chart icon.
- `METHODOLOGY.md`: category scope, formulas, sources and limitations.
- `.github/workflows/pages.yml`: optional automatic GitHub Pages deployment.

## Data freshness

Latest reporting month: **August 2026**. Source data updated **September 11, 2026**. Downloaded September 28, 2026, Eastern time. This is a fixed snapshot, not a live feed. Redeploying the site does not retrieve newer data.

To update, obtain the DSS source data and metadata, aggregate the same included categories by month and town as documented in METHODOLOGY.md, and replace the `data`, `months`, and `updated` fields in `data.js`. Preserve the July 2025 baseline, town names, geometry and program keys. Validate all 169 town/program/month combinations and independently reconcile totals before publishing. Update the snapshot dates in this README, index.html and METHODOLOGY.md. New categories require an explicit methodology review.

## Editing

Change the draft name and placeholder in `index.html`. Colors and layout live in `style.css`. Do not relabel category totals as unique people or law-attributable losses without additional evidence. The original detailed dashboard remains a separate file outside this repository package.

## Attribution and licensing

Public-source data and map provenance are documented in METHODOLOGY.md. Source material retains its applicable terms; public availability does not itself grant a blanket license. No open-source license is assigned to the custom code in this package; the owner can choose one before accepting third-party reuse. System fonts avoid redistributed font assets.


District views are included for State House, State Senate, and Congress. Choose Geography, then a district on the map or in the menu. District totals are population-weighted estimates; see METHODOLOGY.md and allocation-audit.json. Upload districts.js alongside data.js when hosting. All geometry and allocations are bundled for offline use.
