# MOEBIUS_WEB_P2 · Open Source Release Report

> 2026-09-16 · First public release of the Mœbius Research Atlas

## Repository

| Field | Value |
|---|---|
| Repository | `conanxin/moebius-research-atlas` |
| Repository URL | https://github.com/conanxin/moebius-research-atlas |
| Visibility | **PUBLIC** |
| Default branch | **main** |
| Wiki | disabled |
| Issues | enabled |
| Topics | `moebius`, `jean-giraud`, `digital-humanities`, `art-research`, `visual-culture`, `digital-archive`, `research-atlas` |
| Homepage (set) | https://conanxin.github.io/moebius-research-atlas/ |
| Description | "An open digital research atlas of Mœbius: visual language, space, information regimes, evidence and counterexamples." |

## Release

| Field | Value |
|---|---|
| Tag | `v0.1.0` (annotated) |
| Tag commit | `3c43590610eb7741494e5609f9b3d95dd65999ba` |
| Tag object | `3daf952ea012e22a68e6a086b8e8ed7a8cb5eb3e` |
| Title | Mœbius Research Atlas v0.1.0 |
| GitHub Release URL | https://github.com/conanxin/moebius-research-atlas/releases/tag/v0.1.0 |
| Published | 2026-09-16T13:54:55Z |
| Target | `main` HEAD |

## Commit history (public)

```
3c43590 docs: add public repository and live atlas links
d8aa037 feat: include existing portal HTML in public release
7f5adfa feat: add open-source Mœbius Research Atlas
```

Note: the P1 local commit `51add62` was amended before push to (a) remove an accidentally-included cross-project doc (`docs/F5_F6A_INTERPRETATION_RECONCILIATION.md` from an adjacent MURAL_ATLAS project), (b) extend `.gitignore` to prevent re-tracking, and (c) add `.nojekyll`. The amended SHA is `7f5adfa`. This amendment happened before any public push, so the published history starts at `7f5adfa` and contains the corrected contents.

## GitHub Pages

| Field | Value |
|---|---|
| Configured | yes (REST API POST `/pages`) |
| Source branch | `main` |
| Source path | `/` (root) |
| Build type | legacy |
| Public | true |
| HTTPS enforced | true |
| URL | https://conanxin.github.io/moebius-research-atlas/ |
| Status at verification | **built** (rebuilt in 9s after the final commit) |

## HTTP smoke

All paths returned HTTP 200 with correct byte counts:

| Path | Status | Bytes | Content-Type |
|---|---|---|---|
| `/` | 200 | 82,952 | text/html |
| `/index.html` | 200 | 82,952 | text/html |
| `/research-atlas.html` | 200 | 23,955 | text/html |
| `/timeline_1970s.html` | 200 | 6,026 | text/html |
| `/timeline.html` | 200 | 19,399 | text/html |
| `/publications.html` | 200 | 14,325 | text/html |

## Online research-verdict smoke

All required status markers are present in the live Research Atlas:

- `SUPPORTED_WITH_LIMITS` — present
- `PARTIAL_1_OF_2` — present
- `OPEN_FROZEN_LOW` — present
- `EXHAUSTED` — present

All forbidden framing strings are absent:

- `ESTABLISHED THEORY` — absent
- `UNIVERSAL THEORY` — absent
- `FINAL MODEL` — absent

Section 08 (Counterexample · Stel vs 40 Days) renders with the lede: "Body visibility is not narrative causality." and the closing "Body visibility does not automatically equal narrative causality." The `≠` symbol appears three times in Section 09 (How the Research Works) — Case 01/02/03 method-failure lessons.

## Online asset smoke

7/7 sample assets served over HTTP:

| Asset | Bytes |
|---|---|
| `assets/public/1970s/taom_1989_reproduction/062_lt-01_AOM0013.jpg` | 626,240 |
| `assets/public/1980s/catalog_renders/052_s018_153_S018_p077_lot153_Moebius_Starwatcher-077.jpg` | 142,853 |
| `assets/public/1990s/coeur_v1/000_c1_03.jpg` | 143,544 |
| `assets/public/1990s/stel/024_woe_211.jpg` | 151,196 |
| `assets/public/1990s/40days/018_pg05.jpg` | 37,527 |
| `assets/public/research/042_RELATION_ONTOLOGY_2X2.jpg` | 398,750 |
| `assets/public/research/043_MOEBIUS_MODEL_COUNTEREXAMPLES.jpg` | 476,004 |

