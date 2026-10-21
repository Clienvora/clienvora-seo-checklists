# Clienvora SEO Checklist Library

The complete free SEO checklist library as open data. **1,637 checks** across **101 checklists** and **4 disciplines**, released under CC BY 4.0.

Every check on clienvora.com/checklists/ is in this repository, in the same structure it appears on the site: a title, a short explanation where the page gives one, and the discipline and checklist it belongs to.

## Why this exists

Most SEO checklists are a PDF you cannot search, a spreadsheet someone made in 2019, or a page that hides half its content behind a form. This one is open, structured, and generated from the live pages, so the numbers are not estimates.

| File | What it is |
| --- | --- |
| `seo-checklist-library.pdf` | The whole library, printable. 110 pages, A4, tick boxes, grouped by discipline. |
| `seo-checklist-library.xlsx` | The same rows with a Status and an Owner column, for tracking a team through an audit. Opens in Google Sheets. |
| `seo-checklist-library.csv` | The same rows as CSV, for scripts and other tools. |
| `checklist-catalogue.json` | The catalogue: every checklist, its discipline, its URL, and its check count. |

## What is in it

| Discipline | Checklists | Checks |
| --- | --- | --- |
| Technical SEO | 311 | 1 |
| On-Page SEO | 447 | 1 |
| Off-Page SEO | 319 | 1 |
| Local SEO | 560 | 1 |
| **Total** | **101** | **1,637** |

## How each check is written

Every row on the site carries three things, and the site has a rule that none of them are optional:

1. **The tool that finds the problem.** A named report in a named tool, not a general instruction.
2. **The action that fixes it.** With code where code helps, for example a redirect rule or a canonical tag.
3. **The proof that the fix landed.** The command, the report, or the URL to re-check.

A check that cannot be verified is a check that cannot be repeated, and a check that cannot be repeated is the one that gets skipped in month two. That is why the detail column is empty on some rows and long on others.

## How this was generated

The counts are read from the pages, not typed by hand. `scripts/checklist_extract.py` in the clienvora.com repository parses each checklist page, finds the checks using whichever of the three markup templates that page uses, and writes both this repository's files and the catalogue that the website renders. The PDF and the spreadsheet come from the same extraction pass, so they cannot disagree with each other or with the site.

Every page that carries a check count reads it from `checklist-catalogue.json`, so the number published on the website and the number of rows in the spreadsheet are the same number.

## Data quality notes

- One page in the library, the SEO tools comparison, is a comparison table rather than a list of checks, so it contributes zero rows. The library has 101 checklists and 1,637 checks from 4 of them.
- The `Detail` column is empty wherever the source page shows a check title without a supporting paragraph. That is a property of the source, not a gap in the export.
- Positions in `checklist-catalogue.json` are the order the checks appear on the page, so a check that moves on the site moves here too.

## Using it

Attribution is not required, but if you publish the data or a derivative, a line like this is appreciated:

> SEO checklist data from Clienvora, 101 checklists and 1,637 checks, licensed under CC BY 4.0. Source: https://www.clienvora.com/checklists/

## Citation

See `CITATION.cff`. A plain-text form:

```
Clienvora. (2026). Clienvora SEO Checklist Library (Version 2026-10-21) [Data set]. https://github.com/Clienvora/clienvora-seo-checklists
```

## The live library

The interactive version, where progress is saved in your browser and each checklist is its own page with the full explanation, is at https://www.clienvora.com/checklists/

## License

CC BY 4.0. See `LICENSE`.
