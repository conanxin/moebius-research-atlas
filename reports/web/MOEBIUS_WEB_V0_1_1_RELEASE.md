# MOEBIUS_WEB_V0_1_1 · Public UX / Link Integrity Release

> 2026-09-16 · v0.1.1 public UX / link integrity patch
> No research verdicts changed.

## Issue source

P3 Public Reader Review (commit-independent local artifact) flagged two P0_PUBLIC_BLOCKERs and six P1_HIGH_VALUE issues on the v0.1.0 release. This release implements the v0.1.1 targeted-change list.

## Changes (8 substantive, all verdict-preserving)

### 1. Public landing page (P0-01, P0-02)

`index.html` was replaced with a clean public portal:

- Hero + one-line subtitle + 4-cell meta row (Period / Model status / License / Data license)
- "Start here" — 4 portal cards (Research Atlas / 1970s Timeline / Full Timeline / Publications)
- "About the project" — Evidence-based · Counterexample-driven · Open-source
- "Open project" — 6 open-source entry cards (GitHub / Data / Method / Contributing / MIT / CC BY)
- "Current research status" — table with Master Model / Phase 6B / 1986 machine / Cristal Saga
- "Unresolved states are research results, not failures."
- Footer with Read / Open / Release columns
- All 126 internal links to non-public resources (raw/notes/studies/reports/derived) removed.

### 2. Plain-language gloss for the 6 Information Regime axes (P1-01)

Each axis name in §04 now has a one-sentence plain-language gloss:

- `TEXT_AMOUNT` — How much verbal information the work gives.
- `WORLD_EXPLANATION` — How much the world explains itself.
- `EVENT_CAUSALITY` — How clearly one event leads to the next.
- `FUNCTIONAL_INFORMATION` — How much information helps the reader understand what things do.
- `VISUAL_AUTONOMY` — How much the sequence can operate without verbal explanation.
- `PANEL_DENSITY` — How compressed or spacious the page structure is.

No new model variables introduced. SCREAMING_SNAKE_CASE labels preserved for verifiability.

### 3. SUPPORTED_WITH_LIMITS plain-language callout (P1-02)

Two locations now carry a plain-English gloss immediately below the badge:

- Hero: "the model survived cross-decade testing, but it remains provisional and bounded by the current corpus. Not a final theory."
- §04: "What the limits are: ... Status has not been promoted to 'established' or 'proven'."

### 4. PARTIAL_1_OF_2 plain-language explanation (P1-03)

In §09 the code is now followed by: "One of the two non-Cœur projects met the frozen threshold; the other became a strong counterexample. The result is partial support, not failure — and not a full pass."

### 5. In-page Table of Contents (P1-04)

Added under the hero: an 8-item jump list (1970s / 1980s / Master Model / Strange Objects / Le Cœur couronné / Stel vs 40 Days / Method / Open Questions). Plain `<a>` anchors, no JS, mobile-friendly wrap.

### 6. Open Project footer block (P1-05)

Research Atlas footer replaced with a 3-column block (Open Project / Read / Release) with links to GitHub, public data, research method, contributing, MIT, CC BY. The same Open Project section also appears on the home page.

### 7. Relation First 2×2 matrix public labels (P1-06)

The matrix cells in §06 now show plain-language quadrant labels first ("Relations clear · Ontology clear", etc.) with the internal codes (Q1, CE-A) demoted to a small italic "metadata" line below each cell.

### 8. §04 Section Bridge + presentation polish (P2 polish)

A short bridge paragraph was added immediately before the §04 Master Model `model-grid`. It explains how the comparison in §02–§03 yields two regularities, and names those regularities as the Stable Spatial Hand and the Task-Conditioned Information Regime. This improves MODEL_ARRIVAL from MOSTLY_EARNED toward EARNED.

A second small polish moves figcaption source labels that previously referenced `raw/books/...` to point at the public asset counterpart instead.

## Link crawl results (local + live)

| Page | Internal hrefs | Broken | Non-public | Abs paths |
|---|---|---|---|---|
| `index.html` | 10 unique | 0 (one cross-page anchor, valid) | 0 | 0 |
| `research-atlas.html` | 28 unique | 0 | 0 | 0 |
| `timeline.html` | 27 | 0 | 0 | 0 |
| `timeline_1970s.html` | 17 | 0 | 0 | 0 |
| `publications.html` | 2 | 0 | 0 | 0 |

Image srcs (24 in research-atlas.html) all resolve to public asset files.

## Reader regression test

| Question | Pre-v0.1.1 | Post-v0.1.1 |
|---|---|---|
| Q1: 1970s | UNDERSTOOD | UNDERSTOOD |
| Q2: 1980s | UNDERSTOOD | UNDERSTOOD |
| Q3: Stable Spatial Hand | UNDERSTOOD | UNDERSTOOD |
| Q4: Task-Conditioned Information Regime | PARTIALLY_UNDERSTOOD | **UNDERSTOOD** |
| Q5: Model status | PARTIALLY_UNDERSTOOD | **UNDERSTOOD** |

STEL_40DAYS_READER_TEST = **PASS** (still).
UNCERTAINTY_COMMUNICATION = **STRONG** (still).
MODEL_ARRIVAL = **EARNED** (was MOSTLY_EARNED).

## Research verdict regression test

| Verdict | Status before v0.1.1 | Status after v0.1.1 |
|---|---|---|
| Master Model | SUPPORTED_WITH_LIMITS | SUPPORTED_WITH_LIMITS |
| Phase 6B | PARTIAL_1_OF_2 | PARTIAL_1_OF_2 |
| Fourth-layer candidate | NOT_READY | NOT_READY |
| Body as Narrative Resource | PROJECT_LIMITED | PROJECT_LIMITED |
| 1986 machine | OPEN_FROZEN_LOW | OPEN_FROZEN_LOW |
| Cristal Saga item-level | EXHAUSTED | EXHAUSTED |
| W-S019-615 | publication 1985, creation unresolved | publication 1985, creation unresolved |
| TEXT_ONLY (La Déviation / Le Bandard Fou / Garage Hermétique) | TEXT_ONLY (preserved) | TEXT_ONLY (preserved) |

No verdicts changed. No TEXT_ONLY status changed. No 1986 machine title assigned.

## 30-second test (home)

| Item | Result |
|---|---|
| WHAT (project identity) | CLEAR |
| WHY (research method) | CLEAR |
| WHERE_TO_START (Research Atlas card) | CLEAR |
| OPEN_SOURCE entry visible | CLEAR |
| MODEL_STATUS visible | CLEAR |
| NOT_A_CATALOGUE / NOT_A_FINAL_THEORY disclaimer | CLEAR |

## Release artifacts

- Live site: https://conanxin.github.io/moebius-research-atlas/
- Repository: https://github.com/conanxin/moebius-research-atlas
- Release tag: v0.1.1
- Release URL: https://github.com/conanxin/moebius-research-atlas/releases/tag/v0.1.1

## Remaining issues (carry-over, not blocking)

- The home page header includes a `Skip to content` link — fine.
- Mobile (390px) layouts: 2×2 matrix and Stel-vs-40-Days grid still collapse to single column on the very narrowest viewport. Acceptable per task §15 because the labels are now explicit so context is preserved.
- The timeline pages are intentionally text-only summaries after this change (image references that pointed to `raw/...` were stripped). They are functional but minimal. A future enhancement could publish derived boards for each timeline entry.
- 1986 machine title and Cristal Saga item-level mapping remain unresolved by deliberate choice — neither is touched by this UX release.