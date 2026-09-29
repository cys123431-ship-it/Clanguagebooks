# PHASE 1 HANDOFF

## Goal

Skeleton-first: textbook (primary) + K&R (enhancement) -> our C-part TOC + chapter spec. No Korean prose writing in this phase.

## Current status

- PHASE 1 checkpoints: 7 / 8 (8 = Ch01 body writing: NOT started, must stay unchecked).
- All 7 phase1 docs exist. Ch01 body NOT written (forbidden this phase).

## Completed files

- docs/phase1/01-textbook-outline.md — 17/17 ch, sections+Labs+MiniProjects, book pp. verified.
- docs/phase1/02-kr-outline.md — Ch1-8 + App A/B/C, titles verbatim.
- docs/phase1/03-crosswalk.md — ~60 concept rows, CORE/ENHANCE/ADD/ADV/LEGACY.
- docs/phase1/04-gap-analysis.md — A/B/C lists with verdicts.
- docs/phase1/05-proposed-c-book-toc.md — PART 1-8 draft + DS prereqs.
- docs/phase1/06-chapter-specification.md — 16-item template + code/exercise rules.
- README.md — checkpoints 2-7 checked, progress 7/8.

## Incomplete files

- None structural. Quality TBD at writing phase: 3 approx titles in 01 (marked), Adv-Topic bodies unsampled.

## Source files

- `c언어 압축 (1).pdf` (750 pp, image-only, no text layer/bookmarks). TOC: PDF pp.10-17. Body spot: PDF ~455, ~595.
- `C_Programming.pdf` (288 pp, image-only). TOC: PDF pp.7-9. Second Edition, K&R, Prentice Hall 1988 (verified title/copyright pages).
- Both on user Desktop; NOT in repo (copyright). Never commit PDFs.

## Important decisions

- textbook = primary skeleton; K&R = enhancement only; no paragraph/code/exercise copying.
- Modern-C: minimal boxes only (no C23 survey). DS/Algo bodies deferred. Ch8 UNIX = LEGACY-adapt.
- Token policy kept: tables/bullets, EN analysis allowed, no polished Korean prose.

## Uncertain items

- 01: 3 titles approx (Ch03 MiniProject noun, Ch05 5.2-Lab noun, Ch08 8.5-Lab noun) — re-verify from scan at writing.
- 01: Ch08/Ch09/Ch17 "Advanced Topic" body unsampled (page nos. 353/393/736).
- Legend `(i)` = inferred-from-title labels; low risk but confirm against body when writing.

## OCR / PDF issues

- No text layer in either PDF; no bookmarks. TOC+spot-checks read via rendered images (scale 1.2-2.0).
- No OCR engine in env (no tesseract). Full-body OCR deferred; not needed for skeleton.
- Render PNGs kept in local work dir only; do NOT commit.

## Next exact task

1. `git log -3 --oneline` to confirm tip.
2. PHASE 1 item 8: write Chapter-spec brief header for our Ch01, then draft body per 06-template (separate turn).
3. Or: sample Adv-Topic bodies (pp.353/393/736, PDF+2) to close uncertainty.

## README status

- Updated this turn: items 2-7 checked, bar 7/8. Item 8 unchecked. Overall book bar stays 0% (pre-body).

## Last known commit

- 908a181 docs: analyze textbook+K&R structure, crosswalk, gaps, TOC draft, chapter spec
- Plus 1 follow-up commit this turn (HANDOFF + README). Verify: `git log -3 --oneline`.

## Notes for next AI

- Keep docs compact; never paste book prose/code. Titles + labels only.
- Final Korean prose is a later phase; do not polish Korean now.
- Push target: origin main. Repo has single branch main.
