# Shark Tank: Pitch Explorer

An analysis of Shark Tank pitches from three geographies: India, the US and Australia (2,584 pitches in total). It shows how many pitches ended in a deal, how many did not, and which category each pitch falls into. Together, this shows where investors have put their money across the whole Shark Tank journey. The data counts pitches and deal outcomes; it does not include the amounts invested.

| Geography | Pitches | Seasons | Deals secured | No deal |
|---|---|---|---|---|
| India | 759 | 1–5 | 433 | 326 |
| Australia | 284 | 1–6 | 155 | 129 |
| US | 1,541 | 1–18 | 956 | 585 |

## What is on the page

- **Country and Season drop-downs** at the top. Everything on the page follows them.
- **Pitches tab:** every pitch with serial number, season, episode, company, brand, founders, founder LinkedIn, website, category, deal outcome and pitch page. Search, a Filters panel (category and deal outcome), sorting, paging and a click-to-open detail strip for each row.
- **Analytics tab:** headline numbers, pitches and deals by season, deal rate by category, pitches by category and season (with % share per season), and total pitches and deals closed by category. Each section has a Graph / Numbers switch (the deal rate section also has a Pie). Long category lists show the biggest six first, with a "Show all" button.
- **README and Sources tabs:** what the page shows, where the data comes from, and what each column means.

## Files in this repository

- `index.html`: the whole site. The data is built into it, so there is no build step and no server.
- `pitches.csv`: the data sheet, one row per pitch (2,584 rows).
- `NEXT_PROMPT.md`: a prompt to paste into Claude later to enrich the data (valuations, sharks, and so on) and rebuild the site.
- `README.md`: this file.

## Data sheet columns

| Column | Meaning |
|---|---|
| country | India, Australia or United States |
| sr_no | Serial number, restarting at 1 for each country |
| season, season_no | Season label (for example "Season 3") and its number |
| episode | Episode number within the season |
| company_name, brand_name | The company and its brand |
| founders | Founder names, separated by "; " |
| founder_linkedin | One LinkedIn link per founder, separated by "; " and lined up with the founders by position |
| website | The company website |
| category | The category used on the site (see below) |
| category_original | The category exactly as it was in the source files |
| deal_secured | Yes if a deal was secured, No if not |
| source_url | The page the row came from |

"LinkedIn profile not found" and "Website not found" mean the source had nothing for that field.

## About the categories

The source files put 508 pitches in a catch-all category called "Other". 442 of them were moved into existing or new categories by reading the company name and website. The new categories are Pets, Sports & Outdoors, Kids, Baby & Toys, Entertainment & Events, Travel & Hospitality, Business & Services and Industrial & Cleantech. The remaining 66 stayed in "Other" because the name gave no clear clue. The `category_original` column keeps the source label for every row, and the site shows it in a row's detail strip when it was changed.

## Publish on GitHub Pages

1. Unzip the downloaded file on your computer. GitHub cannot unzip it for you.
2. On GitHub, create a new **public** repository (for example `shark-tank-explorer`). Do not tick "Add a README file", because this repository already has one.
3. Open the new repository, click **uploading an existing file** (or Add file, then Upload files), and drag in the **four files** (`index.html`, `pitches.csv`, `NEXT_PROMPT.md`, `README.md`). Drag the files, not the folder. Click **Commit changes**.
4. Go to **Settings, then Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose the **main** branch and the **/ (root)** folder, and click **Save**.
5. After a minute or two the site is live at `https://<your-username>.github.io/<repository-name>/`.

## Notes

- The source files have no valuation, ask or investor columns, so the analytics cover counts and deal rates only.
- Most founder LinkedIn entries in the US and Australia files read "not found".
- To update the data later, use `NEXT_PROMPT.md`.