## Fresh clone smoke

`git clone --depth=1 https://github.com/conanxin/moebius-research-atlas.git` to `/tmp/moebius-research-atlas-smoke` succeeded (rc=0). Verified:

- `index.html` (82,952 bytes)
- `research-atlas.html` (23,955 bytes)
- `README.md` (6,285 bytes)
- `LICENSE` (1,085 bytes)
- `docs/RESEARCH_METHOD.md` (4,473 bytes)
- `assets/public/` (5 entries)
- `data/public/atlas-works.json` (9,834 bytes)
- `data/public/atlas-claims.json` (5,363 bytes)
- `data/public/atlas-evidence.json` (27,148 bytes)
- `.gitignore` (788 bytes)

Total files in clone: 148.

Clone was deleted after verification; no modifications made.

## Pre-publish tracked-file audit

Before pushing, all 115 tracked files were audited. Findings:

- No `raw/`, `private/`, `tmp/`, `cache/`, or `.hermes-runtime/` directories in tracked set.
- One cross-project file was found and removed before push: `docs/F5_F6A_INTERPRETATION_RECONCILIATION.md` (MURAL_ATLAS project content that accidentally landed inside `docs/` in the workspace). It was kept on disk and added to `.gitignore` to prevent re-tracking.
- Total tracked size at push: 23.81 MB (mostly public visual assets).

## Public repository visibility breakdown

- `index.html`, `timeline_1970s.html`, `timeline.html`, `publications.html`, `research-atlas.html` — 5 HTML pages
- `css/research-atlas.css`, `js/research-atlas.js` — 2 stylesheet/script
- `assets/public/1970s/` (12 files), `assets/public/1980s/catalog_renders/` (10 files), `assets/public/1990s/{coeur_v1,coeur_v2,coeur_v3,stel,40days}/` (30 files), `assets/public/research/` (32 files incl. numbered + named) — 84 visual assets under `assets/public/`
- `data/public/` — 4 JSON files + 1 CSV + 1 README (atlas-works, atlas-claims, atlas-evidence, public-assets × 2 formats, README)
- `docs/` — 4 documents (RESEARCH_METHOD, DATA_MODEL, EVIDENCE_MODEL, PROJECT_STATUS)
- `reports/web/` — 11 P0/P0.5/P1 web reports (P0 architecture, P0.5 lineage, P1 build / manifest / gate)
- `README.md`, `LICENSE` (MIT), `LICENSE-DATA.md` (CC BY 4.0), `NOTICE-ASSETS.md`, `CONTRIBUTING.md`, `.gitignore`, `.nojekyll`

## Remaining issues

None that block release. The release gate is **READY_FOR_PUBLICATION** (since the user authorized `gh repo create` + `gh release create` + Pages enablement as part of this P2 round, unlike P1 which only stopped at LOCAL_OPEN_SOURCE_READY).

What remains explicitly **unresolved** (and that is correct, not a bug):

- 1986 machine TITLE / PUBLICATION — preserved as `OPEN_FROZEN_LOW`
- Cristal Saga item-level local plate-front mapping — preserved as `EXHAUSTED`
- Phase 6B-R fresh-context replication — not executed; remains the next research gate
- Body as Narrative Resource — preserved as `PROJECT_LIMITED_WITHIN_CURRENT_NON_COEUR_90S_TEST`
- Reading Discipline non-Cœur — preserved as `FORMALIZATION_READY · INSUFFICIENT`

## What this release does NOT include

- No Vercel / Netlify / Cloudflare / custom-domain deployment
- No DNS changes
- No Phase 6B-R execution
- No new Mœbius research Phase
- No asset additions to repair TEXT_ONLY cases (La Déviation / Le Bandard Fou / Garage Hermétique remain TEXT_ONLY by design)
- No Cristal Saga item-level repair
- No 1986 machine title assignment
- No upgrade to Master Model status
- No fourth-layer model creation