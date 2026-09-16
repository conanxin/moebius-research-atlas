# Mœbius Archive

A digital study of visual language, space, information and narrative — built around the work of Mœbius (Jean Giraud, 1938–2012).

This is **not** a complete catalogue. It is **not** an exhaustive image archive. It is **not** a final theory. It is an ongoing, evidence-led research archive in which models are built, tested against counterexamples, frozen when supported, and revised when they are not.

## Links

- **Repository:** https://github.com/conanxin/moebius-research-atlas
- **Live Research Atlas:** https://conanxin.github.io/moebius-research-atlas/research-atlas.html
- **Portal (GitHub Pages root):** https://conanxin.github.io/moebius-research-atlas/

## Quick links

- **Research Atlas** — [`research-atlas.html`](research-atlas.html)
- **1970s Timeline** — [`timeline_1970s.html`](timeline_1970s.html)
- **Full Timeline** — [`timeline.html`](timeline.html)
- **Publications** — [`publications.html`](publications.html)
- **Archive Home** — [`index.html`](index.html)
- **Public Research Data** — [`data/public/`](data/public/)
- **Public Visual Assets** — [`assets/public/`](assets/public/)

## What this is

A research archive that documents:

1. **How Mœbius's visual language works** — across 1970s, 1980s, 1990s — through a working **Master Model**: *Stable Spatial Hand × Task-Conditioned Information Regime*. Status: **SUPPORTED_WITH_LIMITS** (not a final theory).
2. **How strange objects stay readable** — through the *Strange Object Readability* framework (Function × Ontology × Physics × Human Relation × Space Role).
3. **How the body drives narrative** — through *Body as Narrative Resource* in <em>Le Cœur couronné</em> and partial replication outside.
4. **What the open questions are** — including the unresolved 1986 machine title/publication and the exhausted Cristal Saga item-level mapping.

## What this is not

- Not a complete catalogue of every Mœbius work.
- Not an exhaustive image archive.
- Not a final theory or artistic biography.
- Not a marketing site.

## Repository structure

```
/
├── index.html              # portal (existing)
├── research-atlas.html     # main research narrative page (this release)
├── timeline_1970s.html     # 1970s First-Pass LOCK browsing tool (existing)
├── timeline.html           # 1980s timeline (existing)
├── publications.html        # publications index (existing)
│
├── css/
│   └── research-atlas.css
├── js/
│   └── research-atlas.js
│
├── assets/
│   └── public/             # public visual assets (copies of originals with lineage)
│       ├── 1970s/
│       ├── 1980s/
│       ├── 1990s/
│       └── research/       # derived research boards
│
├── data/
│   └── public/             # public research data (JSON + CSV)
│       ├── atlas-works.json
│       ├── atlas-claims.json
│       ├── atlas-evidence.json
│       ├── public-assets.json
│       ├── public-assets.csv
│       └── README.md
│
├── docs/
│   ├── RESEARCH_METHOD.md
│   ├── DATA_MODEL.md
│   ├── EVIDENCE_MODEL.md
│   └── PROJECT_STATUS.md
│
├── studies/                # research studies and locked findings
├── reports/                # phase reports, claim ledgers, freeze records
├── notes/                  # work cards, corpus notes, research leads
│
├── README.md
├── CONTRIBUTING.md
├── LICENSE                  # MIT (code)
├── LICENSE-DATA.md          # CC BY 4.0 (research data)
├── NOTICE-ASSETS.md         # visual asset source attribution
└── .gitignore
```

## How the research works

```
IDENTITY GATE   →   SAMPLE FREEZE   →   FRESH VISION
        ↓
     LEDGER   →   HYPOTHESIS   →   COUNTEREXAMPLE   →   LOCK
```

See [`docs/RESEARCH_METHOD.md`](docs/RESEARCH_METHOD.md) for full protocol.

## Current limitations (must read)

These are not gaps that will be silently filled by the website. They are research findings:

1. **SECTION_02** of the Research Atlas (La Déviation / Le Bandard Fou / Garage Hermétique) is **TEXT_ONLY** by design — no local raw scans available; using text-only research cards rather than fabricating visual evidence.
2. **1970s visual evidence** in the Atlas comes from TAOM 1989 reproductions and moebius.fr harvests. Captions clearly state the source.
3. **Catalog-renders** (1980s auction entries) are shown as **identity = SOURCE_IDENTIFIED · image_match_status = PENDING**. They are not promoted to canonical original artwork.
4. **Cristal Saga** item-level plate-front mapping is **EXHAUSTED**. Corpus-level evidence remains.
5. **1986 machine** title and publication are **UNRESOLVED**. Status: OPEN_FROZEN_LOW.

## Open questions

- **1986 machine**: TITLE / PUBLICATION unresolved
- **Cristal Saga**: item-level visual mapping exhausted
- **Body as Narrative Resource**: PROJECT_LIMITED (Phase 6B PARTIAL_1_OF_2)
- **Reading Discipline**: FORMALIZATION_READY but non-Cœur validation INSUFFICIENT
- **Phase 6B-R**: fresh-context clean replication is the NEXT gate

Unresolved states are research results, not failures.

## Local viewing

Static site. Two options:

1. **Double-click** `research-atlas.html` (works in any modern browser)
2. **Static server**:
   ```bash
   cd path/to/repo
   python -m http.server 8000
   # then open http://localhost:8000/research-atlas.html
   ```

No build step. No npm install. No framework runtime.

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md). Contributions must respect:

- **No automatic override** of CONFIRMED / LOCKED / CURRENT VERDICT
- **Research edits** enter as PROPOSED / UNVERIFIED first
- **Asset lineage** must be traceable per file (see [`notes/ASSET_METADATA_SCHEMA.md`](notes/ASSET_METADATA_SCHEMA.md))
- **Source identification** must precede claim escalation

## Public UX

v0.1.1 improves the public surface without touching any research verdict:

- Public landing page (`index.html`) replaced the prior internal-workspace dashboard with a clean portal.
- Internal links to non-public resources removed from public HTML.
- Plain-language glosses added for key model terms (axis names, status codes).
- Open-source entry point added to both home and atlas footers.
- In-page table of contents on the Research Atlas.
- Mobile layout adjustments for comparison grids and the top nav.

A reader-test report (P3) and its v0.1.1 implementation list are archived locally.

## License

- **Code**: [MIT](LICENSE)
- **Research data** (`data/public/`, `docs/`, generated metadata): [CC BY 4.0](LICENSE-DATA.md)
- **Visual assets**: see [NOTICE-ASSETS.md](NOTICE-ASSETS.md) — assets are **not** automatically included in MIT or CC BY. Each source is attributed.

## Acknowledgments

Built on systematic reading, external fresh-vision review, and explicit counterexample testing. Thanks to the user who provided external review across multiple sessions and insisted that unresolved states be preserved as research results, not papered over.
