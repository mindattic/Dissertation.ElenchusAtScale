---
layer: release
status: living
---
# Elenchus at Scale — Release charter

> The one finish line this repo is working toward. Every open ticket in this repo sits under one of the epics
> below, and every epic is part of the milestone. Work that does not fit is out of scope until this milestone is
> reached (owner, 2026-11-27, MAT-T319).

## 1. What this is
*Elenchus at Scale: Socratic Oral Assessment by Synthetic Examiners* is a dissertation manuscript arguing, with
Gadfly as its case, that whether a synthetic Socratic examiner's evidence is fit to inform a grade depends on
sampling, anchored rubrics, fairness controls, blind human grading and the place of integrity signals more than on
model capability.

## 2. The milestone: Elenchus at Scale, submitted manuscript {#milestone}
- **Milestone:** MS-44, "Elenchus at Scale submitted manuscript"
- **Published means:** the finished manuscript, formatted to the chosen program's or venue's requirements, is
  submitted, and its final PDF, Word and Markdown are in `exports/` and on the Pages site.
- **The natural stopping point:** Chapters 7 (empirical test design) and 8 (conclusion) are drafted in full, the
  abstract and front matter describe the finished work, the open verification items in Appendix A are closed or
  stated as limitations, one whole-manuscript review pass is recorded in the ledger, and the manuscript is
  submitted. The thesis already states that it designs a test and reports no result, so a submitted, verified
  manuscript is complete without running the study.

## 3. Done when (acceptance checks)
Each line is also a `tickets milestone check` (build | exists | harness | signoff).
1. exists — `exports/Elenchus at Scale.pdf` holds the final export (via `scripts\export.ps1 -Publish`).
2. exists — `chapters/08-conclusion.md` is drafted (no "Status: outline" marker left in any chapter).
3. signoff — the owner confirms the manuscript was submitted, naming where and when.

## 4. Epics, in priority order
| Priority | Epic (ticket) | What it delivers | Features |
|---|---|---|---|
| 900 | DEAS-T3 Finish the chapters | Chapters 7 and 8 drafted, abstract and front matter final | DEAS-T6 Empirical test chapter (990), DEAS-T7 Conclusion (980), DEAS-T8 Abstract and front matter (970) |
| 800 | DEAS-T4 Verification and review | Ledger open items closed or stated; research notes in the repo; one full review pass | DEAS-T9 Research notes in repo (890), DEAS-T10 Open verification items (880), DEAS-T11 Whole-manuscript review (870) |
| 700 | DEAS-T5 Submission | Venue chosen, manuscript formatted, exported and submitted | DEAS-T12 Submission target (790), DEAS-T13 Formatted submission (780) |

## 5. Out of scope (not before this milestone)
Ideas and systems deliberately left out. A new request that lands here is filed `proposed`, never approved
automatically.
- Running the empirical study of Chapter 7, the Gadfly pilot, or any data collection — the dissertation designs
  the test and reports no result.
- Changes to Gadfly itself; Chapters 4 and 5 describe named commits and stay pinned to them.
- Companion papers or articles derived from the dissertation.
- Open-ended bughunts (DEAS-T2) and repo clean-up sweeps.
- Fitting the Chapter 3 model to data.

## 6. Current verified state
- Front matter, Chapters 1 to 6, the reference list (83 works) and Appendix A are drafted: 41,894 body words
  (counted 22 November 2026, README).
- Chapters 7 and 8 are outlines only (`chapters/07-empirical-test-design.md`, `chapters/08-conclusion.md`).
- Export and Pages run through Dissertation.Tools (`scripts/export.ps1`, `.github/workflows/docs.yml`); the repo
  was extracted from Gadfly (3244fc1) and renamed (9d583ad).
- `references/research-notes/README.md` still links to Gadfly's `docs/research/` with paths that no longer resolve
  in this repo.
- Open items are listed at the end of ledger sections A.6 to A.9 (measurement-theory sources, paywalled figures,
  AI Act provisions, gaze aversion, a reference transcript).

## 7. Decision record
- 2026-11-27 — charter drafted from README/AGENTS.md/chapters/ledger/git log/tickets; Legion vote: **Approve**, 8 of 9 voters (plurality quorum reached, consensus 0.89); dissent: one voter read the "NEW tasks" line under the wont-do heading as wont-do; they are kept, so no change.
- Triage: 1 open → done 0, duplicate 0, wont-do 1 (DEAS-T2 bughunt), kept 0; new 22 (3 epics DEAS-T3..T5, 8 features DEAS-T6..T13, 11 tasks DEAS-T14..T24), all approved; MS-44 active with two exists checks and a signoff.
