# Elenchus at Scale

*Socratic Oral Assessment by Synthetic Examiners*

**Author:** MindAttic.
**Status:** Working draft (in progress). 41,894 words of body text across eight chapters (46,989 with the front matter and Appendix A; the reference list, about 2,400 more, is not counted). Chapters 7 and 8 are still early drafts. Citations are APA 7, with verification levels recorded in Appendix A. (Word counts: whitespace-separated words in the committed `chapters/*.md`, with LaTeX math, code blocks, comments and link targets removed; body is chapters 01 to 08, the total adds the front matter and Appendix A, and neither includes `80-references.md`. Counted 22 November 2026.)

## Thesis in one paragraph

A Socratic oral examination conducted by synthetic examiners — language models that question a student aloud, write each follow-up from the student's own previous answer, and judge the answers against the instructor's material — is a procedure for gathering evidence about understanding. Using [Gadfly](https://github.com/mindattic/Gadfly) as its case, the dissertation argues that whether that evidence is fit to inform a grade turns less on the capability of the underlying models than on five conditions: wide sampling across the instructor's objectives, scoring anchored to fixed rubrics rather than free-floating model judgment, controls for speaking anxiety, accent and transcription error, blind human grading with reconciliation, and integrity signals kept as context for a human grader rather than as automated verdicts. It reviews six literatures (the Socratic elenchus as assessment, oral examination validity and reliability, dynamic assessment, LLM-as-judge reliability, speaking-anxiety and fairness confounds, and academic integrity/proctoring evidence) against a recorded source-verification ledger, and designs the empirical test that would show whether a system meets these conditions. It does not claim Gadfly already meets them.

## Read it

- **Online:** https://mindattic.github.io/ElenchusAtScale/ (the full text as one page, under Docs)
- **By chapter:** `chapters/`

| File | Contents |
|---|---|
| `00-front-matter.md` | Abstract |
| `01-introduction.md` | Chapter 1: Introduction |
| `02-literature.md` | Chapter 2: Literature Review |
| `03-formal-model.md` | Chapter 3: A Formal Model of Evidence-Gathering by Questioning |
| `04-gadfly-method.md` | Chapter 4: The Gadfly Method |
| `05-validity-fairness-integrity.md` | Chapter 5: Validity, Fairness and Integrity |
| `06-limitations.md` | Chapter 6: Limitations and Objections |
| `07-empirical-test-design.md` | Chapter 7: The Design of an Empirical Test |
| `08-conclusion.md` | Chapter 8: Conclusion |
| `80-references.md` | References |
| `90-appendix-verification-ledger.md` | Appendix A: Source Verification Ledger |

## History

Started inside [`mindattic/Gadfly`](https://github.com/mindattic/Gadfly) as `dissertation/` (GAD-T256), using the conventions [Synthetic Exchange Theory](https://github.com/mindattic/SyntheticExchangeTheory) had already worked out. Extracted into this standalone repo (GAD-T417) so the dissertation's own history, CI and GitHub Pages site are no longer coupled to Gadfly's exam-application deploys; no functional change to any chapter, note, ledger or export.

## Toolset

Export, publish, word-count, scaffolding, verification-ledger and research-note conventions are shared with Synthetic Exchange Theory through the [Provenance](https://github.com/mindattic/Provenance) toolkit (its `DESIGN.md` is the convention of record), cloned beside this repo as `..\Provenance`. `academic.json` configures it for this manuscript.

```powershell
powershell -File scripts\export.ps1                 # export (MindAttic.Export, configured by export.json)
powershell -File scripts\export.ps1 -Publish         # also copy the newest bundle into exports\ and docs\elenchus-at-scale.md
powershell -File ..\Provenance\scripts\Measure-Words.ps1 -ProjectRoot .
```

Never hand-edit an export: edit the chapters under `chapters/`, then re-export.

## Verification

Citations are APA 7, inline. No source is cited as verified unless it was read at the level recorded in Appendix A (`chapters/90-appendix-verification-ledger.md`); `references/VERIFICATION.md` and `references/UNRETRIEVED.md` track status and gaps, and `references/research-notes/` holds the per-source notes.

## License

This repo has no LICENSE file. All rights reserved.
