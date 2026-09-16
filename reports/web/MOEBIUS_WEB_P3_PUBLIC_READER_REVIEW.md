# MOEBIUS_WEB_P3 · Public Reader Review Report

> 2026-09-16 · READ-ONLY PUBLIC REVIEW of v0.1.0
> Live site: https://conanxin.github.io/moebius-research-atlas/
> Review mode: simulate a first-time visitor; no source files consulted until after content review.

## TL;DR

The **Research Atlas page itself** is high-quality research communication: clear method statement, honest uncertainty, evidence-led counterexample logic, deliberate TEXT_ONLY disclosures, and a closing line ("Unresolved states are research results, not failures") that does the heavy epistemic lifting.

But the **home page (`index.html`) was shipped in a broken state for public use**: it links to 126 non-public resources (`raw/`, `notes/`, `studies/`, `reports/`, `derived/` paths) that return HTTP 404 on the live site. This is a P0_PUBLIC_BLOCKER. Without addressing it, a first-time reader who clicks any Work Card or timeline evidence link gets a broken page.

**Decision: PASS_WITH_TARGETED_V0_1_1** — research communication is sound, but two P0 blockers in the home page need a small v0.1.1 round.

---

## 1. Public version reviewed

| Page | URL | Bytes | Status |
|---|---|---|---|
| Home (root) | `/` | 82,952 | 200, broken links to non-public paths |
| Research Atlas | `/research-atlas.html` | 23,955 | 200, clean |
| 1970s Timeline | `/timeline_1970s.html` | 6,026 | 200 |
| Full Timeline | `/timeline.html` | 19,399 | 200 |
| Publications | `/publications.html` | 14,325 | 200 |

Fetched via `curl` after the GitHub Pages rebuild triggered by the v0.1.0 release.

## 2. First 30 seconds test

### Home page first screen

The home page above the fold shows:

- Title: "Moebius Archive — Mœbius / Jean Giraud 数字档案"
- Lead: "Phase 2A.1 · 1980s core corpus: 45 works (43 visual) · 23 publications · Session 01 done · 1986 machine lead: OPEN_FROZEN (LOW)"
- Dense "Mœbius Research Model" status block with 8 sub-blocks (Master Model, Research Protocol, 1970s, 1980s, 1990s Validation, Studies, Themes, Counterexamples, Research Leads).
- "Start Here" block with "▸ Research Atlas (NEW)" card and several other internal-research cards.

| Item | Result |
|---|---|
| PROJECT_SUBJECT | UNCLEAR |
| PROJECT_TYPE | UNCLEAR |
| PRIMARY_RESEARCH_QUESTION | UNCLEAR |
| WHY_DIFFERENT_FROM_FAN_SITE | PARTIAL |
| CURRENT_MODEL_STATUS | PARTIAL |

**HOME first impression = UNCLEAR.** A first-time visitor sees internal phase labels, internal milestone counts (45 works / 43 visual / Session 01), and dense acronyms (S018, S019, AOM) before they see "research atlas". The Research Atlas card exists but is buried inside a status block.

### Research Atlas hero

The Research Atlas hero shows:

- Eyebrow: "MŒBIUS ARCHIVE · OPEN RESEARCH ATLAS"
- H1: "Mœbius Research Atlas"
- Subtitle: "A Digital Study of Visual Language, Space, Information and Narrative"
- One-liner: "One artist, many visual regimes."
- Body intro: "This atlas is not a complete catalogue of Mœbius's work. It documents a research method: how systematic reading, cross-work comparison, blind review, counterexample testing, and disciplined evidence management gradually shape — and revise — what we know about Mœbius's visual language."
- 4-meta row (Period covered · Master model status · Code license · Research data license)

| Item | Result |
|---|---|
| PROJECT_SUBJECT | CLEAR |
| PROJECT_TYPE | CLEAR |
| PRIMARY_RESEARCH_QUESTION | CLEAR |
| WHY_DIFFERENT_FROM_FAN_SITE | CLEAR |
| CURRENT_MODEL_STATUS | CLEAR (badge visible) |

**ATLAS first impression = CLEAR.**

## 3. 3-minute comprehension test

A reader who reads Hero + Sections 02/03/04 (5 minutes total) then closes the page:

