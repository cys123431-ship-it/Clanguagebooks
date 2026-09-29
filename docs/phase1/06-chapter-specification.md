# Chapter Writing Specification (FINAL, manager-approved; no body prose)

- Baseline C17; verify examples on MSVC C17 AND GCC C17 before publication. No code files yet.
- 16-section template is now GROUPED, not all-mandatory.

## MANDATORY (teaching chapters)

- brief header: `Goal | Prereq secs | K&R refs | Gap IDs | VISUALs | Est. pages | DS-flag`
- learning goals (3-5 bullets, verbs; DS-prereq flag if any)
- prerequisite/connection (what is reused, what breaks if skipped)
- motivation (problem before solution, 1 concrete pain)
- core explanation + syntax (one canonical form)
- compilable example(s) (<15 lines starter; `main` returns 0; no unexplained constructs; Ch3 may use explicit "뒤에서 설명" markers for `#include`/`main`)
- common mistakes where relevant (bad pattern | symptom | cause + warnings text)
- summary (5-8 bullets mirroring goals)
- exercises (quota below)
- provenance label per block: `[T]` textbook / `[K]` K&R / `[E]` external-modern supplement
- content-role label where useful: 🟢 기본 / 🟡 보강 / 🔵 추가 / 🟣 심화

## OPTIONAL (use when topic benefits)

- execution trace (numbered steps)
- K&R enhancement (ref + purpose 1-liner; no copied code)
- modern-C portability box (C17 vs notes; [E] tagged)
- advanced-topic box (e.g. "모듈이란?", "스텁 기법", manual-vs-GC)
- debugger/tool box (e.g. loops Ch7)
- historical note (e.g. implicit-int -> App D)

## TOPIC-SPECIFIC (required only for matching chapters)

- memory diagram: Ch4/11/12/13/14/15/17/18 (addr boxes + arrows; mandatory there)
- bad/why/correct trio: pointer/memory/UB-prone chapters
- UB/safety box: Ch5/12/17/24
- draw-memory exercise: pointer/memory chapters (+1 item)
- build/toolchain steps: Ch2/21 (+ App A)
- DS-bridge checklist: Ch18 only (node/traverse/insert/free-all/head-update)

## Reduced templates

- Ch1/Ch2: goals + concepts + 1 guided example + mistakes + summary + 2-3 exercises. (Tool setup, no full 16.)
- Reference appendices (App B/C): entry format `prototype | semantics | return-errors | pitfall | where-taught`. No prose lessons, no exercises.

## Code rules (binding)

- Compilable; init all pointers; check malloc/fopen/scanf; free/close shown; ownership stated for heap;
  no unexplained globals; warnings-clean (`/W4`, `-Wall -Wextra`); beginner-vs-production labeled;
  no VLAs in main examples; `.c` files (VS `.c`-vs-`.cpp` note Ch2); portability box `_CRT_SECURE_NO_WARNINGS` vs Annex-K (Ch2/Ch14); NULL-after-free = habit note only.

## Exercise quota

- Per teaching chapter: >=1 output-predict, >=1 find/fix-bug, >=1 write-from-scratch.
- Answer-key policy (manager DECIDED): student chapter = questions + short hints only; no full solutions under the questions.
  Full answers + detailed explanations live separately under `book/solutions/`, mirroring the manuscript path:
  `book/solutions/partN/chapterNN-solutions.md` (e.g. `book/solutions/part1/chapter01-solutions.md`).
  A chapter's solution file is written only after that chapter's manuscript is manager-approved.

## K&R-use rule

- Allowed: section ref, concept label, "example purpose" 1-liner.
- Forbidden: paragraph/code/exercise copy. Quicksort/allocator/dir-list = purpose-ref only.

