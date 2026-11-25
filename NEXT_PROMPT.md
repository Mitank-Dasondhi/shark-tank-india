# Prompt for enriching this data later

Paste the prompt below into a new Claude chat and attach `pitches.csv` and `index.html` from this repository. Fill in the part marked **WHAT TO ADD** first.

---

I have a Shark Tank pitch explorer for India, Australia and the US, hosted on GitHub Pages. I've attached two files:

- `pitches.csv`: the data sheet, one row per pitch (2,584 rows). Columns: `country`, `sr_no`, `season`, `season_no`, `episode`, `company_name`, `brand_name`, `founders`, `founder_linkedin`, `website`, `category`, `category_original`, `deal_secured`, `source_url`. `sr_no` restarts at 1 for each country. `category_original` is the label from the source files, and `category` is the label the site uses (the source's "Other" was re-sorted into new categories). Founders and LinkedIn links are separated by "; " and line up by position. "LinkedIn profile not found" and "Website not found" mean the source had nothing.
- `index.html`: the whole site. The data is embedded as JSON inside `<script id="data" type="application/json">`. Each row there has the same fields as the CSV plus a `uid` (a running number from 1 to 2,584 across all countries, used to track which row is open).

The site is one light, white page in a single system font with soft pastel highlights and four tabs:
- **Pitches:** a Country drop-down and a Season drop-down (the season list follows the country), a search box, a Filters panel (category and deal outcome), grey summary tiles ("In this list", "Matching now") and clickable tiles (Deal secured, No deal), a sortable table with 50 rows per page, and a detail strip that opens when a row is clicked.
- **Analytics:** four stat tiles, then four sections: pitches and deals by season, deal rate by category, pitches by category and season (with % share per season), and total pitches and deals closed by category. Each section has a Graph / Numbers switch (deal rate by category also has a Pie). Long category lists show the biggest six first with a "Show all" button.
- **README** and **Sources:** plain explanations built from the data, and they change with the country.

Colours: Deal secured = green, No deal = grey, a single series = blue, categories in the pie and stacked columns use the first seven colours plus grey for the rest. Hover boxes show on tiles, headings, badges, bars and links.

**WHAT TO ADD:** [for example: valuation asked, equity offered, deal amount, deal valuation, sharks who invested, episode air date, company city, founder gender, or fixing a category. Say where the new data comes from, or attach it.]

Please:

1. Add the new columns to `pitches.csv`, keeping every existing column, `sr_no` and `category_original` unchanged. Leave a cell blank when you don't know the value. Don't guess or invent values, and tell me which rows are missing data and why.
2. Run a sanity check before building: same row count per country, no duplicate company within a season, and no existing value changed (except any category I asked you to fix).
3. Regenerate `index.html` with the new data in the embedded JSON block. Show the new columns in the Pitches tab and in each row's detail strip, and keep sorting, search, filters and the country and season drop-downs working on them.
4. Add analytics that use the new columns (for example average valuation by category and season, or deals by shark), as separate sections with the same Graph / Numbers switch. Keep each table about one thing, with column headings centred over their numbers.
5. Keep the existing look and behaviour. Before giving the files back, test the page with all rows and tell me the counts you see for the old columns: India 759 pitches (122, 169, 157, 156, 155 across Seasons 1 to 5; 433 deals secured, 326 no deal); Australia 284 pitches (63, 51, 51, 51, 35, 33 across Seasons 1 to 6; 155 and 129); US 1,541 pitches (Seasons 1 to 18: 64, 36, 60, 103, 116, 116, 116, 96, 96, 92, 96, 100, 96, 87, 87, 80, 72, 28; 956 and 585).
6. Return the updated `pitches.csv` and `index.html`, and tell me which files to upload to GitHub.

---
