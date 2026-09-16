# MOEBIUS_WEB_P3 · V0.1.1 Recommendations

> 2026-09-16 · Pre-implementation list of high-value targeted changes for v0.1.1
> All changes preserve research verdicts. Each item: WHY · WHERE · MINIMAL FIX · IMPACT BUDGET

## Priority order (top to bottom)

### 1. **P0-01**: Strip or guard non-public hrefs in `index.html`

**Why:** The published home page has 126 links to `raw/`, `notes/`, `studies/`, `reports/`, `derived/` paths — none of which exist in the public repo. All return HTTP 404. Every reader who clicks past the home page hits a broken link.

**Where:** `index.html (repository root)` (committed as `d8aa037`).

**Minimal fix (two valid options):**

- **Option A (preferred): Replace the home page entirely with a clean public portal.** Header + one-line tagline + 4-card grid (Research Atlas · 1970s Timeline · Full Timeline · Publications) + status badge row + footer link to GitHub. Keep the current dense content in a separate `archive-status.html` only linked from internal navigation.
- **Option B: Surgical strip.** Remove all `href` attributes that resolve to non-public directories. Leave text-only labels in place so no information is lost, but make it impossible to click to a 404.

**Effort:** 30–60 min for Option A; 15–30 min for Option B.

**Impact:** Restores the entire reader journey past the home page. Without this fix, v0.1.0 is functionally broken for anyone who clicks.

---

### 2. **P0-02**: Make the home page first-fold answer "what is this?"

**Why:** The current first-fold is internal dashboard text ("Moebius Archive — P1B Curation", "Phase 2A.1 · 1980s core corpus: 45 works"). A first-time visitor does not learn what the project is.

**Where:** Same `index.html`. Even after P0-01 fix, the replacement hero must lead with project identity.

**Minimal fix:** Top of page = eyebrow + H1 project name + one-line subtitle ("A digital study of Mœbius's visual language across 1970s / 1980s / 1990s") + 4 portal cards + license badges. Move the Phase 2A.1 / P1B summary to a separate "Archive Status" section lower on the page.

**Effort:** Included in P0-01 Option A.

**Impact:** First-time visitors understand the project within 5 seconds.

---

### 3. **P1-01**: Add plain-English glosses for the 6 Task-Conditioned Information Regime axes

**Why:** Section 04 lists 6 axis names (TEXT_AMOUNT, WORLD_EXPLANATION, EVENT_CAUSALITY, FUNCTIONAL_INFORMATION, VISUAL_AUTONOMY, PANEL_DENSITY) without explanation. Sections 06/07/08 depend on these terms.

**Where:** `research-atlas.html` Section 04, in the `.regime-dims` block.

**Minimal fix:** One short clause per axis. Examples:

- TEXT_AMOUNT — how much on-page text vs image carries the page
- WORLD_EXPLANATION — how much the world's rules are explained
- EVENT_CAUSALITY — how much an event causes the next event
- FUNCTIONAL_INFORMATION — how much the world works like a system
- VISUAL_AUTONOMY — how much the image carries meaning without text
- PANEL_DENSITY — how many panels per page on average

Keep the SCREAMING_SNAKE_CASE labels (verifiability) but add a `<dd>` with plain text under each `<dt>`.

**Effort:** 15 min.

**Impact:** Section 04 becomes self-explanatory. Sections 06/07/08 stop being opaque.

---

### 4. **P1-02**: Add inline "what the limits are" callout under the SUPPORTED_WITH_LIMITS badge

**Why:** The badge is visible in the hero and Section 04 but the reader does not know what the limits are, nor that this is not a final theory.

**Where:** `research-atlas.html` Section 04, immediately under the `<p class="model-status">`.

**Minimal fix:** Add: `<p class="model-limits">A working model tested against counterexamples across 1970s/1980s/1990s. Not a final theory — see Section 10 for the protocol that constrains it, and Section 11 for what is not yet established.</p>`

**Effort:** 5 min.

**Impact:** Reader sees the epistemic status of the model right where it is named.

---

### 5. **P1-03**: Add a "1 of 2 projects passed" plain-English line in Section 09

**Why:** `PARTIAL_1_OF_2` is a code. The closing line saves it for some readers, but the gap is unnecessary.

**Where:** `research-atlas.html` Section 09, immediately under the section lede.

**Minimal fix:** Add: `<p class="plain-summary">Of the two projects tested, one passed the threshold (Stel), one did not (40 Days dans le Désert). The result is partial support, not failure.</p>`

**Effort:** 5 min.

**Impact:** Section 09 becomes accessible to a non-specialist without needing to decode the code.

---

### 6. **P1-04**: Add an "On this page" anchor list under the hero

**Why:** The atlas is 11 sections long. No in-page jump list means continuous scrolling.

**Where:** `research-atlas.html` under `<header class="atlas-header">` and `<main id="main">`.

**Minimal fix:** A small block with 11 numbered anchor links. Keep it minimal (no JS, just `<a href="#section-XX">`).

**Effort:** 10 min.

**Impact:** Reader can jump between sections; less scroll fatigue.

---

### 7. **P1-05**: Add a GitHub / data / CONTRIBUTING link block to the footer

**Why:** A first-time reader cannot find the source code or data without guessing the URL. The current footer has LICENSE / NOTICE-ASSETS but no GitHub link.

**Where:** `research-atlas.html` footer.

**Minimal fix:** Add: "Open source: github.com/conanxin/moebius-research-atlas · CONTRIBUTING.md · data/public/" — three plain links. Same on `index.html` if it survives P0-01.

**Effort:** 5 min.

**Impact:** Reader who likes the site can find the source.

---

### 8. **P1-06**: Replace Q1 / CE-A codes in the 2x2 matrix with plain descriptions

**Why:** Section 06's matrix uses internal codes (Q1, CE-A) that have no inline definition.

**Where:** `research-atlas.html` Section 06, in the matrix table.

**Minimal fix:** Either:
- (a) Replace `Q1 (default)` with `relations clear / ontology clear — the default case` and `CE-A` with `counterexample class A — no visual-level case yet (open slot)`.
- (b) Add a one-paragraph legend under the matrix that defines Q1 and CE-A in plain English.

**Effort:** 10 min.

**Impact:** Section 06's matrix becomes self-explanatory.

---

## Explicit non-changes

| ID | Reason for not changing |
|---|---|
| NA-01 | CE_BODY_1 / CE_BODY_3 in Section 09 are internal audit codes; the plain-English line already carries the message. |
| NA-02 | Compound status labels (PROJECT_LIMITED_WITHIN_CURRENT_NON_COEUR_90S_TEST etc.) are intentionally precise research codes. |
| NA-03 | Strange Object Readability's 5 axes are frozen in Phase 5A framework. Reordering = changing framework. |
| NA-04 | TEXT_ONLY works already have the explicit disclosure; P2-03 polish is a presentation tweak but not a fix. |

---

## Effort budget

Total v0.1.1 effort estimate: **80–120 min** of editing + QA. Less if Option B is chosen for P0-01.

## What v0.1.1 will NOT include

- New visual assets
- Changes to research verdicts
- Changes to public research data
- A new GitHub Pages build
- New sections
- Removal of any existing content

## What must happen AFTER v0.1.1

A new public-readability review round (P3-R) to verify each recommended change actually improved first-time comprehension. Same 23-question protocol.