| Q | Reader takeaway | Verdict |
|---|---|---|
| Q1: 1970s 发生了什么？ | "Five core works. The formation period: not a linear style evolution, but parallel experiments in different visual regimes." Five works with role labels. | UNDERSTOOD (with effort; labels are jargon-heavy) |
| Q2: Why no single 1980s style? | "Do not search for a single '1980s Mœbius style'. Same decade — different tasks — different visual regimes. TASK / PROJECT CONDITION often predicts visual language better than SIMPLE CHRONOLOGY." | UNDERSTOOD |
| Q3: Stable Spatial Hand? | 3 bullets: contour/silhouette control, spatial readability, physical legibility of strange forms. | UNDERSTOOD |
| Q4: Task-Conditioned Information Regime? | 6 axis names listed without plain gloss. | PARTIALLY_UNDERSTOOD |
| Q5: Model status? | Badge: SUPPORTED_WITH_LIMITS. No inline "what limits". | PARTIALLY_UNDERSTOOD |

**MODEL_ARRIVAL = MOSTLY_EARNED.** Section 02 (1970s comparison) + Section 03 (1980s comparison + the "task vs chronology" sentence) build to Section 04 (model announced). The comparison earns the model, but the model itself is announced rather than derived.

**TERM_INTRODUCED_BEFORE_EXPLAINED:** 6 axis names (TEXT_AMOUNT, WORLD_EXPLANATION, EVENT_CAUSALITY, FUNCTIONAL_INFORMATION, VISUAL_AUTONOMY, PANEL_DENSITY) and the regime label examples (LOW_EXPLANATION, HIGH_VISUAL_CAUSALITY, etc) are used before being defined.

## 4. Section-by-section review

11 sections, scored on PURPOSE_CLEAR / KEY_POINT_CLEAR / EVIDENCE_VISIBLE / JARGON_LOAD / NEXT_TRANSITION_CLEAR.

| # | Section | Score summary | One-line takeaway |
|---|---|---|---|
| 01 | Hero | HIGH/HIGH/LOW/LOW/HIGH | Method statement clearly orients. |
 | 02 | 1970s | HIGH/MEDIUM/MEDIUM/MEDIUM/MEDIUM | Five formation works + TEXT_ONLY disclosure for 3 of 5. |
 | 03 | 1980s | HIGH/HIGH/MEDIUM/MEDIUM/LOW | One-liner about "many Mœbius" + 1986 machine preserved as UNRESOLVED. |
 | 04 | Master Model | HIGH/HIGH/HIGH/HIGH/MEDIUM | Two-axis framework + status badge; axes lack plain gloss. |
 | 05 | Strange Object Readability | HIGH/HIGH/MEDIUM/MEDIUM/MEDIUM | Cleanest jargon-to-English ratio (each axis gets one-line gloss). |
 | 06 | Relation First / Ontology Deferred | HIGH/HIGH/MEDIUM/HIGH/MEDIUM | "WORKING_MODEL_V0.1" explicit; matrix codes need inline definition. |
 | 07 | Crystal / Energy | HIGH/HIGH/MEDIUM/MEDIUM/MEDIUM | "Initial question → current result" narrative; Cristal Saga EXHAUSTED. |
 | 08 | Le Cœur couronné | HIGH/HIGH/LOW/HIGH/MEDIUM | "Body Acts Before Explanation" title; 3 body arcs in jargon. |
 | 09 | Counterexample Stel vs 40 Days | HIGH/HIGH/LOW/HIGH/MEDIUM | Stel meets / 40 Days does not; "research progress, not failure". |
 | 10 | How the Research Works | HIGH/HIGH/LOW/LOW/MEDIUM | 7-step chain + 3 real method-failure cases (best for first-time readers). |
 | 11 | Open Questions | HIGH/HIGH/LOW/MEDIUM/LOW | Closing line "Unresolved states are research results, not failures." |

Full detail in `MOEBIUS_WEB_P3_SECTION_AUDIT.csv`.

## 5. Jargon audit

17 terms audited. **10 SAFE** (have inline plain-English explanation + example). **7 NEEDS_GLOSS** (used in Sections 04/06/07/08/11 without inline definition).

