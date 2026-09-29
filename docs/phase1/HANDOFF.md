# PHASE 1 HANDOFF

## Goal

Skeleton-first: textbook (primary) + K&R (enhancement) -> our C-part TOC + chapter spec. No Korean prose writing in this phase.

## Current status

- PHASE 1 checkpoints: 7 / 8 (8 = Ch01 body writing: NOT started, must stay unchecked).
- Architecture review integrated this turn per manager decisions (FINAL). No body prose written.
- Note: review commit 37f8ba9 landed mid-task; rebased onto it, 07 read in full and left intact.

## Completed files

- docs/phase1/01-textbook-outline.md — 17/17 ch, sections+Labs+MiniProjects, book pp. verified.
- docs/phase1/02-kr-outline.md — Ch1-8 + App A/B/C, titles verbatim.
- docs/phase1/03-crosswalk.md — ~60 rows, destinations reconciled to Ch1-24 (const-split, argv->Ch19, funcptr->Ch22, list->Ch18, stdlib->App B).
- docs/phase1/04-gap-analysis.md — FINAL verdicts (CORE/REQUIRED BOX/RECOMMENDED/ADVANCED/REFERENCE ONLY/DEFER), provenance kept.
- docs/phase1/05-proposed-c-book-toc.md — FINAL Ch1-24 + App A-D, C17/VS2022-GCC, Ch18 separate bridge, tiered DS prereqs.
- docs/phase1/06-chapter-specification.md — FINAL grouped template (MANDATORY/OPTIONAL/TOPIC-SPECIFIC) + MSVC+GCC verify rule + answer-key placeholder.
- README.md — checkpoints 2-7 checked, progress 7/8.

## Incomplete files

- None structural. The previously approximate titles and Advanced Topic checks were resolved against the source scan. Standing note only: `(i)` labels inferred from titles should be confirmed against body pages when each chapter is written.

## Source files

- `c언어 압축 (1).pdf` (750 pp, image-only, no text layer/bookmarks). TOC: PDF pp.10-17. Body spot: PDF ~455, ~595.
- `C_Programming.pdf` (288 pp, image-only). TOC: PDF pp.7-9. Second Edition, K&R, Prentice Hall 1988 (verified title/copyright pages).
- Both on user Desktop; NOT in repo (copyright). Never commit PDFs.

## Important decisions

- textbook = primary skeleton; K&R = enhancement only; no paragraph/code/exercise copying.
- Manager FINAL: C17 baseline (C23 notes only); VS2022 primary + GCC secondary; PART numbering retained (9=DS/10=Algo/11=Projects); Ch18 separate DS bridge; union split (core-brief + Ch23 revisit); func-ptrs RECOMMENDED not pre-DS; stdlib -> App B reference; no VLAs in main examples; ownership (not NULL-after-free) is Ch17 safety core.
- Token policy kept: tables/bullets, EN analysis allowed, no polished Korean prose.

## Uncertain items

RESOLVED (verified 2026-09-29 vs textbook scan, rendered pages):
- Ch03 MiniProject: exact title "사각형의 둘레와 면적", book p.116. Outline corrected (was "사과형의 면적과 면적").
- Ch05 Lab (5.2): exact title "거스름돈 계산하기", book p.174. Outline corrected (was "가스요금 계산하기").
- Ch08 Lab (8.5): exact title "자동차 경주 프로그램", book p.340. Outline already correct, no change.
- Ch08 Advanced Topic: "모듈이란?" (modularization; cohesion/coupling), book p.353. Class ADVANCED.
- Ch09 Advanced Topic: "스텁 기법" (stub-based top-down test), book p.393. Class ADVANCED.
- Ch17 Advanced Topic: "수동 메모리 관리 vs 자동 메모리 관리" (manual-vs-GC; motivates free-discipline), book p.736. Class ADVANCED.

UNRESOLVED:
- None from prior list. Standing note: legend `(i)` = inferred-from-title labels; confirm against body when writing.

## OCR / PDF issues

- No text layer in either PDF; no bookmarks. TOC+spot-checks read via rendered images (scale 1.2-2.0).
- No OCR engine in env (no tesseract). Full-body OCR deferred; not needed for skeleton.
- Render PNGs kept in local work dir only; do NOT commit.

## Next exact task

Integrated architecture has passed manager consistency review. Next: Chapter 1 body writing. PHASE 1 remains 7/8 until writing begins.

## README status

- Updated this turn: items 2-7 checked, bar 7/8. Item 8 unchecked. Overall book bar stays 0% (pre-body).

## Last known commit

- 5702048 docs: verify remaining textbook outline uncertainties
- 37f8ba9 docs: add phase1 architecture review
- dda652c docs: integrate final phase1 C book architecture
- Final manager-consistency cleanup follows these commits; inspect `git log -5 --oneline` for the current tip.

## Architecture review status

- Review file: docs/phase1/07-architecture-review.md — left intact per task (audit record, do not rewrite).
- Original review verdict: NEEDS MAJOR REVISION (2 critical + 8 major). Those findings were integrated in `dda652c` and then manager-checked for consistency.
- Current architecture status: READY FOR CHAPTER 1 WRITING.
- PHASE 1 remains 7/8 until Chapter 1 body writing begins.
## Notes for next AI

- Keep docs compact; never paste book prose/code. Titles + labels only.
- Final Korean prose is a later phase; do not polish Korean now.
- Push target: origin main. Repo has single branch main.



