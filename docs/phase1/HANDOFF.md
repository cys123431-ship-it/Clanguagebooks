# PHASE 1 HANDOFF

## Goal

Textbook (primary) + K&R (enhancement) -> approved C-part architecture -> chapter-by-chapter Korean manuscript production. Architecture and writing kickoff are complete; the full book is not complete.

## Current status

- PHASE 1 setup/integration/writing-kickoff checkpoints: **8 / 8**. Checkpoint 8 is complete.
- Chapter 1 manuscript: **APPROVED (manager final approval 2026-09-30)**. Draft 2 passed final manager review without further body changes.
- Exact manuscript path: `book/part1/chapter01-programming-concepts.md`.
- Chapter 1 solution file: **APPROVED (manager final approval 2026-09-30)**.
- Exact solution path: `book/solutions/part1/chapter01-solutions.md`. Exercises 1–8 are all covered; the approved Chapter 1 manuscript remains unchanged.
- Chapter 2 manuscript: **APPROVED (manager final approval 2026-09-30)** (`book/part1/chapter02-program-development-tools.md`). Targeted manager revisions A–D passed final review.
- Chapter 2 solution file: **APPROVED (manager final approval 2026-09-30)**.
- Exact solution path: `book/solutions/part1/chapter02-solutions.md`. Exercises 1–8 are all covered; Exercise 8 remains 〔심화·도전〕.
- Chapter 3 manuscript: **APPROVED (manager final approval 2026-09-30)** (`book/part1/chapter03-c-program-components.md`). All six chapter examples passed GCC and MSVC verification; the approved manuscript remains unchanged.
- Chapter 3 solution file: **Draft 1 / manager review pending** (`book/solutions/part1/chapter03-solutions.md`). Exercises 1–12 covered; #12 retains 〔심화·도전〕. The two new complete solution programs passed GCC; MSVC is unavailable in this writing environment and their MSVC checks are NOT RUN.
- Final-approved chapters: **3**. Chapter 4 has not started.
- Chapter-by-chapter manuscript production has begun. No automatic transition to PHASE 2.
- Chapter 1 Draft 2 starting state verified: `main`, clean, HEAD/origin main `4f70ba3b8e90484da67a4c81d7a146bb9ea41ce4` (Draft 1 commit). Draft 1 started from `47bf4dc`.
- README and all phase1 documents 01-07 read before writing. Approved 05/06 remain binding; 07 remains an unchanged historical audit.

## Completed files

- docs/phase1/01-textbook-outline.md — 17/17 ch, sections+Labs+MiniProjects, book pp. verified.
- docs/phase1/02-kr-outline.md — Ch1-8 + App A/B/C, titles verbatim.
- docs/phase1/03-crosswalk.md — ~60 rows, destinations reconciled to Ch1-24 (const-split, argv->Ch19, funcptr->Ch22, list->Ch18, stdlib->App B).
- docs/phase1/04-gap-analysis.md — FINAL verdicts (CORE/REQUIRED BOX/RECOMMENDED/ADVANCED/REFERENCE ONLY/DEFER), provenance kept.
- docs/phase1/05-proposed-c-book-toc.md — FINAL Ch1-24 + App A-D, C17/VS2022-GCC, Ch18 separate bridge, tiered DS prereqs.
- docs/phase1/06-chapter-specification.md — FINAL grouped template (MANDATORY/OPTIONAL/TOPIC-SPECIFIC) + MSVC+GCC verify rule + answer-key policy (DECIDED: solutions under `book/solutions/`).
- `book/part1/chapter01-programming-concepts.md` — Chapter 1 APPROVED manuscript: 5 goals, sections 1.1-1.4, original guided examples, conceptual diagrams, mistakes table, 7 summary points, 8 original exercises with hints, Chapter 2 bridge.
- `book/solutions/part1/chapter01-solutions.md` — Chapter 1 APPROVED solution manuscript: full answers + detailed explanations for exercises 1–8.
- `book/solutions/part1/chapter02-solutions.md` — Chapter 2 APPROVED solution manuscript: full answers + detailed explanations for exercises 1–8.
- `book/part1/chapter03-c-program-components.md` — Chapter 3 APPROVED manuscript: 12 original exercises; all six examples verified on GCC and MSVC.
- `book/solutions/part1/chapter03-solutions.md` — Chapter 3 solution Draft 1: full answers + detailed explanations for exercises 1–12; manager review pending.
- README.md — checkpoint 8 checked, setup/kickoff progress 8/8; Chapters 1–2 manuscript+solutions APPROVED; Chapter 3 manuscript APPROVED, solutions Draft 1 / manager review pending; final-approved chapters = 3.

## Incomplete files

- Chapter 1 manuscript and Chapter 1 solution manuscript are both manager-approved.
- Chapter 2 manuscript and solutions and Chapter 3 manuscript are **APPROVED**. Chapter 3 solutions are **Draft 1 / manager review pending**; MSVC verification of the two new solution programs remains outstanding. Chapter 4 has not started.
- No structural files are otherwise incomplete. The previously approximate titles and Advanced Topic checks were resolved against the source scan. Standing note only: `(i)` labels inferred from titles should be confirmed against body pages when each chapter is written.

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
- **Answer-key policy (manager DECIDED, 2026-09-30):** student chapters carry questions + short hints only; full answers and detailed explanations go under `book/solutions/partN/chapterNN-solutions.md`, written only after that chapter's manuscript is approved. Recorded in 06. Applies to all later chapters.

## Chapter 1 Draft 2 — targeted manager revisions (completed)

- A. Program definition: now "instructions written so a computer performs a task"; embedded fixed values mentioned as secondary; input data explicitly separated from the program; "same program + different input -> different output" kept (§1.1, summary).
- B. Compiler/interpreter: core flow is source -> translation/build -> executable form -> execution. Compiler and interpreter are presented as implementation tools, not language categories. The CPython/bytecode material is reduced to a short `보충 (선택 읽기)` box. Build-stage details stay in Ch2.
- C. Korean line edit across §1.1-1.4: shortened long sentences, removed repeated conclusions, and cut translated-sounding phrasing. Technical content is unchanged.
- D. Maximum-temperature reasoning stays informal (the current maximum is right for the records seen so far, and the procedure terminates). No loop invariant, induction or formal proof terms were used.
- E. Exercise 8 is labeled `〔심화·도전〕` with a one-line note. All 8 exercises kept, and none contain C code. The hint box notes that full solutions are separate.
- Structure (1.1-1.4, 자주 하는 오해, 핵심 정리, 확인 문제, 다음 장에서는) unchanged. No Chapter 2 content.