Top needs-gloss:
- Task-Conditioned Information Regime (6 axes unglossed)
- Information Regime (parent term unglossed)
- Visual Causality (used as tag)
- Functional Information (used as tag)
- Project Vocabulary (used as conclusion)
- Body as Narrative Resource (status badge opaque)
- SUPPORTED_WITH_LIMITS (badge visible but limits not inline)

Full detail in `MOEBIUS_WEB_P3_JARGON_AUDIT.csv`.

**Conclusion:** No jargon is "TOO_INTERNAL" — every term appears in some form of plain context. The issue is *density*, not *opacity*.

## 6. Stel vs 40 Days core test

This section is the single most important test for whether the research method is publicly communicable.

| Question | Verdict |
|---|---|
| A. Stel positive case understandable? | YES — parentheticals ("fall/daze onset alters beast interaction"; "instrument invasion + neurological intervention → subconscious voyage") explain WHY. |
| B. 40 Days counterexample understandable? | YES with caveat — plain-English line carries it; CE_BODY_1/CE_BODY_3 codes are unexplained. |
| C. BODY VISIBILITY ≠ NARRATIVE CAUSALITY? | YES — repeated in section lede + closing. |
| D. Why PARTIAL_1_OF_2 and not FAILED/SUPPORTED? | PARTIAL — closing sentence saves it, but the "1 of 2" never appears in plain English. |
| E. Method allows theory to be constrained? | YES — "Counterexamples can limit a model — that is research progress, not failure." |

**STEL_40DAYS_READER_TEST = PASS (with caveats).**

**ONE_SENTENCE_READER_SUMMARY:** "Mœbius's World of Edena shows bodies physically triggering narrative shifts; his 40 Days dans le Désert shows bodies on screen without triggering anything — so the research project concluded the body-as-narrative-resource idea only works for some projects, not all, and that's progress, not failure."

A stranger can produce this sentence from the page.

## 7. Uncertainty communication

**UNCERTAINTY_COMMUNICATION = STRONG.**

Every uncertainty is named explicitly:
- 1986 machine — TITLE unresolved · PUBLICATION unresolved · OPEN_FROZEN_LOW (Section 03 + 11)
- Cristal Saga — item-level EXHAUSTED; corpus-level remains (Section 07 + 11)
- Body as Narrative Resource — PROJECT_LIMITED_WITHIN_CURRENT_NON_COEUR_90S_TEST; FOURTH_LAYER=NOT_READY (Section 11)
- Reading Discipline — FORMALIZATION_READY; non-Cœur validation INSUFFICIENT (Section 11)
- Phase 6B-R — fresh-context clean replication is the NEXT gate (Section 11)

Closing line of the entire atlas: **"Unresolved states are research results, not failures."** This is the single most important sentence on the site. It communicates to a non-specialist that "we don't know" is not "we failed".

## 8. TEXT_ONLY presentation

**TEXT_ONLY_PRESENTATION = INTENTIONAL.**

La Déviation / Le Bandard Fou / Garage Hermétique cards each carry an explicit: "Visual asset not used in current public evidence set. No local raw scan of [X] is available. Research continues via the verified claim ledger." Reason is given; substitute is cited. The presentation reads as a research choice, not a broken page.

## 9. Caption evidence clarity

**CAPTION_EVIDENCE_CLARITY = HIGH** for most tiers:
- TAOM 1989 reproduction: caption states "1989 reproduction from The Art of Moebius (Moebius Production)"
- moebius.fr harvest: caption states "Source: moebius.fr"
- Catalog render: caption states "identity = SOURCE_IDENTIFIED · image_match_status = PENDING"
- Research boards: caption states "RESEARCH DERIVATIVE — boards visualize claims and counterexamples"

**CAPTION_EVIDENCE_CLARITY = MEDIUM** for 80s catalog works (W-S019-613 / W-S018-153 / W-S019-615). The work IDs and ISBN are visible in caption text, but full provenance is only in Section 03 prose. Reader has to read carefully.

## 10. Visual hierarchy

**METADATA_DOMINANCE = NO.** The hero leads with title + subtitle + one-liner + body intro. Status badges appear in a 4-cell meta row below, not as the dominant element.

Section 04's Master Model status badge (SUPPORTED_WITH_LIMITS) appears between H2 and the model-grid. It is visible but not overwhelming.

## 11. Reading density

