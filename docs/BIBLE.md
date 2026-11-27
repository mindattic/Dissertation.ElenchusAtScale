---
layer: bible
status: living
---
# Elenchus at Scale — Project Bible

> Single source of truth for what this manuscript IS, is NOT, and the rules that keep it coherent.
> README says how to read and export it; this says how to think about it. The finish line lives in
> `docs/RELEASE.md`.

## 1. The one sentence {#DEAS-§1}
*Elenchus at Scale: Socratic Oral Assessment by Synthetic Examiners* is a dissertation arguing, with Gadfly as its
case, that whether a synthetic Socratic examiner's evidence is fit to inform a grade depends on the conditions of
the examination more than on the capability of the models.

## 2. The product promise {#DEAS-§2}
- A reader can check every citation: each source's verification level is recorded in Appendix A.
- The thesis names five conditions (wide sampling, anchored rubrics, fairness controls, blind human grading with
  reconciliation, integrity signals as context) and designs the test that would show whether a system meets them.
- Statements about Gadfly are tied to named commits and can be checked in its code.

## 3. What it is NOT {#DEAS-§3}
- Not an empirical study: it designs a test (Chapter 7) and reports no result.
- Not a claim that Gadfly already meets the conditions.
- Not Gadfly's documentation; Gadfly's behaviour is described as of commits `e691015` and `5643444`.
- Not a place for unverified sources: an unopened source is never presented as verified.

## 4. Architecture canon {#DEAS-§4}
```
chapters/*.md ──► scripts\export.ps1 (Dissertation.Tools) ──► MindAttic.Export ──► ePub\MindAttic\ELENCHUS\ELENCHUS V<N>.*
     │                                                    -Publish ──► exports\ + docs\elenchus-at-scale.md (Pages)
references/ (VERIFICATION.md, UNRETRIEVED.md, research-notes/) ◄──► Appendix A ledger
```
### 4.1 Files
- `chapters/00` front matter; `01`–`08` body chapters; `80-references.md`; `90-appendix-verification-ledger.md`.
- `academic.json`, `export.json`, `scripts/export.ps1` — the Dissertation.Tools configuration and shim.
- `.github/workflows/docs.yml` — the Pages caller.

### 4.2 Domain model
- **Research question** (Section 1.4), **condition** (the five above), **objective** (an instructor's learning
  objective sampled by the examination), **verification level** (full text, abstract or publisher page, record).

### 4.3 Key procedures
- Export and publish: `powershell -File scripts\export.ps1 -Publish`.
- Word count: `powershell -File ..\Dissertation.Tools\scripts\Measure-Words.ps1 -ProjectRoot .`

## 5. The Laws {#DEAS-§5}
Inherits `MindAttic.HouseRules.md` by reference, and Dissertation.Tools `DESIGN.md` conventions.
1. {#DEAS-LAW-1} Citations are APA 7, inline; never present an unopened source as verified.
2. {#DEAS-LAW-2} Adding a citation adds its reference entry, its ledger level and its research note.
3. {#DEAS-LAW-3} Never hand-edit an export; edit the chapters and re-export.
4. {#DEAS-LAW-4} Every review or drafting pass appends its own ledger section; corrections are numbered and never
   renumbered.
5. {#DEAS-LAW-5} State a weakness as a limitation rather than paper over it.

## 6. Verified state {#DEAS-§6}
Front matter, Chapters 1–6, references (83 works) and Appendix A drafted; 41,894 body words (22 November 2026).
Chapters 7 and 8 are outlines. Extracted from Gadfly (3244fc1).

## 7. Active frontier {#DEAS-§7}
`docs/RELEASE.md`: MS-44 "Elenchus at Scale submitted manuscript".

## 8. Quality bar {#DEAS-§8}
A chapter is done when it is full prose (no "Status: outline" marker), every citation is in the reference list and
Appendix A at its level, cross-references resolve, and a ledger section records the pass that wrote it.

## 9. Glossary {#DEAS-§9}
- **Elenchus** — Socratic questioning that exposes inconsistency in a respondent's beliefs.
- **Synthetic examiner** — a system of language models that questions a student aloud and judges the answers.
- **Gadfly** — the working exam application used as the case.
- **Ledger** — Appendix A, the source verification and corrections record.