### Draft 2 source verification (2026-09-30)

- The textbook PDF pages were rendered locally with the Windows.Data.Pdf API and **visually inspected** this time (not OCR). Rendered PNGs stayed in the session scratchpad and are not committed.
- Book p.41 / PDF p.43: Lab title is `프린터 고장 수리 알고리즘`. **01 outline typo fixed** (was `프린터 가장 수리 알고리즘`).
- Book p.19 / PDF p.21: the textbook defines a program as a list of instructions designed to perform a specific task. This supports Revision A (instruction-centered definition).
- Book p.29 / PDF p.31: the textbook describes conversion to machine code via "컴파일러 또는 인터프리터". This is consistent with the Draft 2 wording that treats both as tools. The textbook itself does not discuss mixed implementations, so the CPython note stays [E2]-sourced.
- No re-OCR or full-chapter reanalysis was done. K&R was not re-consulted, because no K&R-derived claim changed.

## Uncertain items

RESOLVED (verified 2026-09-29 vs textbook scan, rendered pages):
- Ch03 MiniProject: exact title "사각형의 둘레와 면적", book p.116. Outline corrected (was "사과형의 면적과 면적").
- Ch05 Lab (5.2): exact title "거스름돈 계산하기", book p.174. Outline corrected (was "가스요금 계산하기").
- Ch08 Lab (8.5): exact title "자동차 경주 프로그램", book p.340. Outline already correct, no change.
- Ch08 Advanced Topic: "모듈이란?" (modularization; cohesion/coupling), book p.353. Class ADVANCED.
- Ch09 Advanced Topic: "스텁 기법" (stub-based top-down test), book p.393. Class ADVANCED.
- Ch17 Advanced Topic: "수동 메모리 관리 vs 자동 메모리 관리" (manual-vs-GC; motivates free-discipline), book p.736. Class ADVANCED.
- Ch01 Lab: exact title "프린터 고장 수리 알고리즘", book p.41 (visually verified 2026-09-30). Outline corrected (was "프린터 가장 수리 알고리즘").

UNRESOLVED:
- Chapter 1 manager approval: RESOLVED. Approved 2026-09-30.
- Chapter 1 solution file `book/solutions/part1/chapter01-solutions.md` is **APPROVED** and covers exercises 1–8. No later chapter or appendix was started.
- Source-reading limitation: original-page OCR was used; a manager may visually compare source pages if exact source typography or diagram details matter. Source diagrams are not reproduced.
- Standing note for later chapters: legend `(i)` = inferred-from-title labels; confirm against body when writing.

## OCR / PDF issues

- No text layer in either PDF; no bookmarks. TOC+spot-checks read via rendered images (scale 1.2-2.0).
- The earlier skeleton pass had no OCR engine configured. This writing pass used installed Windows OCR on locally rendered Chapter 1 / K&R pages; no full-book OCR was needed.
- Render PNGs kept in local work dir only; do NOT commit.

## Next exact task

**Manager review of Chapter 3 solution Draft 1.**

## Draft 1 self-review and checks

- PASS: full manuscript reread for Korean clarity, beginner scope, concise history, terminology, compiler/interpreter distinctions, algorithm-before-code progression and the Chapter 2 bridge.
- PASS: original prose, contexts, numerical data, diagrams and questions; no copied source paragraphs, code, exercise wording or diagrams.
- PASS: 5 learning goals, 7 summary points, 8 conceptual exercises; balanced Markdown fences/HTML comments; all code fences contain text rather than C.
- PASS: worked arithmetic and the locker flowchart's 0/1 boundary checked. A local verification script translated the maximum-finding procedure and compared it with the expected maximum for 3,905 nonempty inputs (lengths 1-5, values from {-8, -3, -1, 0, 4}). These checks supplement, not replace, the prose reasoning about correctness and termination.
- NOT APPLICABLE: MSVC/GCC execution, since the chapter contains no executable C examples.
- No PDF/DOCX or later chapter created. Source PDFs, OCR, rendered pages and check scripts stay outside the repository.

## README status

- Checkpoints 1-8 checked; preparation/writing kickoff = 8/8.
- Overall content percentage is not calculated from that milestone. Chapters 1–3 manuscripts are manager-approved; final-approved chapters = 3.
- Chapter 1 solution file is APPROVED; exercises 1–8 are covered.
- Chapter 2 manuscript and solution file are APPROVED; solutions cover exercises 1–8.
- Chapter 3 manuscript is APPROVED. Its six examples passed GCC and MSVC. Chapter 3 solutions are Draft 1 / manager review pending; the new solution programs passed GCC, while their MSVC verification is NOT RUN.
- PHASE 1 learner-outcome completion criteria remain outstanding; PHASE 2 remains planned.

## Last known commit

- 5702048 docs: verify remaining textbook outline uncertainties
- 37f8ba9 docs: add phase1 architecture review
- dda652c docs: integrate final phase1 C book architecture
- Final manager-consistency cleanup follows these commits; inspect `git log -5 --oneline` for the current tip.
- `47bf4dc117cc6c27afc11b28b986537bb69b8d2e` was the verified starting tip for Draft 1.
- `4f70ba3b8e90484da67a4c81d7a146bb9ea41ce4` docs: draft chapter 1 programming concepts (Draft 1).
- Draft 2 commit: `docs: revise chapter 1 after manager review` (child of 4f70ba3). Use `git log -1` for its SHA.

## Architecture review status

- Review file: docs/phase1/07-architecture-review.md — left intact per task (audit record, do not rewrite).
- Original review verdict: NEEDS MAJOR REVISION (2 critical + 8 major). Those findings were integrated in `dda652c` and then manager-checked for consistency.
- Current architecture status: APPROVED; Chapter 1 approved manuscript written against it.
- PHASE 1 preparation/writing kickoff = 8/8; Chapter 1 manager approval complete.

## Notes for next AI

- Keep architecture-analysis documents compact; manuscript prose belongs in `book/part1/chapter01-programming-concepts.md`.
- Chapters 1–2 manuscripts and solutions and the Chapter 3 manuscript are APPROVED and locked. Chapter 3 solutions are Draft 1 / manager review pending; the next task is their manager review. Do not start Chapter 4 before completing the current review stage.
- Dated chapter sections below preserve historical statuses; Current status and the final Chapter 3 section describe the present state.
- Push target: origin main. Repo has single branch main.




## Chapter 1 manager final approval

