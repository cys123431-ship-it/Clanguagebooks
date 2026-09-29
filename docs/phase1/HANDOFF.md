# PHASE 1 HANDOFF

## Goal

Textbook (primary) + K&R (enhancement) -> approved C-part architecture -> chapter-by-chapter Korean manuscript production. Architecture and writing kickoff are complete; the full book is not complete.

## Current status

- PHASE 1 setup/integration/writing-kickoff checkpoints: **8 / 8**. Checkpoint 8 is complete.
- Chapter 1 manuscript created: **Draft 1, manager review pending**, not final publication copy.
- Exact manuscript path: `book/part1/chapter01-programming-concepts.md`.
- Chapter-by-chapter manuscript production has begun. No automatic transition to PHASE 2.
- Actual starting state verified: `main`, clean, HEAD/origin main `47bf4dc117cc6c27afc11b28b986537bb69b8d2e`.
- README and all phase1 documents 01-07 read before writing. Approved 05/06 remain binding; 07 remains an unchanged historical audit.

## Completed files

- docs/phase1/01-textbook-outline.md — 17/17 ch, sections+Labs+MiniProjects, book pp. verified.
- docs/phase1/02-kr-outline.md — Ch1-8 + App A/B/C, titles verbatim.
- docs/phase1/03-crosswalk.md — ~60 rows, destinations reconciled to Ch1-24 (const-split, argv->Ch19, funcptr->Ch22, list->Ch18, stdlib->App B).
- docs/phase1/04-gap-analysis.md — FINAL verdicts (CORE/REQUIRED BOX/RECOMMENDED/ADVANCED/REFERENCE ONLY/DEFER), provenance kept.
- docs/phase1/05-proposed-c-book-toc.md — FINAL Ch1-24 + App A-D, C17/VS2022-GCC, Ch18 separate bridge, tiered DS prereqs.
- docs/phase1/06-chapter-specification.md — FINAL grouped template (MANDATORY/OPTIONAL/TOPIC-SPECIFIC) + MSVC+GCC verify rule + answer-key placeholder.
- `book/part1/chapter01-programming-concepts.md` — Chapter 1 Draft 1: 5 goals, sections 1.1-1.4, original guided examples, conceptual diagrams, mistakes table, 7 summary points, 8 original exercises with hints, Chapter 2 bridge.
- README.md — checkpoint 8 checked, setup/kickoff progress 8/8; one draft and zero final-approved chapters reported separately.

## Incomplete files

- None structural. The previously approximate titles and Advanced Topic checks were resolved against the source scan. Standing note only: `(i)` labels inferred from titles should be confirmed against body pages when each chapter is written.

## Source files

- `c언어 압축 (1).pdf` (750 pp, image-only, no text layer/bookmarks). TOC: PDF pp.10-17. Body spot: PDF ~455, ~595.
- `C_Programming.pdf` (288 pp, image-only). TOC: PDF pp.7-9. Second Edition, K&R, Prentice Hall 1988 (verified title/copyright pages).
- Both on user Desktop; NOT in repo (copyright). Never commit PDFs.

### Chapter 1 source pages actually consulted

Page numbers below are 1-based. The manuscript's HTML comments preserve provenance and content role separately.

| Source | Printed pages | PDF pages | Use |
|---|---|---|---|
| [T] Ch01 §1.1 | 18-25 | 20-27 | Program, instructions, precise procedures, reuse |
| [T] Ch01 §1.2 | 25-30 | 27-32 | Machine/assembly/high-level languages; translation |
| [T] Ch01 §1.3 | 30-34 | 32-36 | Concise C history, systems relevance, portability |
| [T] Ch01 §1.4 | 34-40 | 36-42 | Algorithms, decomposition, pseudocode and flowcharts |
| [T] Printer Lab, average Lab, maximum MiniProject | 41-43 | 43-45 | Pedagogical purposes only; new contexts, data, prose and diagrams |
| [T] Q&A / Exercise | 44-45 | 46-47 | Scope and non-copying review; no exercise text reused |
| [K] Introduction | 1-4 | 15-18 | Systems context, portability, scope of the tutorial |
| [K] Ch1 opening / §1.1 Getting Started | 5-8 | 19-22 | Small concrete tasks, creation/translation/execution distinction |
| [K] §1.2 opening only | 8-9 | 22-23 | Gradual example progression; no variables/loops syntax imported |

The original PDFs were locally rendered and their body pages read through Windows Korean OCR. Direct image inspection was unavailable in this agent session. OCR contains recognition noise; no verbatim quotations or source-code transcriptions are used. Historical digressions and dated ecosystem claims were omitted rather than reproduced.

External verification (official pages fetched and read on 2026-09-29; not substitutes for the original books):
- [E1] GCC manual, *Options Controlling the Kind of Output*, opening description of preprocessing, compilation, assembly and linking: https://gcc.gnu.org/onlinedocs/gcc/Overall-Options.html
  - Supports §1.2's layered source-to-build model. Stage internals and commands remain Chapter 2 material.
- [E2] Python documentation, *Glossary*, `bytecode` and `interpreted`: https://docs.python.org/3/glossary.html#term-bytecode and https://docs.python.org/3/glossary.html#term-interpreted
  - Supports §1.2's concrete CPython example: compilation to intermediate bytecode plus interpreter execution; no language-level compiled/interpreted dichotomy.

## Important decisions

