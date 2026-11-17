# Prompt for enriching this data later

Paste the prompt below into a new Claude chat and attach `pitches.csv` and `index.html` from this repository. Fill in the part marked **WHAT TO ADD** first.

---

I have a Shark Tank India pitch explorer hosted on GitHub Pages. I've attached two files:

- `pitches.csv`: the data sheet, one row per pitch (759 rows, Seasons 1 to 5). Columns: `sr_no`, `season`, `episode`, `company_name`, `brand_name`, `website`, `founders`, `founder_linkedin`, `category`, `deal_secured`, `source_url`. Founders and LinkedIn links are separated by "; " and line up by position. "LinkedIn profile not found" and "Website not found" mean the source had nothing.
- `index.html`: the whole site. The data is embedded as JSON inside `<script id="data" type="application/json">`, and each row there also has a `season_no` number (1 to 5) worked out from `season`.

The site is one light, white page in a single system font with soft pastel highlights and four tabs:
- **Pitches:** season buttons with counts (All seasons, Season 1 to 5), a search box, a Filters panel (category and deal outcome), grey summary tiles ("In this list", "Matching now") and clickable tiles (Deal secured, No deal), a sortable table with 50 rows per page, and a detail strip that opens when a row is clicked.
- **Analytics:** four stat tiles, then cards for pitches and deals by season, deal rate by category, pitches by category and season (with % share per season), and total pitches and deals closed by category.
- **README** and **Sources:** plain explanations built from the repository's own files.

Colours: Deal secured = green, No deal = grey, a single series = blue. Hover boxes show on tiles, headings, badges, bars and links.

**WHAT TO ADD:** [for example: valuation asked, equity offered, deal amount, deal valuation, sharks who invested, episode air date, company city, founder gender. Say where the new data comes from, or attach it.]

Please:

1. Add the new columns to `pitches.csv`, keeping every existing column and `sr_no` unchanged. Leave a cell blank when you don't know the value. Don't guess or invent values, and tell me which rows are missing data and why.
2. Run a sanity check before building: same row count, no duplicate company within a season, and no existing value changed.
3. Regenerate `index.html` with the new data in the embedded JSON block. Show the new columns in the Pitches tab and in each row's detail strip, and keep sorting, search and filters working on them.
4. Add analytics that use the new columns (for example average valuation by category and season, or deals by shark), as separate tables or charts. Keep each table about one thing, with column headings centred over their numbers.
5. Keep the existing look and behaviour. Before giving the files back, test the page with all rows and tell me the counts you see for the old columns (759 pitches; 122, 169, 157, 156 and 155 across Seasons 1 to 5; 433 deals secured and 326 no deal).
6. Return the updated `pitches.csv` and `index.html`, and tell me which files to upload to GitHub.

---
