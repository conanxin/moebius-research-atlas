# NOTICE-ASSETS.md — Visual Asset Source Attribution

Visual assets in `assets/public/` are **NOT** covered by either the MIT license (code) or CC BY 4.0 (research data). Each asset is attributed to its source as recorded in `data/public/public-assets.json` (fields: `source_path`, `public_path`, `sha256`, `display_section`).

## Source tiers

| Tier | Description | License note |
|---|---|---|
| `book_page_scan` | Local scans of published albums (e.g. <em>Le Cœur couronné</em>, <em>40 Jours dans le Désert B</em>, <em>The Art of Moebius</em>, <em>World of Edena</em>) | The original works remain under their original publishers' and authors' rights. The scan itself is a local reproduction for research use only. |
| `reproduction_page` | TAOM 1989 reproduction pages (from <em>The Art of Moebius</em>, Moebius Production, 1989) | Reproductions of pre-1989 works. The 1989 publication is the reproduction source. The original works remain under their original rights. |
| `site_harvest` | Images harvested from moebius.fr (artist's official site) | Used for research; source attribution preserved in metadata. |
| `catalog_render` | Catalog-rendered images from auction PDFs (S018, S019) | Renders of catalog pages; the underlying catalog descriptions are reproduced under fair-use research citation. |
| `derived_board` | Research diagrams (`review/studies/*.jpg`) | These are research visualizations created by this project; they may be reproduced under CC BY 4.0 alongside other research data. |

## How to find a specific asset's source

Every asset in `assets/public/` is registered in `data/public/public-assets.json` with at least:

- `asset_id`
- `source_path` (path in the local archive, e.g. `raw/books/1992_coeur_couronne_t1/pages/c1_03.jpg`)
- `public_path` (path in `assets/public/`)
- `sha256` (first 16 chars in the public JSON; full in CSV)
- `display_section` (which Research Atlas section uses it)
- `caption_status` (e.g. `IDENTITY_GATE_PASS · STORY_PAGE_VERIFIED`)

## Use of visual assets in derivative works

If you build on this archive, you must:

1. Check `data/public/public-assets.json` for each visual asset you reuse
2. Respect the original source's rights (publisher, artist estate, or institution)
3. Not present Mœbius's original artworks as your own work

The Research Atlas itself uses these assets only with explicit captions stating source tier and evidence status. See `research-atlas.html` for the in-page treatment.

## What is NOT in the public asset set

- All of `raw/` (the full local archive; many works remain confidential to the archive)
- Internal session transcripts
- Working notes that are not directly cited by a published claim