- textbook = primary skeleton; K&R = enhancement only; no paragraph/code/exercise copying.
- Manager FINAL: C17 baseline (C23 notes only); VS2022 primary + GCC secondary; PART numbering retained (9=DS/10=Algo/11=Projects); Ch18 separate DS bridge; union split (core-brief + Ch23 revisit); func-ptrs RECOMMENDED not pre-DS; stdlib -> App B reference; no VLAs in main examples; ownership (not NULL-after-free) is Ch17 safety core.
- The former skeleton-only/no-prose constraint applied to architecture production, not this authorized body-writing task. Chapter 1 is newly written Korean textbook prose.
- This task explicitly overrides the reduced template's 2-3 exercise recommendation with 6-10 conceptual exercises; Draft 1 has 8. Architecture files were not rewritten.
- No C source examples are introduced in this conceptual chapter. MSVC/GCC compilation checks are not applicable here, not claimed as passed. Future executable examples still require both toolchains.

## Uncertain items

RESOLVED (verified 2026-09-29 vs textbook scan, rendered pages):
- Ch03 MiniProject: exact title "사각형의 둘레와 면적", book p.116. Outline corrected (was "사과형의 면적과 면적").
- Ch05 Lab (5.2): exact title "거스름돈 계산하기", book p.174. Outline corrected (was "가스요금 계산하기").
- Ch08 Lab (8.5): exact title "자동차 경주 프로그램", book p.340. Outline already correct, no change.
- Ch08 Advanced Topic: "모듈이란?" (modularization; cohesion/coupling), book p.353. Class ADVANCED.
- Ch09 Advanced Topic: "스텁 기법" (stub-based top-down test), book p.393. Class ADVANCED.
- Ch17 Advanced Topic: "수동 메모리 관리 vs 자동 메모리 관리" (manual-vs-GC; motivates free-discipline), book p.736. Class ADVANCED.

UNRESOLVED:
- Chapter 1 requires manager review of Korean pacing, conceptual accuracy, exercise difficulty and final approval. Draft 1 is not publication-approved.
- Separate instructor answer-key location remains undecided under 06; only student hints are included. No later chapter or appendix was started.
- Source-reading limitation: original-page OCR was used; a manager may visually compare source pages if exact source typography or diagram details matter. Source diagrams are not reproduced.
- Existing 01's printer Lab title reads `프린터 가장 수리 알고리즘`; body OCR on book p.41 / PDF p.43 reads `프린터 고장 수리 알고리즘`. This is an outline-title typo only; 01 was left unchanged as out of this three-file writing task.
- Standing note for later chapters: legend `(i)` = inferred-from-title labels; confirm against body when writing.

## OCR / PDF issues

- No text layer in either PDF; no bookmarks. TOC+spot-checks read via rendered images (scale 1.2-2.0).
- The earlier skeleton pass had no OCR engine configured. This writing pass used installed Windows OCR on locally rendered Chapter 1 / K&R pages; no full-book OCR was needed.
- Render PNGs kept in local work dir only; do NOT commit.

## Next exact task

**Manager review of Chapter 1 Draft 1.** Do not automatically start Chapter 2.

## Draft 1 self-review and checks

- PASS: full manuscript reread for Korean clarity, beginner scope, concise history, terminology, compiler/interpreter distinctions, algorithm-before-code progression and the Chapter 2 bridge.
- PASS: original prose, contexts, numerical data, diagrams and questions; no copied source paragraphs, code, exercise wording or diagrams.
- PASS: 5 learning goals, 7 summary points, 8 conceptual exercises; balanced Markdown fences/HTML comments; all code fences contain text rather than C.
- PASS: worked arithmetic and the locker flowchart's 0/1 boundary checked. A local verification script translated the maximum-finding procedure and compared it with the expected maximum for 3,905 nonempty inputs (lengths 1-5, values from {-8, -3, -1, 0, 4}). These checks supplement, not replace, the prose reasoning about correctness and termination.
- NOT APPLICABLE: MSVC/GCC execution, since the chapter contains no executable C examples.
- No PDF/DOCX or later chapter created. Source PDFs, OCR, rendered pages and check scripts stay outside the repository.

## README status

- Checkpoints 1-8 checked; preparation/writing kickoff = 8/8.
- Overall content percentage is not calculated from that milestone. Chapter 1 Draft 1 exists; final-approved chapters = 0.
- PHASE 1 learner-outcome completion criteria remain outstanding; PHASE 2 remains planned.

## Last known commit

- 5702048 docs: verify remaining textbook outline uncertainties
- 37f8ba9 docs: add phase1 architecture review
- dda652c docs: integrate final phase1 C book architecture
- Final manager-consistency cleanup follows these commits; inspect `git log -5 --oneline` for the current tip.
- `47bf4dc117cc6c27afc11b28b986537bb69b8d2e` was the verified starting tip for this draft. The writing commit is named `docs: draft chapter 1 programming concepts`; use `git log -1` after integration for its SHA.

## Architecture review status

- Review file: docs/phase1/07-architecture-review.md — left intact per task (audit record, do not rewrite).
- Original review verdict: NEEDS MAJOR REVISION (2 critical + 8 major). Those findings were integrated in `dda652c` and then manager-checked for consistency.
- Current architecture status: APPROVED; Chapter 1 Draft 1 written against it.
- PHASE 1 preparation/writing kickoff = 8/8; Chapter 1 manager review pending.
## Notes for next AI

- Keep architecture-analysis documents compact; manuscript prose belongs in `book/part1/chapter01-programming-concepts.md`.
- Review the existing Draft 1; do not infer approval or write Chapter 2 without the next instruction.
- Push target: origin main. Repo has single branch main.



