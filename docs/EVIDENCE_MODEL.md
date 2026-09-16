# Evidence Model

This archive distinguishes six types of visual evidence. Each claim must declare which types it rests on, and each visual asset must declare its type.

## The six types

### 1. ORIGINAL_ARTWORK

A direct scan of an original artwork (the actual ink, gouache, or print on paper).

- Strongest evidence tier.
- Requires the work to be the actual physical artwork, not a reproduction.

### 2. PUBLICATION_SCAN

A scan of a page from a published book / album / portfolio / magazine.

- The publication provides the canonical context.
- Evidence strength depends on whether the specific page can be matched to the work under study.
- Example: a specific page from <em>Le Cœur couronné</em> Vol.1 used as evidence for a claim about Vol.1.

### 3. REPRODUCTION_PAGE

A page from a later book that reproduces an earlier work.

- Example: TAOM 1989 (<em>The Art of Moebius</em>, Moebius Production) reproduces 1970s work.
- Lower trust than ORIGINAL or PUBLICATION_SCAN, because the reproduction adds a layer of editorial selection.
- Acceptable as visual evidence **with** explicit caption: "1989 reproduction from <em>The Art of Moebius</em>".

### 4. CATALOG_RENDER

A render of an auction-catalog page that depicts a work.

- Typically the render shows one work plus auction metadata (lot number, dimensions, estimate).
- Identity can be confirmed at `SOURCE_IDENTIFIED` level (the work exists and is by Mœbius).
- Pixel-level matching to the original artwork is typically `PENDING`.
- Acceptable as evidence with explicit caption: `identity = SOURCE_IDENTIFIED · image_match_status = PENDING`.

### 5. DERIVED_BOARD

A research visualization created by this archive (typically a grid / timeline / comparison matrix).

- Used to summarize claims and counterexamples.
- Always captioned: "RESEARCH DERIVATIVE — research diagram, not original artwork".
- Useful for teaching and visual summaries, not as primary evidence for any work-specific claim.

### 6. TEXT_ONLY

No visual evidence available; the claim is supported by textual research records only.

- Used for cases where local raw scans do not exist.
- The Research Atlas uses TEXT_ONLY cards for *La Déviation*, *Le Bandard Fou*, *Garage Hermétique* (1970s works without local scans).

## Claim → evidence → limitation → verdict chain

Every published claim must declare:

1. **Claim** — what is asserted.
2. **Evidence** — which assets / works support it (with type labels).
3. **Limitation** — what the evidence does NOT establish.
4. **Verdict** — the status (LOCKED / SUPPORTED / PROJECT_LIMITED / etc.).

This chain is visible in `data/public/atlas-claims.json` and on the Research Atlas page.

## What is NOT visual evidence

- Web profile photos that crop one figure from a multi-figure page (without parent page context)
- Verso / signature / colophon pages presented as if they were plate fronts
- Contact sheets presented as if they were individual artworks
- Product / package montages presented as if they were individual artworks

These asset roles are tracked in `notes/ASSET_METADATA_SCHEMA.md` and adjudicated per file, not inherited from work records.
