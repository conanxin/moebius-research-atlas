# Data Model

This archive stores four interlocking data types: **work**, **publication**, **asset**, **claim**, and **evidence**.

## work

A single artwork or piece of content authored by Mœbius (Jean Giraud). Examples:

- W-S019-613 — Le Monde d'Edena « Stel » planche 23
- W-LCC-VOL1 — Le Cœur couronné Vol.1 (1992)
- W-70S-LT-01 — The Long Tomorrow plate 1

Fields (minimum):

| Field | Description |
|---|---|
| `work_id` | Stable identifier |
| `title` | Authoritative title |
| `period` | Creation period (decade-level) |
| `year_creation` | Best-known creation year (may be unresolved) |
| `year_publication` | Publication year (if known) |
| `medium` | Material / technique |
| `dimensions` | Size |
| `signature_observed` | Whether signature / monogram is documented |
| `source_identified_by` | Catalog PDF or other primary source |
| `identity_status` | `SOURCE_IDENTIFIED` / `CROSSCHECKED` / `VERIFIED` |
| `image_match_status` | `PENDING` / `MATCHED` |
| `work_card_md` | Path to a detailed work card |

## publication

A book, album, or portfolio in which one or more works appear.

- `publication_id` (e.g. `PUB-LCC-VOL1`)
- `title` (with original-title)
- `publication_year` (verbatim from catalog)
- `publisher` · `country` · `language` · `ISBN` · `pages`
- `local_files` — paths to local scans of the publication
- `coverage_status` — `NONE` / `PARTIAL` / `FULL`

## asset

A visual file in the local archive (`raw/`, `assets/public/`, `derived/`).

- `asset_id` — unique identifier
- `local_path` — repository-relative path
- `sha256` — content hash (full or first 16 chars in public JSON)
- `asset_role` — `INDIVIDUAL_PLATE_FRONT` / `CONTACT_SHEET` / `COVER` / `PACKAGE` / `VERSO` / `SIGNATURE_PAGE` / `COLOPHON` / `PRODUCT_MONTAGE` / `MULTI_PLATE_PHOTO` / `CROP` / `THUMBNAIL` / `DERIVED_BOARD` (see `notes/ASSET_METADATA_SCHEMA.md`)
- `depicts_work_id` — which work the asset depicts (if known)
- `is_complete_artwork` / `is_multi_work_image` — boolean flags
- `canonical_for_visual_study` — `YES` / `NO` / `PENDING_REVIEW`
- `composition_complete` — `true` / `false` / `uncertain`

## claim

A falsifiable research statement with explicit scope and verdict.

- `claim_id` — unique identifier (e.g. `claim: BODY_AS_NARRATIVE_RESOURCE`)
- `title` — short title
- `statement` — full claim text
- `status` — `COMPLETE_AND_LOCKED` / `SUPPORTED` / `SUPPORTED_WITH_LIMITS` / `PROJECT_LIMITED` / `WORKING_MODEL_V0.1` / `OPEN_FROZEN_LOW` / `EXHAUSTED` / `NOT_READY` / etc.
- `scope` — applicable corpora
- `limitations` — explicit boundaries

## evidence

The chain connecting a claim to its supporting assets and works.

- `claim_id` → `work_id` → `asset_id` (via `evidence_role`)
- `evidence_role` — `PRIMARY` / `SECONDARY_BOARD` / `CATALOG_RENDER` / `TEXT_ONLY`

## Relationships

```
work  ←depicts←  asset
       ↑
   appears in ←   publication
       ↑
   supports  ←   evidence
       ↑
       claim
```

A claim is grounded in evidence; evidence links to assets; assets depict works; works appear in publications.

## Where data lives in this repo

- **Internal full data** (not for public release): `data/works.jsonl` · `data/assets.jsonl` · `data/publications_*.jsonl` · `data/artist_statements.jsonl`
- **Public data**: `data/public/atlas-works.json` · `data/public/atlas-claims.json` · `data/public/atlas-evidence.json` · `data/public/public-assets.json`
- **Work cards**: `notes/works/*.md`
- **Asset schema**: `notes/ASSET_METADATA_SCHEMA.md`