| Section | Text chars | Notes |
|---|---|---|
| 01 Hero | 446 | Light. |
| 02 1970s | 3,106 | Densest. Five work cards with role labels + TEXT_ONLY explanations. |
| 03 1980s | 1,320 | Medium. |
| 04 Master Model | 913 | Compact but content-heavy. |
| 05 Strange Object | 607 | Light. |
| 06 Relation First | 607 | Light. |
| 07 Crystal / Energy | 647 | Light. |
| 08 Le Cœur | 992 | Medium; body-arc taxonomy dense. |
| 09 Stel vs 40 Days | 739 | Clean. |
| 10 Research Method | 1,693 | Long but broken by 7-step + 3 cases structure. |
| 11 Open Questions | 563 | Light. |

No section is too dense. Sections 02 and 04 are densest but are broken up by images. Section 08's body-arc taxonomy is the most jargon-dense block on the page.

## 12. Navigation

**NAVIGATION_RESULT = PASS_WITH_FRICTION.**

- Home → Research Atlas path exists (Research Atlas card in Start Here block).
- Research Atlas top nav: 5 items (Atlas / 1970s Timeline / Full Timeline / Publications / Archive Home).
- Each section heading is an anchor.
- BUT: no in-page TOC at top; no prev/next section navigation; reader must scroll continuously.
- BUT: Home page's Research Atlas link is buried in dense status cards.

## 13. Open source discovery

**OPEN_SOURCE_DISCOVERABILITY = LOW.**

- `research-atlas.html` mentions MIT (code) and CC BY 4.0 (data) in hero meta. Does NOT link to GitHub repo, CONTRIBUTING.md, data/public/.
- `index.html` mentions MIT. Does NOT link to repo or data.
- README.md on GitHub has the full picture (repo + CONTRIBUTING + LICENSE + LICENSE-DATA + data/public/), but a reader has to find it.
- No "Open Project" entry point on the website.

## 14. Mobile reader

**MOBILE_READER_RESULT = PASS_WITH_FRICTION.**

- CSS has 3 media queries (max-width:768px, max-width:390px, prefers-reduced-motion:reduce).
- Hero-meta uses `grid-template-columns: repeat(auto-fit, minmax(180px, 1fr))` so it reflows.
- 2x2 matrix in Section 06 becomes single-column at narrow widths (loses the comparison structure).
- Counter grid (Stel vs 40 Days) similarly becomes single-column.
- 5-item top nav may overflow horizontally at 390px.
- 6-board grid in Section 04 wraps.

Layout compromises inherent to dense content; readable but requires vertical scrolling.

## 15. Public reader personas

| Persona | Gains | Gets lost |
|---|---|---|
| **A. Mœbius fan** | Recognizable works + 1986 machine mystery preserved + 1980s "no single style" insight. | Jargon role tags in Section 02; home page is internal-dashboard style; TEXT_ONLY works look incomplete. |
| **B. Art / visual-culture student** | Full Master Model; 5 axes of Strange Object Readability; 2x2 Relation First matrix; counterexample pattern; Crystal / Energy narrowing. | Internal codes (Q1, CE-A) in Section 06; unglossed axis names in Section 04; jargon body-arc taxonomies in Section 08. |
| **C. DH / research methods reader** | 7-step method chain + 3 method-failure cases; controlled-vocabulary status labels; 5-limitation set; closing line. | Repo / data / CONTRIBUTING not discoverable from site; home page is not the research atlas; epistemic markers look Latin to non-specialists. |

## 16. Issue register