- Date: 2026-09-30
- Approved manuscript: `book/part1/chapter01-programming-concepts.md`
- Basis: Draft 2 reviewed end-to-end against the manager-requested revisions and project architecture.
- Result: APPROVED. No further body revision required before producing the separate solution file.
- Final-approved chapters: 1.


## Chapter 1 solution Draft 1

- Created: `book/solutions/part1/chapter01-solutions.md`
- Status: **Draft 1 / manager review pending**
- Coverage: exercises 1–8, including every subquestion
- Chapter 1 manuscript: unchanged / APPROVED
- Chapter 2: not started
- Next exact task: manager review of Chapter 1 solution Draft 1

## Chapter 1 solution manager final approval

- Date: 2026-09-30
- Approved solution file: `book/solutions/part1/chapter01-solutions.md`
- Coverage: exercises 1–8, including all subquestions.
- Manager checks: arithmetic, branch cases, terminology, multiple-answer handling, and no-C-code constraint all passed.
- Result: APPROVED. Chapter 1 manuscript + solutions are both complete for the current writing stage.
- Next: Chapter 2 manuscript writing.

## Chapter 2 Draft 1

- Created: `book/part1/chapter02-program-development-tools.md`
- Status: **Draft 1 / manager review pending**. Chapter 1 manuscript and solutions unchanged (APPROVED).
- Starting state verified: `main`, clean, HEAD = origin/main = `7eab08f5aad6add53cfc9a368d732ad9ef89c379`.
- Structure: 이 장에서 배우는 것 → 2.1 프로그램은 어떻게 만들어지는가? → 2.2 전처리·컴파일·어셈블·링크 → 2.3 개발 도구의 역할 → 2.4 Visual Studio 2022에서 C 프로그램 만들기 → 2.5 C17과 컴파일 옵션 → 2.6 오류와 경고 읽기 → 2.7 첫 프로그램을 빌드하고 실행해 보기 → 자주 하는 오해 → 핵심 정리 → 확인 문제(8, #8 심화·도전) → 다음 장에서는.
- One executable example only (`hello.c`, 7 lines), explicitly marked "structure explained in Ch3". `#include`/`#define` are previewed only as directives; macro mechanics are left to Ch20.
- Visuals (original text diagrams): write-build-run cycle, source→executable flow, 5-stage toolchain pipeline, IDE/tool-role box and table, error-classification decision flow.

### Chapter 2 source pages actually consulted (rendered and visually inspected, 2026-09-30)

| Source | Printed pages | PDF pages | Use |
|---|---|---|---|
| [T] Ch02 §2.1 프로그램 개발 과정 | 50-57 | 52-59 | Lifecycle overview, source/compile/link, object file, library, build, run/debug, error kinds, Q&A on which files to keep |
| [T] §2.2 통합 개발 환경 | 57-58 | 59-60 | IDE concept; VS as primary IDE |
| [T] §2.3 설치 | 60-61 | 62-63 | "C++를 사용한 데스크톱 개발" workload |
| [T] §2.4 비주얼 스튜디오 사용하기 | 61-68 | 63-70 | Solution/project, empty project, add item typed as `hello.c`, build solution, run without debugging, console notice is not program output |
| [T] §2.5-2.6 예제 설명·응용 | 68-72 | 70-74 | Scope check only: the textbook explains the program's lines here; this book defers that to Ch3 |
| [T] §2.7 오류 수정 + 디버거 | 76-81 | 78-83 | Error vs warning, reported line may be the next line, link error ("unresolved external symbol"), logic error, debugger (not taught here) |
| [T] Mini Project 오류를 처리해보자 | 82 | 84 | Pedagogical purpose only (deliberate-error practice); new experiments written |
| [K] Ch1 opening + §1.1 Getting Started | 5-6 | 19-20 | Create-compile-load-run mechanics as the first hurdle; "depends on the system"; `.c` naming; `cc` → `a.out`. Old `main()` form not used |

- Pages 62-67 and 73-75, 83-86 were rendered and skimmed but not used as sources. No textbook or K&R prose, figures, code listings or exercises were copied.
- Textbook simplifications corrected in our text (recorded, not contradicted in reader-facing prose):
  - Library "built into the compiler" → supplied with the toolchain/OS.
  - "Compiler converts to machine code" → toolchain stage model.
  - Warning = "경미한 오류" → a signal that must be investigated.
  - Link error filed under "컴파일 시간 오류 #3" → a separate link category.
  - Sidebar "C++ tools can develop C" → same toolchain, different languages; `.c` vs `.cpp`.

### External official docs used (fetched 2026-09-30)

- [E1] GCC Overall Options: https://gcc.gnu.org/onlinedocs/gcc/Overall-Options.html. Four stages; `-E`, `-S`, `-c`, `-o`; default `a.out`.
- [E3] GCC C Dialect Options: https://gcc.gnu.org/onlinedocs/gcc/C-Dialect-Options.html. `-std=c17` = ISO C17 (2017 revision, published 2018); current default `gnu23`.
- [E4] GCC Warning Options: https://gcc.gnu.org/onlinedocs/gcc/Warning-Options.html. `-Wall` is not all warnings; `-Wextra`; `-Werror`.
- [E5] MSVC /std: https://learn.microsoft.com/en-us/cpp/build/reference/std-specify-language-standard-version. `/std:c17` since VS2019 16.8; default C mode = C89 + MS extensions; property C/C++ > Language > C Language Standard.
- [E6] MSVC warning level: https://learn.microsoft.com/en-us/cpp/build/reference/compiler-option-warning-level. `/W4` recommended for new projects; IDE default `/W3`, command-line default `/W1`; `/WX`.
- [E7] MSVC /Tc /Tp: https://learn.microsoft.com/en-us/cpp/build/reference/tc-tp-tc-tp-specify-source-file-type. `.c` → C, `.cpp`/`.cxx` → C++ by default.
- [E8] Compile a C program on the command line: https://learn.microsoft.com/en-us/cpp/build/walkthrough-compile-a-c-program-on-the-command-line. Developer command prompt; `cl hello.c` → `hello.obj` + `hello.exe`; C and C++ "similar, but not the same".
- [E9] Security Features in the CRT: https://learn.microsoft.com/en-us/cpp/c-runtime-library/security-features-in-the-crt. `_s` functions; `_CRT_SECURE_NO_WARNINGS` disables warnings but the issues remain.
- [E10] Compiler Warning C4996: https://learn.microsoft.com/en-us/cpp/error-messages/compiler-warnings/compiler-warning-level-3-c4996. Level 3; `/sdl` elevates it to an error.
- [E11] Visual Studio debugger overview: https://learn.microsoft.com/en-us/visualstudio/debugger/debugger-feature-tour. F5 = Start Debugging with the debugger attached.
- [E12] MSVC AddressSanitizer: https://learn.microsoft.com/en-us/cpp/sanitizers/asan. Mentioned only by name.

### Toolchain verification (actually run, 2026-09-30)

- `hello.c` (the exact chapter listing):
  - MSVC 19.51.36260 x64, `cl /std:c17 /W4 hello.c`: **PASS** (0 warnings; output `Hello, C!`; exit 0).
  - GCC 16.1.0 (MinGW-w64 UCRT), `gcc -std=c17 -Wall -Wextra`: **PASS** (0 warnings; output `Hello, C!`; exit 0).
- GCC stage commands `-E`/`-S`/`-c`/link: PASS. `hello.i` = 1,244 non-empty lines, which supports the "천 줄이 넘게" wording (environment-dependent). A default GCC build on Windows produced `a.exe`.
- Diagnostics quoted or described in the chapter, all reproduced:
  - Missing `;`: MSVC `C2143` at line 6; GCC `expected ';' before 'return'` at 5:26.
  - `prinft`: MSVC `C4013` warning + `LNK2019`/`LNK1120`; GCC 16 implicit-declaration **error**.
  - `int class = 0;`: valid as `.c` on both toolchains; rejected as `.cpp` (MSVC C2236…, g++ errors).
  - A declared-but-undefined function gives a pure link error on both (`LNK2019` / ld `undefined reference`).
- **Limitation:** the installed IDE is **Visual Studio Community 2026 (18.x, MSVC toolset 14.51)**, not VS2022. Compiler flags and behavior used in the chapter are the same.
  - The VS2022 menu wording in §2.4 comes from the textbook (VS2022, Korean UI) plus Microsoft docs. It was not click-verified in a VS2022 IDE.
  - Exact Korean labels are unverified for "C 언어 표준", "ISO C17(2018) 표준(/std:c17)", "SDL 검사" and the "마지막으로 성공한 빌드" prompt. The chapter warns that labels may vary.

### Draft 1 review requests — manager decisions

- VS2022 workflow retained; the menu-label limitation above remains documented. Names and locations may vary by version, update and display language; no exact VS2022 click verification is claimed.
- GCC stage-by-stage optional box and all three deliberate-error experiments retained by manager decision; the depth is accepted for Chapter 2.
- All 8 exercises retained by manager decision, including Exercise 8 as `〔심화·도전〕`. This explicitly overrides the reduced template's 2–3 recommendation for Chapter 2.

- No Chapter 3 work started. Architecture docs unchanged.
- Chapter 2 solution Draft 1 has now been created separately; the approved Chapter 2 manuscript remains unchanged.
- Next exact task: **Manager review of Chapter 2 solution Draft 1.**

## Chapter 2 Draft 2 — targeted manager revisions

- Status: **APPROVED (manager final approval 2026-09-30)**.
- Starting state verified: `main`, clean, local HEAD = remote `main` = `11c958947e5d2e60654e580ae25153ce6aec308a`.
- A. Derived build outputs wording corrected (§2.1): human-maintained source code is distinguished from object/executable outputs; rebuilding also requires dependencies and the build environment. Distribution may include runtime libraries or data files.
- B. Failed-current-build vs old executable clarified (§2.6): an error prevents the current output from being successfully produced/updated; an earlier executable may remain. The existing last-successful-build warning box is retained; related link/experiment wording and Exercise 3 items 1–2 are aligned.
- C. Runtime vs logic distinction corrected (§2.6): runtime problems prevent normal progress/completion after execution begins and need not crash; logic problems complete execution with an unintended result/behavior. Explanations, four-category table and decision flow now agree. Wrong numerical results belong to the logic example; Exercise 3's intended classifications remain unchanged.
- D. Portability wording softened (§2.5): building standard C source with multiple toolchains is one simple example; source-level portability eases moving/rebuilding, without guaranteeing unchanged operation everywhere.
- Retained: §2.1–2.7 structure, GCC `-E`/`-S`/`-c`/link optional box, 3 deliberate-error experiments, 8 exercises (Exercise 8 `〔심화·도전〕`), minimal Hello C listing, VS2022 primary/GCC secondary, C17, debugger/sanitizer depth, and all detailed MSVC/GCC verification metadata.
- Verification: full chapter reread; textual consistency, preserved sections/example/commands, and restricted three-file scope checked. Executable code and commands are unchanged, so the previously passed MSVC `/std:c17 /W4` and GCC `-std=c17 -Wall -Wextra` experiments were not rerun.
- Chapter 1 manuscript and solutions unchanged / APPROVED. Architecture documents unchanged. PHASE 1 setup/writing kickoff remains 8/8. No Chapter 2 solutions or Chapter 3 created.
- Next exact task: **Manager final approval of Chapter 2 Draft 2.**

## Chapter 2 manager final approval

- Date: 2026-09-30
- Approved manuscript: `book/part1/chapter02-program-development-tools.md`
- Basis: Draft 2 reviewed end-to-end after targeted corrections to rebuild dependencies, stale executables, runtime-vs-logic classification, and portability wording.
- Retained by manager decision: GCC stage-by-stage box, 3 deliberate-error experiments, all 8 exercises, VS2022-primary/GCC-secondary toolchain framing.
- Toolchain evidence from Draft 1 remains valid because executable examples and commands were unchanged in Draft 2.
- Result: APPROVED. No further Chapter 2 body revision required before producing the separate solution file.
- Final-approved chapters: 2.
- Next: `book/solutions/part1/chapter02-solutions.md` Draft 1.


## Chapter 2 solution Draft 1

- Created: `book/solutions/part1/chapter02-solutions.md`
- Status: **Draft 1 / manager review pending**
- Coverage: exercises 1–8, including every subquestion; Exercise 8 remains 〔심화·도전〕
- Toolchain baseline preserved: MSVC `/std:c17 /W4`; GCC `-std=c17 -Wall -Wextra`
- Chapter 1 manuscript and solutions: unchanged / APPROVED
- Chapter 2 manuscript: unchanged / APPROVED
- Chapter 3: not started
- Next exact task: manager review of Chapter 2 solution Draft 1

## Chapter 2 solution manager final approval

- Date: 2026-09-30
- Approved solution file: `book/solutions/part1/chapter02-solutions.md`
- Coverage: exercises 1–8, including all subquestions; Exercise 8 retained as `〔심화·도전〕`.
- Manager checks: build-stage order, tool-role distinctions, error classification, `.c`/`.cpp`, MSVC/GCC options, diagnostic parsing, stale-build guidance, incremental rebuild logic, and Windows-to-Unix portability explanation all passed.
- Result: APPROVED. Chapter 2 manuscript + solutions are both complete for the current writing stage.
- Final-approved chapters: 2.
- Next: Chapter 3 manuscript writing.


## Chapter 3 Draft 1 — C 프로그램 구성요소

- Created: `book/part1/chapter03-c-program-components.md`.
- Status: **Draft 1 / manager review pending**. Manuscript writing complete; dual-toolchain verification **not complete** because MSVC is unavailable in this environment.
- Starting state: clean `main`; actual local HEAD and remote main verified as `3c8af4a1eac2b89a22a91b1db759e2aa6803dfd8`, rather than assumed from the prompt. Read `git status`, branch, and last 8 commits before editing.
- Required reading complete: README, Chapters 1–2, HANDOFF, and phase1 documents 01–07. Approved 05/06 remain binding; historical 07 was not reopened or edited.
- Structure: learning goals → §3.1–3.9 → common mistakes → 7 summary points → 12 original exercises → short Chapter 4 bridge only.
- Scope: main/include/comments/directives/function-call preview/int/assignment/simple arithmetic/printf/checked scanf/integrated study-time program. No loops, arrays, pointer mechanics, user-defined helper functions, VLA, globals or advanced type rules.
- B5 REQUIRED BOX implemented: scanf return value counts successful assignments, not the number read; one `%d` requires return 1; failure ends the program before variable use. `&` is a deliberately limited storage-location preview pointing to Chapter 12.
- Examples progress: A output → B one variable → C calculation → D format examples → E checked input → F input/calculation/output. Student-facing strings use ASCII to avoid an unrelated console-encoding lesson. Prose, examples, numbers and questions are newly written.

### Original source pages actually consulted (2026-09-30)

| Source | Pages inspected | Use |
|---|---|---|
| [T] `c언어 압축 (1).pdf`, 750-page scan | Book pp.88–89 / PDF pp.90–91 | Chapter opening, first program anatomy |
| [T] §3.2–3.4 | Book pp.89–95 / PDF pp.91–97 | Comments, preprocessing/header, function/main/return |
| [T] §3.5–3.6 | Book pp.96–103 / PDF pp.98–105 | Variables, initialization, assignment, arithmetic |
| [T] §3.7 and arithmetic Lab | Book pp.104–107 / PDF pp.106–109 | Formats and value correspondence; Lab purpose only |
| [T] §3.8–3.9 | Book pp.108–112 / PDF pp.110–114 | scanf, limited address preview, VS2022 CRT note, integration |
| [T] Labs and MiniProject | Book pp.113–116 / PDF pp.115–118 | Scope and originality check; circle/exchange/average/rectangle programs not reused |
| [T] Summary/exercises/programming | Book pp.117–120 / PDF pp.119–122 | Scope and non-copying check; no question wording or listings reused |
| [K] uploaded `C Programming Language - 2nd Edition (OCR).pdf`, 238 pages | PDF pp.9–15: Ch1 opening, §1.1, relevant portion of §1.2 | Cumulative small examples, call/argument reading, comments, variables, integer arithmetic |
| [K] same OCR edition | PDF pp.137–138: §7.2 | Output formats and value types, default six digits for `%f` |
| [K] same OCR edition | PDF pp.140–142: §7.4 | Successful-assignment count and storing input through a supplied location |

- Primary scan pages were rendered and visually inspected, not inferred from the repository outline. The K&R title page was visually verified and its relevant OCR text read. K&R PDF pp.139 and parts of pp.138/142 belonging to adjacent sections were incidentally extracted, but variadic implementation/file access were not used.
- K&R source is the user-uploaded OCR edition; it is the original K&R work in a different PDF layout, not the previously catalogued 288-page `C_Programming.pdf` scan. All new page references explicitly refer to the 238-page PDF, not printed pagination.
- Actual primary §3.1/3.9 titles read **덧셈 프로그램 #1/#2**, while 01 and the prompt say 맛샘. This is a source-outline typo, not an architectural contradiction; architecture files were left unchanged as instructed. MiniProject title 사각형의 둘레와 면적 confirmed on book p.116.
- Technical corrections to source simplifications: header declarations/information distinguished from implementation; statements not universally said to end in `;`; `%f` default output corrected to six fractional digits; input checking added; `scanf` formats not claimed identical to `printf`; MSVC-specific definitions kept out of canonical sources. K&R legacy main syntax and broad array/pointer statements were not imported.

### External references actually used

Checked 2026-09-30; only authoritative sources used for technical verification:

- WG14 public C11 draft N1570: https://www.open-std.org/jtc1/sc22/wg14/www/docs/n1570.pdf — downloaded and extracted locally. Clauses §5.1.2.2.1/3 (main/start/return), §6.7.6.3p10 (void parameter list), §7.21.6.1/3 (printf formats/default precision/return), §7.21.6.2p10 and §7.21.6.4 (scanf assignment count and limits), §7.22.4.4p5 (zero success; other status values). Used for established rules retained in C17, not represented as the C17 document itself. N2176 could not be text-read because the retrieved PDF required a password; no N2176 verification is claimed.
- Microsoft Learn scanf: https://learn.microsoft.com/en-us/cpp/c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l?view=msvc-170 — return count, storage location and C4996 example.
- Microsoft Learn Security Features in the CRT: https://learn.microsoft.com/en-us/cpp/c-runtime-library/security-features-in-the-crt?view=msvc-170 — warning definition does not eliminate underlying risks.
- Microsoft Learn C4996: https://learn.microsoft.com/en-us/cpp/error-messages/compiler-warnings/compiler-warning-level-3-c4996?view=msvc-170 — CRT policy, `/sdl` severity and preprocessor-definition setting.
- Microsoft Learn `/D`: https://learn.microsoft.com/en-us/cpp/build/reference/d-preprocessor-definitions?view=msvc-170 — command-line definition without modifying source.
- Microsoft Learn `/std`: https://learn.microsoft.com/en-us/cpp/build/reference/std-specify-language-standard-version?view=msvc-170 — `.c`, ISO C17 mode.
- GCC C Dialect Options: https://gcc.gnu.org/onlinedocs/gcc/C-Dialect-Options.html — `-std=c17` verification mode.
- Microsoft main overview was also consulted, but its implementation-specific extensions/restrictions were not used as ISO C rules; main wording is based on the WG14 clauses above.

### Actual toolchain verification

Environment: Linux, GCC **13.3.0 (Ubuntu 13.3.0-6ubuntu2~24.04)**. Exact complete fenced C listings extracted unchanged to scratch `.c` files. Compiler output, program stdout and exit status checked. No source/test/PDF/image artifacts committed.

The commands actually run had this form (one for each of the six names below):

```text
gcc -std=c17 -Wall -Wextra tmp/ch3-tests/ready.c -o tmp/ch3-tests/ready
gcc -std=c17 -Wall -Wextra tmp/ch3-tests/minutes.c -o tmp/ch3-tests/minutes
gcc -std=c17 -Wall -Wextra tmp/ch3-tests/split_time.c -o tmp/ch3-tests/split_time
gcc -std=c17 -Wall -Wextra tmp/ch3-tests/formats.c -o tmp/ch3-tests/formats
gcc -std=c17 -Wall -Wextra tmp/ch3-tests/read_number.c -o tmp/ch3-tests/read_number
gcc -std=c17 -Wall -Wextra tmp/ch3-tests/study_time.c -o tmp/ch3-tests/study_time
```

| Example | Lines | GCC build | Warnings | Actual execution result | MSVC |
|---|---:|---|---:|---|---|
| A ready.c | 7 | PASS | 0 | `Study log ready.`; exit 0 | NOT RUN |
| B minutes.c | 8 | PASS | 0 | `Study: 35 min`; exit 0 | NOT RUN |
| C split_time.c | 10 | PASS | 0 | `2 h 15 min`; exit 0 | NOT RUN |
| D formats.c | 10 | PASS | 0 | Four lines: `Sessions: 3`, `Hours: 1.500000`, `Group: B`, `Topic: Review`; exit 0 | NOT RUN |
| E read_number.c | 14 | PASS | 0 | Inputs 42 and 0: correct `Read:` line, exit 0; `abc` and immediate input end: `Input failed.`, no value output, exit 1 | NOT RUN |
| F study_time.c | 16 | PASS | 0 | 135→2 h 15 min, 60→1 h 0 min, 0→0 h 0 min, 1440→24 h 0 min; exits 0. `abc` and immediate input end: failure only after prompt, no calculation output, exits 1 | NOT RUN |

- **6 complete examples; 14 executions PASS on GCC.** Full stdout including prompts/newlines and exit values matched. Exercise bug fragment intentionally not executed. Exercise solutions were not created.
- **MSVC limitation:** no `cl`, Windows CRT runtime, or configured Windows execution environment was available. Neither baseline `/std:c17 /W4` nor adjusted CRT builds were run. Chapter 2's previous Windows results do not validate these new examples. Do not claim all examples passed both toolchains.
- **C4996 handling:** canonical C sources retain `scanf` and contain no Microsoft definitions. Documented MSVC input-example commands are `cl /std:c17 /W4 /D_CRT_SECURE_NO_WARNINGS read_number.c` and the same for `study_time.c`. These are proposed verification commands, not executed evidence. No warning suppression was applied in this environment. GCC builds are independent and omit the define.
- To close the MSVC gate, first run all six exact `.c` listings with `/std:c17 /W4`, retain the actual diagnostic output, then run the two input examples with the documented `/D_CRT_SECURE_NO_WARNINGS` and repeat their valid/invalid-input tests. Record compiler version, baseline C4996 behavior, adjusted warnings and stdout/exit status. Keep `/W4`; do not globally disable warnings or silently replace scanf with scanf_s.
- VS2022 property labels are document-based, not click-verified. The manuscript retains the version/update/display-language limitation.

### Final review and remaining limitations

- Entire Chapter 3 reread: main/void/status, header vs implementation, directives vs statements, call/argument/return, initialization/assignment, integer division, formats and checked input are consistent with Chapters 1–2.
- Scope deliberately stops before Ch4 type/range teaching, Ch5 full operator rules, Ch6 conditions beyond input guard, Ch8 function mechanics and Ch12 pointer mechanics. Input examples explicitly assume small representable integers and do not claim full-line/range validation; Chapter 14 is the later expansion point.
- **12 original exercises**: output prediction (#5), find/fix ignored input failure (#9), write-from-scratch (#11–12), input-number vs scanf-return reasoning (#8), plus components/comments/directives/calls/variables/arithmetic/formats/&. #12 marked 〔심화·도전〕. Questions and short hints only.
- Chapter 1, Chapter 1 solutions, Chapter 2 and Chapter 2 solutions unchanged / APPROVED. Architecture documents unchanged. No Chapter 3 solutions, no Chapter 4 work, no PDF/DOCX manuscript.
- README updated to Chapter 3 Draft 1 / manager review pending; approved chapter count remains 2; PHASE 1 setup/writing kickoff remains **8 / 8**. Stale current-status references to Chapter 2 solution Draft 1 were reconciled to its already recorded approval; historical entries retained.
- **Unresolved publication gate:** MSVC compilation/execution and C4996 baseline/adjusted results. Manager review must not treat GCC evidence as dual-toolchain PASS.
- Next exact task: **Manager review of Chapter 3 Draft 1**.

## Chapter 3 manager review — Draft 1 content pass

- Date: 2026-09-30
- Manager reviewed the full Draft 1 manuscript against the approved Ch3 scope, Chapter 1–2 continuity, 06 writing specification, 03 crosswalk, and 04 gap analysis.
- Content verdict: **PASS pending toolchain gate**. No broad rewrite is required.
- Confirmed strengths: accurate `main`/header/directive framing; function preview kept shallow; variables/arithmetic stop before Ch4/Ch5 depth; `printf` formats are type-consistent; B5 `scanf` return checking is implemented; `&` is limited to a pointer-forward preview; input failure is separated from the value read; no `fflush(stdin)`/blanket `scanf_s` substitution; 12 original exercises satisfy output-predict/find-fix/write-from-scratch requirements.
- Approval blocker: the project requires examples to be verified on both GCC and MSVC. GCC evidence exists; MSVC `/std:c17 /W4` and the C4996 baseline/adjusted behavior are still unverified for the six Chapter 3 complete examples.
- Manager cleanup performed separately: source-outline titles `맛샘 프로그램 #1/#2` corrected to verified `덧셈 프로그램 #1/#2`; Ch3 `&` forward reference in the crosswalk corrected from Ch11 to Ch12, matching the approved final TOC.
- Chapter 3 content review gate was closed after MSVC verification; see final approval record below.
- MSVC verification completed successfully; final manager approval recorded below.


## Chapter 3 MSVC verification — gate closed

- Date: 2026-09-30.
- Verification environment: GitHub-hosted **Microsoft Windows Server 2025** runner, image `windows-2025-vs2026` version `20260925.250.1`.
- Installed toolchain selected by `vswhere`: **Visual Studio Enterprise 2026 18.10.2**.
- `cl.exe`: `C:\Program Files\Microsoft Visual Studio\18\Enterprise\VC\Tools\MSVC\14.51.36231\bin\HostX64\x64\cl.exe`.
- Compiler banner: **Microsoft (R) C/C++ Optimizing Compiler Version 19.51.36260 for x64**.
- The exact six complete fenced C listings in `book/part1/chapter03-c-program-components.md` were extracted unchanged before compilation. No `scanf_s` substitution, source macro insertion, warning-level reduction, or return-check removal was used.

### A–D baseline build and runtime

| Example | Command | Build | Warnings | Errors | Actual stdout | Exit |
|---|---|---|---:|---:|---|---:|
| A `ready.c` | `cl /std:c17 /W4 ready.c` | PASS | 0 | 0 | `Study log ready.` | 0 |
| B `minutes.c` | `cl /std:c17 /W4 minutes.c` | PASS | 0 | 0 | `Study: 35 min` | 0 |
| C `split_time.c` | `cl /std:c17 /W4 split_time.c` | PASS | 0 | 0 | `2 h 15 min` | 0 |
| D `formats.c` | `cl /std:c17 /W4 formats.c` | PASS | 0 | 0 | `Sessions: 3` / `Hours: 1.500000` / `Group: B` / `Topic: Review` | 0 |

### E–F scanf baseline and adjusted build

- E baseline command: `cl /std:c17 /W4 read_number.c`
  - Result: **PASS**, exit 0; warnings **1**, errors **0**.
  - Actual diagnostic: `read_number.c(7): warning C4996: 'scanf': This function or variable may be unsafe...`
  - Link completed and `read_number.exe` was produced.
- E adjusted command: `cl /std:c17 /W4 /D_CRT_SECURE_NO_WARNINGS read_number.c`
  - Result: **PASS**, exit 0; warnings **0**, errors **0**.
- F baseline command: `cl /std:c17 /W4 study_time.c`
  - Result: **PASS**, exit 0; warnings **1**, errors **0**.
  - Actual diagnostic: `study_time.c(7): warning C4996: 'scanf': This function or variable may be unsafe...`
  - Link completed and `study_time.exe` was produced.
- F adjusted command: `cl /std:c17 /W4 /D_CRT_SECURE_NO_WARNINGS study_time.c`
  - Result: **PASS**, exit 0; warnings **0**, errors **0**.
- Actual baseline behavior in this environment: C4996 is a **warning**, not an error, under the exact command-line `/std:c17 /W4` configuration. The documented `/D_CRT_SECURE_NO_WARNINGS` method removes that diagnostic while preserving `/W4`.

### Runtime verification

- E `read_number.exe` after the adjusted warnings-clean build:
  - input `42` → `Enter an integer:` then `Read: 42`; exit **0**.
  - input `0` → `Enter an integer:` then `Read: 0`; exit **0**.
  - input `abc` → `Enter an integer:` then `Input failed.`; no `Read:` output; exit **1**.
  - immediate EOF → `Enter an integer:` then `Input failed.`; no `Read:` output; exit **1**.
- F `study_time.exe` after the adjusted warnings-clean build:
  - `135` → `Study: 2 h 15 min`; exit **0**.
  - `60` → `Study: 1 h 0 min`; exit **0**.
  - `0` → `Study: 0 h 0 min`; exit **0**.
  - `1440` → `Study: 24 h 0 min`; exit **0**.
  - `abc` → `Input failed.`; no calculation result; exit **1**.
  - immediate EOF → `Input failed.`; no calculation result; exit **1**.
- EOF was actually tested by starting each Windows process with redirected standard input and immediately closing its stdin stream. It was not inferred.
- All runtime stdout and process exit statuses matched the manuscript expectations.

### Verification conclusion

- MSVC gate: **PASS**.
- Existing Chapter 3 claims about `/std:c17`, `/W4`, C4996, `_CRT_SECURE_NO_WARNINGS`, checked `scanf` return values, stdout, and exit values remain truthful.
- Reader-facing Chapter 3 body required **no factual correction**. Hidden verification metadata was updated before final manager approval.
- GCC evidence remains unchanged and valid; it was not rerun.
- Chapter 1–2 files remain untouched and APPROVED.
- Manager cleanup in `docs/phase1/01-textbook-outline.md` and `docs/phase1/03-crosswalk.md` was not changed.
- No Chapter 3 solution file or Chapter 4 work was created.
- Next exact task: **Create `book/solutions/part1/chapter03-solutions.md` Draft 1, then manager-review it before Chapter 4.**

## Chapter 3 manager final approval

- Date: 2026-09-30
- Approved manuscript: `book/part1/chapter03-c-program-components.md`
- Basis: Draft 1 passed manager content review; the remaining dual-toolchain gate was then closed with actual MSVC 19.51.36260 verification on Windows Server 2025 / Visual Studio Enterprise 2026 18.10.2.
- Toolchain result: GCC and MSVC both verified all six complete examples. MSVC baseline `scanf` builds reproduced C4996 as a warning; `/D_CRT_SECURE_NO_WARNINGS` + `/W4` produced 0 warnings/0 errors for the input examples; valid/invalid/EOF runtime behavior matched the manuscript.
- Reader-facing body required no correction after MSVC verification.
- Result: **APPROVED**.
- Final-approved chapters: 3.
- Chapter 3 solutions: not yet created.
- Chapter 4: not started.
- Next exact task: create `book/solutions/part1/chapter03-solutions.md` Draft 1, then manager review before Chapter 4.

## Chapter 3 solution Draft 1

- Date: 2026-09-30.
- Created: `book/solutions/part1/chapter03-solutions.md`.
- Status: **Draft 1 / manager review pending**. The solution file is not approved yet.
- Starting state: clean `main`; after fetch/fast-forward, actual HEAD = origin/main = `70d54ce3a67fa5669cc27e6f37e83c8e2cb433bb`. `git status`, current branch and last eight commits were checked before editing.
- Required reading complete: README, approved Chapter 3 manuscript, approved Chapter 1–2 solutions, this HANDOFF and 06 chapter specification. Answers use the approved Chapter 3 as their authority; no textbook/K&R reanalysis or new external research was needed.
- Coverage: **exercises 1–12, every subquestion**, with matching numbers/titles and separate `정답` / `상세해설` sections. Exercise 12 retains **〔심화·도전〕**.
- Key checks: return status versus screen output; non-nesting block comments; preprocessing versus runtime; three arguments and `%c`/`%d` mapping; variable trace ending in `19 16`; arithmetic `4, 5, 33, 26, 30`; `%f` result `2.500000`; input 0 succeeds while `abc` does not assign an integer; checking input before using `count`; `&` as storage location rather than an input symbol.
- Problem 9 uses a corrected code fragment. Problems **11 and 12 contain the only two complete new solution programs**, `printing_ticket.c` and `two_study_records.c`. Both retain canonical `int main(void)`, standard `scanf`, success `return 0;` and failure checks before destination-variable use. Problem 12 checks the two inputs independently before summing.
- Scope: Chapter 1–3 concepts only; small input-error guards, assumed exercise ranges and simple integer arithmetic. No loops, helper functions, arrays, pointer mechanics, global variables, VLAs, source warning definitions, `scanf_s` substitution or `fflush(stdin)`.

### Actual GCC verification of solution code

- Environment: Linux; **GCC 13.3.0 (Ubuntu 13.3.0-6ubuntu2~24.04)**.
- The complete fenced listings were extracted unchanged to scratch `.c` files. Actual commands:

```text
gcc -std=c17 -Wall -Wextra /workspace/scratch/e5a9e4a0b851/tmp/ch3-solutions-tests/printing_ticket.c -o /workspace/scratch/e5a9e4a0b851/tmp/ch3-solutions-tests/printing_ticket
gcc -std=c17 -Wall -Wextra /workspace/scratch/e5a9e4a0b851/tmp/ch3-solutions-tests/two_study_records.c -o /workspace/scratch/e5a9e4a0b851/tmp/ch3-solutions-tests/two_study_records
```

| Program | GCC build | Warnings | Errors | Complete-program runtime checks |
|---|---|---:|---:|---|
| Problem 11 `printing_ticket.c` | PASS | 0 | 0 | 5/5 PASS |
| Problem 12 `two_study_records.c` | PASS | 0 | 0 | 7/7 PASS |

All stdout, including prompts and newlines, stderr and process exit statuses were checked against expectations. Output below summarizes the result after the relevant input prompts; successful runs exited 0 and failure runs exited 1.

| Program | Input | Actual result | Exit |
|---|---|---|---:|
| 11 | `0` | `Total: 0 won` | 0 |
| 11 | `4` | `Total: 600 won` | 0 |
| 11 | `20` | `Total: 3000 won` | 0 |
| 11 | `abc` | `Input failed.`; no total output | 1 |
| 11 | immediate EOF | `Input failed.`; no total output | 1 |
| 12 | `120`, then `90` | `Total: 3 h 30 min` | 0 |
| 12 | `0`, then `0` | `Total: 0 h 0 min` | 0 |
| 12 | `600`, then `600` | `Total: 20 h 0 min` | 0 |
| 12 | first input `abc` (followed by unused `90`) | immediate failure; no afternoon prompt or total output | 1 |
| 12 | first `120`, second `abc` | failure after afternoon prompt; no total output | 1 |
| 12 | immediate EOF at first read | immediate failure; no afternoon prompt or total output | 1 |
| 12 | `120`, then EOF at second read | failure after afternoon prompt; no total output | 1 |

- **2 complete programs, 12 runtime checks PASS on GCC.** EOF tests actually used closed redirected standard input, not an assumed result.
- Supplementary checks: five temporary C17 wrappers for readable/corrected snippets in Problems 4–7 and 9, each built with `-std=c17 -Wall -Wextra`, 0 warnings/0 errors; **9 executions PASS**. Confirmed Problem 4 output and successful `printf` return 16, Problem 5 output `19 16`, Problem 6 results `4 5 33 26 30`, Problem 7 four formatted lines, and corrected Problem 9 results for 0/4/20/abc/EOF. The original unchecked-input bug fragment was not executed.
- Test script, generated sources, binaries and detailed JSON results remain in scratch, outside the repository. Only the requested manuscript/status files are committed.

### MSVC / C4996 handling and remaining limitation

- **MSVC solution verification: NOT RUN.** This Linux environment has no `cl`, `clang-cl`, Windows runtime (`wine`) or `pwsh`. No actual MSVC build or runtime claim is made for the new solution programs.
- The approved Chapter 3's earlier Windows/MSVC PASS is evidence for its six examples only; it does not verify the newly created Problem 11/12 programs.
- Baseline commands to run in an MSVC developer environment:

```text
cl /std:c17 /W4 printing_ticket.c
cl /std:c17 /W4 two_study_records.c
```

- Record each baseline's actual C4996 count/severity and build result before applying the chapter-established adjusted setting:

```text
cl /std:c17 /W4 /D_CRT_SECURE_NO_WARNINGS printing_ticket.c
cl /std:c17 /W4 /D_CRT_SECURE_NO_WARNINGS two_study_records.c
```

- Exact handling used here: **no suppression was applied**. The `/D_CRT_SECURE_NO_WARNINGS` method is documented only for these MSVC input exercises. It was not inserted into canonical source or passed to GCC. `/W4` remains required; standard `scanf` and both input checks remain unchanged.
- Remaining verification: run both MSVC baseline and adjusted builds, record compiler version/diagnostics, then repeat normal, invalid-first/invalid-second and EOF cases where applicable. Do not describe `/W4` alone as warnings-clean without its actual diagnostic record.

### Status and locked-file review

- Chapter 1 manuscript, Chapter 1 solutions, Chapter 2 manuscript, Chapter 2 solutions and **Chapter 3 approved manuscript remain unchanged / APPROVED**. Full solutions were added only to the separate solution file.
- No architecture changes. In particular, the manager-corrected `덧셈 프로그램 #1/#2` and the Chapter 12 `&` forward reference were preserved without editing 01/03.
- README updated to Chapter 3 solutions **Draft 1 / manager review pending**. Final-approved chapter count remains **3**; PHASE 1 setup/writing kickoff remains **8 / 8**. Current-status entries above were reconciled with the already recorded Chapter 3 approval; dated history remains intact.
- **No Chapter 4 work.** Expected changed files only: the Chapter 3 solution manuscript, README and HANDOFF.
- Next exact task: **Manager review of Chapter 3 solution Draft 1**.
