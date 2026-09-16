# Research Method

The Mœbius Archive follows a strict research protocol that prevents silent revisions and reward-independent evidence.

## Seven-step chain

```
IDENTITY GATE
↓
SAMPLE FREEZE
↓
FRESH VISION
↓
LEDGER
↓
HYPOTHESIS
↓
COUNTEREXAMPLE
↓
LOCK
```

### 1. IDENTITY GATE

Before any work can be used as evidence, its identity must be verified.

- **Author attribution** must be traceable (catalog entry, signed work, museum record).
- **Title and period** must be supported by at least one independent source.
- **Identity status** is classified: `SOURCE_IDENTIFIED` / `CROSSCHECKED` / `VERIFIED`.

If the identity cannot be verified, the work is excluded from the active corpus. UNRESOLVED status is preserved as a research result, not papered over.

### 2. SAMPLE FREEZE

For a given research question, the page sample is determined **before** any visual analysis.

- Pages are selected by **rule-based position**, not visual appeal.
- The sample span must be a **continuous story sequence**, not scattered highlights.
- Sample integrity is locked via **SHA256 hashes** before any reviewer sees the pages.
- The freeze record (`reports/PHASE*_SAMPLE_FREEZE.csv`) is immutable post-freeze.

### 3. FRESH VISION

Pages are reviewed by a **fresh external reviewer** who has not seen the model's vocabulary.

- The review bundle is checked for **literal contamination** (banned keywords) AND **semantic contamination** (hypothesis leakage in framing).
- The reviewer answers **open questions only** (no leading questions).
- The reviewer's observations are recorded verbatim — no rewrites, no paraphrases.

### 4. LEDGER

Observations from fresh vision are entered into a **structured ledger** with:

- Work / project / page identity
- Body / space / text observations
- Open questions and unresolved items
- Counterexamples and null findings

The original ledger file is preserved. Subsequent corrections go to a **delta** file (e.g. `*_DELTA.csv`).

### 5. HYPOTHESIS

A formal claim is written, with:

- Clear scope and applicable corpora
- Falsifiable prediction (what evidence would break it)
- Pre-registered thresholds (PASS / PARTIAL / FAIL)

The hypothesis is **preregistered** via a SHA256-pinned file before being tested.

### 6. COUNTEREXAMPLE

Hypotheses are explicitly tested against cases that should break them.

- **Pre-registered counterexample classes** are frozen before any reading.
- New evidence is matched against these classes, not against ad-hoc cases.
- A counterexample does not invalidate the hypothesis; it **constrains** its scope.

### 7. LOCK

When a hypothesis reaches a stable verdict, the conclusion is **frozen**.

- The verdict includes a clear status: `SUPPORTED` / `SUPPORTED_WITH_LIMITS` / `PROJECT_LIMITED` / `EXHAUSTED` / `OPEN_FROZEN` / `UNRESOLVED` / etc.
- The verdict's scope and limitations are documented.
- Subsequent revisions go through **explicit re-opening**, not silent edit.

## Three method lessons (real failures documented in Research Atlas Case 01–03)

1. **Keyword-clean ≠ hypothesis-blind.** A bundle passed a literal-contamination check but its README contained semantic hypothesis leakage ("especially notice body-state..."). External reviewers saw the hypothesis embedded in the framing. Lesson: anti-contamination must include **semantic** review, not just banned-keyword lists.
2. **Programmatically contiguous ≠ narratively contiguous.** A sample freeze selected pages by scan index; one included front matter, a chapter title page, and a preface. The pages were sequentially adjacent in the source scan, but they were not story. Lesson: sample integrity requires **independent page-role adjudication**, not just byte-contiguous scans.
3. **Confirmed work identity ≠ canonical visual asset.** A work's identity was confirmed at SOURCE_IDENTIFIED level, but the linked local file turned out to be an edition / package page or product montage. The work was real; the asset role was wrong. Lesson: `asset_role` must be **adjudicated per file**, not inherited from the work record.

## Standing prohibitions

The following are NEVER permitted in this archive, regardless of how clean the data looks:

- Filling in unresolved metadata (titles, years, attributions) without independent evidence
- Downgrading or upgrading any current verdict to suit a presentational goal
- Silent edits to lock files
- Using `unresolved` states as a barrier; unresolved is a result, not a failure