| ID | Severity | Location | Summary |
|---|---|---|---|
| P0-01 | P0_PUBLIC_BLOCKER | `/` (index.html) | 126 internal links to non-public resources (raw/, notes/, studies/, reports/, derived/) all return 404. |
| P0-02 | P0_PUBLIC_BLOCKER | `/` (index.html) | Home page first-fold is internal-dashboard text; not a public landing page. |
| P1-01 | P1_HIGH_VALUE | research-atlas.html §04 | 6 Information Regime axes listed without plain-English gloss. |
| P1-02 | P1_HIGH_VALUE | research-atlas.html §04 | "SUPPORTED_WITH_LIMITS" badge has no inline "what the limits are" callout. |
| P1-03 | P1_HIGH_VALUE | research-atlas.html §09 | "PARTIAL_1_OF_2" code is never translated to "1 of 2 projects passed". |
| P1-04 | P1_HIGH_VALUE | research-atlas.html top | No in-page TOC / anchor jump list. |
| P1-05 | P1_HIGH_VALUE | research-atlas.html footer | No GitHub / data / CONTRIBUTING link block. |
| P1-06 | P1_HIGH_VALUE | research-atlas.html §06 | 2x2 matrix uses Q1 / CE-A codes unglossed. |
| P2-01 | P2_POLISH | research-atlas.html §08 | Body-arc taxonomies in jargon. |
| P2-02 | P2_POLISH | research-atlas.html §02 | Work card role tags unglossed. |
| P2-03 | P2_POLISH | research-atlas.html §02 | TEXT_ONLY marker is below the card, easily missed. |
| P2-04 | P2_POLISH | research-atlas.html §04 | Section 04 preamble to the model could be plain-English before axis names. |
| P2-05 | P2_POLISH | research-atlas.html §03 | Work IDs and ISBNs visible to reader; could move into `<details>`. |
| NA-01 | NO_ACTION | research-atlas.html §09 | CE_BODY_1 / CE_BODY_3 codes — plain-English line carries the message. |
| NA-02 | NO_ACTION | research-atlas.html §11 | Compound status labels — precision is the research finding. |
| NA-03 | NO_ACTION | research-atlas.html §05 | Strange Object Readability 5 axes are from frozen framework. |
| NA-04 | NO_ACTION | research-atlas.html §02 | TEXT_ONLY disclosure is already present; P2-03 is presentation. |

Full detail in `MOEBIUS_WEB_P3_ISSUE_REGISTER.csv`.

## 17. P3 decision

**P3_DECISION = PASS_WITH_TARGETED_V0_1_1**

### Why not PUBLIC_READER_PASS

- The home page (`index.html`) is materially broken on the live site (P0-01, P0-02). Without addressing this, a first-time visitor who clicks any "Work Card" link gets a 404.
- Six high-value comprehension issues (P1-01 to P1-06) remain.

### Why not MAJOR_PUBLIC_COMPREHENSION_PROBLEM

- The Research Atlas page itself communicates the research method, the Master Model, the counterexample pattern, and the uncertainty status clearly to a first-time reader.
- Section 09 (Stel vs 40 Days) passes its single-sentence summary test.
- Section 11's closing line ("Unresolved states are research results, not failures") does the heavy epistemic lifting.
- Section 10 (How the Research Works) is the strongest public-friendly content on the site.

The research communication is sound. The public landing is broken. These are different problems.

### Why PASS_WITH_TARGETED_V0_1_1

The 8 recommended changes in `MOEBIUS_WEB_P3_V0_1_1_RECOMMENDATIONS.md` are bounded, minimal, and preserve all research verdicts. Estimated effort: 80–120 min including QA. After v0.1.1, a P3-R verification round should confirm each change improved first-time comprehension.

## 18. What this review did NOT do

Per P3 §0 (READ-ONLY PUBLIC REVIEW):

- Did NOT modify HTML, CSS, JS, README, public data.
- Did NOT add visuals.
- Did NOT modify captions or research verdicts.
- Did NOT commit, push, or release.
- Did NOT add to v0.1.1 (recommendations are advisory only).
- Did NOT run a fresh public-readability verification round (that is the next step after v0.1.1).

The 5 output files are local artifacts (not committed). User decision required before v0.1.1 implementation.

## 19. Output files

| File | Purpose |
|---|---|
| `reports/web/MOEBIUS_WEB_P3_PUBLIC_READER_REVIEW.md` | This report. |
| `reports/web/MOEBIUS_WEB_P3_SECTION_AUDIT.csv` | 11 sections × 5 score dimensions. |
| `reports/web/MOEBIUS_WEB_P3_JARGON_AUDIT.csv` | 17 terms × first-appearance / gloss / example / verdict. |
| `reports/web/MOEEBIUS_WEB_P3_ISSUE_REGISTER.csv` | 17 issues × 8 columns (severity, location, observation, why, reader, fix, research-meaning impact). |
| `reports/web/MOEBIUS_WEB_P3_V0_1_1_RECOMMENDATIONS.md` | 8-item change list, ranked, with effort estimate. |

Local-only. Not committed. Not pushed. Not part of v0.1.0 release.