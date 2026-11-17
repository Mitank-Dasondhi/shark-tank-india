# Shark Tank India: Pitch Explorer

A single-page explorer for all 759 pitches from Seasons 1–5.

- **Pitches tab:** every pitch with serial number, season, episode, company, brand, founders, founder LinkedIn, website, category, deal outcome and pitch page. Season buttons, search, a Filters panel (category and deal outcome), sorting, paging, and a click-to-open detail strip for each row.
- **Analytics tab:** headline numbers, pitches and deals by season, deal rate by category, pitches by category and season (with % share per season), and total pitches and deals closed by category. Everything follows the season buttons, search and filters.
- **README and Sources tabs:** what the page shows, where the data comes from, and what each column means.

Files in this repository:

- `index.html`: the whole site. The data is built into it, so there is no build step and no server.
- `pitches.csv`: the data sheet, one row per pitch, with a serial number added.
- `NEXT_PROMPT.md`: a prompt to paste into Claude later to enrich the data (valuations, sharks, and so on) and rebuild the site.
- `README.md`: this file.

## Publish on GitHub Pages

1. On GitHub, create a new **public** repository (for example `shark-tank-india-explorer`). Do not tick "Add a README file", because this repository already has one.
2. Upload all four files to the top level of the repository (Add file, then Upload files, then Commit changes).
3. Go to **Settings, then Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose the **main** branch and the **/ (root)** folder, and click **Save**.
4. After a minute or two the site is live at `https://<your-username>.github.io/<repository-name>/`.

## Notes

- The source files have no valuation, ask or investor columns, so the analytics cover counts and deal rates only.
- The "Other" category is the label used in the source files. It is not defined anywhere in the data.
- To update the data later, use `NEXT_PROMPT.md`. It rebuilds `index.html` from an updated `pitches.csv`.
