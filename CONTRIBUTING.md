# Contributing

This archive values evidence-led corrections over volume of additions.

## Allowed contributions

- **Metadata corrections** — typos in work cards, broken source links, ISBN fixes, etc.
- **Bibliographic sources** — additional independent sources that confirm or expand a work's record (e.g. library catalog entries, archive catalog URLs, museum records).
- **Source identification** — when an asset currently marked UNRESOLVED / CANDIDATE / SOURCE_IDENTIFIED can be advanced with independent evidence.
- **Asset lineage** — corrections to `data/public/public-assets.json` (file → source mapping, asset_role classification, sha256 verification).
- **UI / accessibility** — HTML / CSS / JS fixes for keyboard navigation, screen reader compatibility, contrast, mobile responsiveness.
- **Research evidence proposals** — a new piece of evidence that supports or refutes an existing claim (without changing the claim's verdict unilaterally).

## Submission structure

For research-related contributions, use this template:

```
CLAIM:        [which claim from data/public/atlas-claims.json]
PROPOSED CHANGE:  [what you want to add / modify]
SOURCE:       [the independent source — URL, ISBN, library code, etc.]
EVIDENCE:     [the actual evidence — quote, image, file, etc.]
CONFIDENCE:   [your assessment: SOURCE_IDENTIFIED / CROSSCHECKED / VERIFIED]
AFFECTED RECORD: [which work_id / asset_id / claim_id this affects]
```

## Core discipline

**Contributions MUST NOT automatically override:**

- **CONFIRMED** (e.g. signed-date art record)
- **LOCKED** (e.g. 1970s First Pass Lock — `studies/1970S_FIRST_PASS_LOCK.md`)
- **CURRENT VERDICT** (e.g. `SUPPORTED_WITH_LIMITS`, `PROJECT_LIMITED`, `OPEN_FROZEN_LOW`)

If your contribution conflicts with a locked verdict, your contribution enters as **PROPOSED / UNVERIFIED** and waits for an explicit research round (Phase N) to re-open the verdict.

## Asset additions

When proposing a new visual asset:

1. The asset must have a **source_path** under `raw/` or `assets/public/`
2. `asset_role` must be explicitly stated (INDIVIDUAL_PLATE_FRONT / CONTACT_SHEET / COVER / etc. — see `notes/ASSET_METADATA_SCHEMA.md`)
3. `sha256` must be recorded
4. **Provenance** must be traceable — auction catalog, library record, museum archive, or local scan of a known publication
5. **identity_status** must be classified: SOURCE_IDENTIFIED / CROSSCHECKED / VERIFIED (definitions: `notes/LEAD-1986-MACHINE-001.md`)

## What this project is NOT open to

- Wholesale downloads of any third-party archive without source provenance
- "Filling in" unresolved metadata (titles, years, attributions) without independent evidence
- Downgrading or upgrading any current verdict to suit a presentational goal
- Silent edits to lock files (`studies/*_LOCK.md`, `studies/CROSS_DECADE_MODEL_LOCK.md`, etc.)
