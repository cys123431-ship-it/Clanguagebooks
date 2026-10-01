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
- Chapter 3 solution file: **APPROVED (manager final approval 2026-10-01)** (`book/solutions/part1/chapter03-solutions.md`). Content review and GCC/MSVC verification passed; exercises 1–12 covered. Approval history below retained; approved file unchanged in Chapter 4 work.
- Chapter 4 manuscript: **Draft 1 / manager review pending** (`book/part1/chapter04-variables-data-types.md`), architecture Part 2. Seven complete examples passed actual GCC/MSVC builds and executions; 14 original exercises. Details in the Chapter 4 section below.
- Final-approved chapters: **3**. No Chapter 4 solutions or Chapter 5 work.
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
- `book/solutions/part1/chapter03-solutions.md` — Chapter 3 APPROVED solutions: exercises 1–12; content review and dual-toolchain verification passed.
- `book/part1/chapter04-variables-data-types.md` — Chapter 4 Draft 1 manuscript: §4.1–4.5, required boxes, seven original complete programs, conceptual memory diagram, 14 exercises; manager review pending.
- README.md — setup/kickoff 8/8; Chapters 1–3 manuscript+solutions APPROVED; Chapter 4 Draft 1 / manager review pending; final-approved chapters = 3.

## Incomplete files

- Chapter 1 manuscript and Chapter 1 solution manuscript are both manager-approved.
- Chapters 1–3 manuscripts and solutions are **APPROVED**. Chapter 4 Draft 1 awaits manager review; its GCC/MSVC verification is complete. No Chapter 4 solutions or Chapter 5 body started.
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

**Manager review of Chapter 4 Draft 1.**

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
- Chapter 3 manuscript and solutions are APPROVED; existing verification evidence remains intact.
- Chapter 4 manuscript is Draft 1 / manager review pending, with seven dual-toolchain verified examples and 14 exercises. Chapter 4 solutions are not created.
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

- Architecture is binding. Chapter 4 belongs to Part 2; its explicit task-specified file path remains `book/part1/chapter04-variables-data-types.md`. No architecture redesign was needed.
- Chapters 1–3 manuscripts and solutions are APPROVED and locked. Next is manager review of Chapter 4 Draft 1. Do not create Chapter 4 solutions before its manuscript approval or start Chapter 5 in this task.
- Dated sections below preserve historical statuses; Current status and the final Chapter 4 section describe the present state.
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

## Chapter 3 solution Draft 1 — manager content review

- Date: 2026-09-30
- Manager reviewed `book/solutions/part1/chapter03-solutions.md` end-to-end against the approved Chapter 3 exercise set.
- Content verdict: **PASS pending MSVC gate**. No substantive rewrite is required.
- Coverage verified: exercises 1–12 and every subquestion; Exercise 12 remains `〔심화·도전〕`.
- Technical checks passed: program components and `main` status semantics; non-nesting block comments; directive-vs-statement distinction; Problem 4 has 3 arguments, `%c`→`'D'`, `%d`→`8`, and successful `printf` return 16; Problem 5 ends `19 16`; Problem 6 gives `4, 5, 33, 26, 30`; Problem 7 formats correctly; Problem 8 distinguishes successful input `0` from failed conversion; Problem 9 checks `scanf` before use; Problem 10 explains `&` as storage location/address, not an input symbol; Problems 11–12 stay within Chapter 3 scope and check every input before calculation.
- GCC verification for the two new complete solution programs is accepted: C17 `-Wall -Wextra`, 0 warnings/errors, normal/invalid/EOF paths checked.
- Remaining approval blocker: the two **new solution programs** have not yet been verified with MSVC. The earlier Chapter 3 manuscript MSVC PASS does not automatically cover these new listings.
- Required next verification: `printing_ticket.c` and `two_study_records.c` with baseline `cl /std:c17 /W4`, record actual C4996 behavior, then warnings-clean adjusted builds with `/D_CRT_SECURE_NO_WARNINGS`, plus normal/invalid/EOF runtime paths.
- Chapter 3 solutions remain **Draft 1**, not APPROVED, until this gate is closed.
- Do not start Chapter 4 before final manager approval of Chapter 3 solutions.
- Next exact task: narrow-scope MSVC verification of the two complete Chapter 3 solution programs, then manager final approval.

## Chapter 3 solution MSVC verification

- Date: 2026-09-30. Narrow verification only; the manager-passed solution explanations were not reworked.
- Starting state: clean `main`, actual HEAD/origin main **`b13a6e9a49a80eca6eae5c0a676362b96e7cdae9`**, checked with status, branch, last eight commits and fetch before editing.
- Required reading complete: Chapter 3 solutions, approved Chapter 3 manuscript, README and HANDOFF.
- Actual verification run: https://github.com/cys123431-ship-it/Clanguagebooks/actions/runs/36727322342
- Job: `109927439414`, conclusion **success**. Source commit: `5bf342bc0e9568b5815147e93449122628f21934` (temporary verifier only; solution listings unchanged from the starting commit).

### Actual Windows / MSVC environment

- GitHub-hosted **Microsoft Windows Server 2025 Datacenter**, version `10.0.26100`, build `26100`.
- Runner image environment: `ImageOS=win25-vs2026`, `ImageVersion=20260925.250.1`.
- Installed edition: **Visual Studio Enterprise 2026**, product version **18.10.2**, installation version `18.10.12217.157`. This is not a VS2022 IDE verification.
- Actual compiler banner: **Microsoft (R) C/C++ Optimizing Compiler Version 19.51.36260 for x64**.
- Actual `cl.exe`: `C:\Program Files\Microsoft Visual Studio\18\Enterprise\VC\Tools\MSVC\14.51.36231\bin\HostX64\x64\cl.exe`.
- The developer environment was selected with `vswhere` and initialized through `VsDevCmd.bat -arch=x64`; the installed `cl.exe` was actually run.

### Exact source extraction

The first complete C fence in each solution section was extracted verbatim, without changing names, whitespace, `scanf`, guards or return statements. Repository line endings were preserved during checkout. UTF-8 source bytes matched these SHA256 values before and after compilation:

| Problem | File | Bytes | SHA256 |
|---|---|---:|---|
| 11 | `printing_ticket.c` | 268 | `5b009f763a4bdb9fd7a87512c5e8840c14c02ea1b23368bcfcf16373fd124e01` |
| 12 | `two_study_records.c` | 513 | `9428c0946cd6b2d69ab4cb70e1fc0f390e148d859c94465c6a32dd6c7f1fb672` |

### Baseline first, then adjusted builds

Commands actually run, in this order for each file:

```text
cl /std:c17 /W4 printing_ticket.c
cl /std:c17 /W4 /D_CRT_SECURE_NO_WARNINGS printing_ticket.c
cl /std:c17 /W4 two_study_records.c
cl /std:c17 /W4 /D_CRT_SECURE_NO_WARNINGS two_study_records.c
```

| Program | Configuration | Build | Build exit | Warnings | Errors | C4996 | Executable produced |
|---|---|---|---:|---:|---:|---|---|
| 11 | Baseline `/std:c17 /W4` | PASS | 0 | 1 | 0 | Warning at line 8 | Yes |
| 11 | Adjusted, adding `/D_CRT_SECURE_NO_WARNINGS` | PASS | 0 | 0 | 0 | Absent | Yes |
| 12 | Baseline `/std:c17 /W4` | PASS | 0 | 2 | 0 | Warnings at lines 9 and 16 | Yes |
| 12 | Adjusted, adding `/D_CRT_SECURE_NO_WARNINGS` | PASS | 0 | 0 | 0 | Absent | Yes |

Actual relevant baseline diagnostics:

```text
printing_ticket.c(8): warning C4996: 'scanf': This function or variable may be unsafe. Consider using scanf_s instead. To disable deprecation, use _CRT_SECURE_NO_WARNINGS. See online help for details.
two_study_records.c(9): warning C4996: 'scanf': This function or variable may be unsafe. Consider using scanf_s instead. To disable deprecation, use _CRT_SECURE_NO_WARNINGS. See online help for details.
two_study_records.c(16): warning C4996: 'scanf': This function or variable may be unsafe. Consider using scanf_s instead. To disable deprecation, use _CRT_SECURE_NO_WARNINGS. See online help for details.
```

C4996 was a warning under these exact baseline options; both baseline executables were produced. Old `.exe`/`.obj` outputs were removed before each build, so executable presence was not inferred from a previous build. The adjustment was applied **only as an MSVC command-line definition**, after recording baseline diagnostics. `/W4` remained enabled. No source macro, `scanf_s` substitution, lower warning level or removed input check was used.

### Actual runtime results — adjusted executables

Every row below is a separate execution of the warnings-clean adjusted executable. Stdout is shown in full using `\n` to represent line endings; Windows CRLF was normalized to LF only for comparison. Stderr was empty in all cases.

| Program/case | Input | Actual stdout | Exit | Result |
|---|---|---|---:|---|
| 11 / 0 | `0` | `Sheets (0-20):\nTotal: 0 won\n` | 0 | PASS |
| 11 / 4 | `4` | `Sheets (0-20):\nTotal: 600 won\n` | 0 | PASS |
| 11 / 20 | `20` | `Sheets (0-20):\nTotal: 3000 won\n` | 0 | PASS |
| 11 / invalid | `abc` | `Sheets (0-20):\nInput failed.\n` | 1 | PASS; no total output |
| 11 / immediate EOF | No input bytes | `Sheets (0-20):\nInput failed.\n` | 1 | PASS; no total output |
| 12 / 120 + 90 | `120`, then `90` | `Morning minutes:\nAfternoon minutes:\nTotal: 3 h 30 min\n` | 0 | PASS |
| 12 / 0 + 0 | `0`, then `0` | `Morning minutes:\nAfternoon minutes:\nTotal: 0 h 0 min\n` | 0 | PASS |
| 12 / 600 + 600 | `600`, then `600` | `Morning minutes:\nAfternoon minutes:\nTotal: 20 h 0 min\n` | 0 | PASS |
| 12 / invalid first | `abc`, followed by unused `90` | `Morning minutes:\nInput failed.\n` | 1 | PASS; no afternoon prompt or total output |
| 12 / invalid second | `120`, then `abc` | `Morning minutes:\nAfternoon minutes:\nInput failed.\n` | 1 | PASS; afternoon prompt occurs, no total output |
| 12 / EOF first | No input bytes | `Morning minutes:\nInput failed.\n` | 1 | PASS; no afternoon prompt or total output |
| 12 / EOF second | `120`, then input stream closed | `Morning minutes:\nAfternoon minutes:\nInput failed.\n` | 1 | PASS; afternoon prompt occurs, no total output |

EOF was **actually tested**, not inferred: each Windows process was started through `System.Diagnostics.Process` with redirected stdin/stdout/stderr. Immediate EOF closed stdin without writing input bytes; second-input EOF wrote `120` and a newline, then closed stdin. Async output reads captured the full prompts/results and each process's actual exit code.

### Gate conclusion and cleanup

- **MSVC gate PASS: 4 actual builds, 12/12 runtime checks**, with exact source hashes unchanged. The existing solution claims about C17, `/W4`, C4996 adjustment, valid/failed input, EOF and exit statuses are confirmed.
- **Reader-facing solution body unchanged.** Its notes about MSVC being unavailable describe the original Draft 1 Linux writing session; this subsequent Windows verification is recorded in the hidden metadata and this dated handoff section. No program or explanation correction was required.
- Solution metadata now **Draft 2 / manager final approval pending**: manager content review passed, GCC verification passed, MSVC verification passed. It is **not APPROVED** yet.
- Existing GCC evidence remains accepted and was not rerun. Chapters 1–2 manuscripts/solutions and approved Chapter 3 manuscript unchanged. No architecture edits or Chapter 4 work.
- Temporary `.github/workflows/ch3-solutions-msvc-verify.yml` removed before finalization. Extracted sources, scripts, executables and JSON/log copies are outside the final repository tree. Only the three requested manuscript/status files differ from the verified starting state; cleanup removes the temporary workflow introduced solely for this run.
- README now shows content review and both verification gates complete, manager final approval pending. Final-approved chapter count remains **3**; PHASE 1 preparation/writing kickoff remains **8 / 8**.
- Next exact task: **Manager final approval of Chapter 3 solutions**.

## Chapter 3 solution manager final approval

- Date: 2026-10-01
- Approved solution file: `book/solutions/part1/chapter03-solutions.md`
- Coverage: exercises 1–12, including every subquestion; Exercise 12 retained as `〔심화·도전〕`.
- Manager content review had already passed with no substantive rewrite required.
- Verification gate: GCC and MSVC both verified the two new complete solution programs (`printing_ticket.c`, `two_study_records.c`).
- MSVC baseline reproduced C4996 as warnings; warnings-clean adjusted builds with `/D_CRT_SECURE_NO_WARNINGS` + `/W4` passed with 0 warnings/0 errors.
- Normal, invalid-first, invalid-second, and actual EOF runtime paths all matched the solution manuscript; 12/12 MSVC runtime checks passed.
- Reader-facing solution body required no factual correction after verification.
- Result: **APPROVED**. Chapter 3 manuscript + solutions are both complete for the current writing stage.
- Final-approved chapters: 3.
- Chapter 4: not started.
- Next exact task: Chapter 4 manuscript writing (`Chapter 4 — 변수와 자료형`).


## Chapter 4 Draft 1 — 변수와 자료형

### Status and scope (2026-10-01)

- Starting repository state verified before edits: clean `main`, HEAD/origin main `2cdfd6706a9fb9a5b1d154086bf534751f84a062`; `git status`, branch and last eight commits inspected. Actual remote HEAD rechecked rather than assuming the supplied SHA.
- Required README, approved Chapter 3 manuscript, HANDOFF and phase1 documents 01–07 read completely. Architecture remains binding and unchanged; no blocking contradiction found.
- Created `book/part1/chapter04-variables-data-types.md`: **Chapter 4 Draft 1 / manager review pending**. Architecture Part **2** is recorded in hidden metadata; the file follows the explicit path in this task. No duplicate Part 2 path was created.
- Retained primary textbook sequence §4.1–4.5. Added original cumulative examples, conceptual memory boxes, measured-size table, mistakes, seven summary points and **14 original exercises** with short hints only.
- All six approved Chapters 1–3 manuscript/solution files remain byte-for-byte unchanged, including their approval metadata. Current-status sections above now reflect the already recorded Chapter 3 solution approval; dated historical records remain intact.
- Final-approved chapter count remains **3**. PHASE 1 preparation/writing kickoff remains **8 / 8**. No whole-book percentage, Chapter 4 approval, Chapter 4 solution file, Chapter 5 body, PDF/DOCX manuscript or architecture changes.

### Original sources actually consulted

Page numbers are 1-based. Source PDFs and renderings stayed outside the repository.

- Primary source: `c언어 압축 (1).pdf`, 750-page image-only original. Cover visually verifies **쉽게 풀어쓴 C언어 Express, 개정4판, Visual Studio 2022, 천인국**.
- Every Chapter 4 page was rendered locally with PyMuPDF and visually inspected: **book pp.124–162 = PDF pp.126–164**, inclusive (39 pages). Covers PDF pp.1–2 also inspected. Rendered two-by-two contact sheets were read at original resolution.

| Primary area | Book pages | PDF pages | Use |
|---|---|---|---|
| §4.1 variables/constants | 124–127 | 126–129 | Named storage, declaration/assignment; original prose |
| §4.2 data types/sizeof | 127–129 | 129–131 | Type categories, storage size; size_t/%zu correction |
| §4.3 integer types/constants/representation | 129–142 | 131–144 | Type family, signed/unsigned, limits, suffixes, symbolic constants; bit-layout detail deferred |
| §4.4 floating point | 142–149 | 144–151 | Range vs precision, literal suffixes, output, approximation |
| §4.5 characters | 149–155 | 151–157 | Character codes, ASCII context, escapes; plain-char signedness corrected |
| Lab / MiniProject | 156–157 | 158–159 | Initialization discipline and integrated calculation goals only; no source code/contexts reproduced |
| Q&A / Summary / Exercise / Programming | 158–162 | 160–164 | Coverage and originality check; no exercise wording copied |

- Verified K&R **Second Edition**, Brian W. Kernighan and Dennis M. Ritchie, using the available file **`C Programming Language - 2nd Edition (OCR).pdf`**, **238 PDF pages**. Title and authors visually confirmed on PDF p.1; contents p.2 inspected. This is a reflowed/OCR copy, not the formerly catalogued 288-page `C_Programming.pdf`; PDF numbers below are not claimed as printed-book/older-scan page numbers.

| K&R section actually consulted | This copy's PDF pages | Use |
|---|---|---|
| §1.4 Symbolic Constants | 17 | Meaningful names, #define as replacement; no original temperature example copied |
| §2.1 Variable Names | 35 | Identifiers, case sensitivity, practical underscore convention |
| §2.2 Data Types and Sizes | 35–36 | Implementation-dependent sizes, char signedness, limits headers |
| §2.3 Constants | 36–39 | Integer/floating suffixes, character vs string, enum constant preview |
| §2.4 Declarations | 39 | Declaration, initialization, const; legacy uninitialized-value wording modernized |
| §2.7 Type Conversions | 41–44 | Only signed/unsigned caution and printf promotions used; full rules left to Chapter 5 |
| §4.9 Initialization, scalar introductory portion | 76 end–77 | Initial value and initialization-rule boundary; scope/storage duration/array detail not imported |
| Appendix B §B.11 Implementation-defined Limits | 234 end heading–235 body | <limits.h>/<float.h> and minimum-vs-actual limits |

K&R text was extracted from its text layer; PDF pp.35,39,235 were also visually inspected to confirm the extraction. No source paragraphs, diagrams, distinctive code or exercises were copied.

### External authoritative checks actually used

Checked 2026-10-01; external references correct/verify the textbook, not replace its teaching skeleton.

- WG14 **N1570**, public C11 committee draft, https://www.open-std.org/jtc1/sc22/wg14/www/docs/n1570.pdf — clauses for these basic rules retained in the C17 baseline:
  - §3.4.1/3 and §3.6: implementation-defined/undefined vocabulary and byte;
  - §5.2.4.2.1–2: minimum integer limits, CHAR_BIT, floating precision/range macros;
  - §6.2.5p3–10/15: basic types, character properties, corresponding unsigned range/modulo semantics, floating value sets;
  - §6.3.1.1/1.8 and §6.5.2.2p6: integer conversions and variadic argument promotions (used only as an introductory warning/printf note);
  - §6.3.2.1p1–2, §6.7.3 and §6.7.9p10: modifiable lvalue/const, indeterminate automatic initialization, the specific uninitialized read;
  - §6.4.4–5, §6.6p6, §6.7.2.2: literal types, suffixes, escapes, string distinction, integer constant expressions and enum constants;
  - §6.5p5 and §6.5.3.4p2/4/5: signed-overflow UB, sizeof bytes/char=1/size_t;
  - §7.18, §7.19, §7.20.1.1 and §7.21.6.1: C17-era bool macros, size_t declaration, optional exact-width types, printf formats including z length modifier.
- Microsoft Learn, **Storage of basic types**, https://learn.microsoft.com/en-us/cpp/c-language/storage-of-basic-types?view=msvc-170 — implementation-specific MSVC size table used as a cross-check; independent actual measurements below are the evidence for the manuscript table. No C++-only type rules imported.
- GCC manual, **Warning Options**, https://gcc.gnu.org/onlinedocs/gcc/Warning-Options.html — checked -Wall/-Wextra and format diagnostics. Compiler version actually used is recorded below.
- N2176 PDF parsing and the Microsoft /std page could not be fetched through web retrieval; neither is listed as a successfully read reference or used to fabricate verification. Actual C17 compiler invocations are recorded below.

### Required technical corrections and depth boundaries

- **B4:** required box uses indeterminate values and initialization-before-read; no meaningful "garbage value" output and no unsafe run. Static-storage rules only forward-referenced to Chapter 9.
- **C1:** required size_t/%zu box, explicit <stddef.h>, actual size experiment, char=1 versus CHAR_BIT distinction.
- **C2:** required introductory signed/unsigned comparison warning; full conversion laws remain Chapter 5.
- **C3:** signed overflow is undefined, shown only as non-executable warning material. The only wrap experiment uses unsigned int + 1U; unsigned is not sold as general overflow safety.
- **C5:** short defined/implementation-defined/undefined vocabulary box; consolidation remains Chapter 24. Source short overflow/narrowing examples were not executed or mechanically labeled as int-overflow UB; the new warning uses INT_MAX + 1 unambiguously.
- **C7:** const object versus integer constant expression; tiny #define/enum preview. No VLA or pointer const material.
- **C11:** optional C17 bool/stdint note only; fixed-width types are optional when supported. _Static_assert remains later material.
- Floating output digits are labeled as tested-environment observations; ASCII is context, not the universal C execution-character-set mandate. Every actual printf format matches its value type.

### Actual toolchains and exact listing verification

- GCC: **Ubuntu 24.04, Linux x86_64**, `gcc (Ubuntu 13.3.0-6ubuntu2~24.04) 13.3.0`; kernel observed `6.18.44`, host `6ff43ba18237`.
- MSVC: actual GitHub-hosted **Windows Server 2025**, Python reports `Windows-2025Server-10.0.26100-SP0`; image `win25-vs2026`, image version `20260922.246.2`.
- Installed IDE: **Visual Studio Enterprise 2026 18.10.1**, installation/build `18.10.12210.168`, not VS2022. Compiler banner: **cl.exe 19.51.36257 for x64**; linker `14.51.36257.0`. VsDevCmd initialized x64 host/target.
- VS2022 remains the book's primary teaching environment; this task honestly records the actual installed MSVC edition. No VS2022 run or UI click verification is claimed.
- Each complete listing A–G was extracted from the final Markdown as UTF-8 with LF plus terminal newline. MSVC received the identical bytes through the temporary workflow's embedded Base64 data. SHA-256 identity was checked against both toolchain results after the editorial pass.
- All **7 GCC builds and 7 MSVC builds PASS**, each **0 warnings / 0 errors**, all **14 executions exit 0**, stderr empty. Full stdout was captured and reviewed; five environment-independent outputs match exactly between toolchains. Size and long-range differences are intentional.
- No scanf in these examples: no C4996, no _CRT_SECURE_NO_WARNINGS define, no scanf_s, no warning suppression, no lowered warning level. No uninitialized read, signed overflow or format mismatch was run.

| Example / exact extracted file | GCC command actually run | MSVC command actually run | Build / warnings / errors / runtime exit (both) |
|---|---|---|---|
| A `rack_stock.c` | `gcc -std=c17 -Wall -Wextra rack_stock.c -o rack_stock` | `cl /std:c17 /W4 rack_stock.c /Fe:rack_stock.exe /Fo:rack_stock.obj` | PASS / 0 / 0 / 0 |
| B `type_sizes.c` | `gcc -std=c17 -Wall -Wextra type_sizes.c -o type_sizes` | `cl /std:c17 /W4 type_sizes.c /Fe:type_sizes.exe /Fo:type_sizes.obj` | PASS / 0 / 0 / 0 |
| C `integer_records.c` | `gcc -std=c17 -Wall -Wextra integer_records.c -o integer_records` | `cl /std:c17 /W4 integer_records.c /Fe:integer_records.exe /Fo:integer_records.obj` | PASS / 0 / 0 / 0 |
| D `integer_limits.c` | `gcc -std=c17 -Wall -Wextra integer_limits.c -o integer_limits` | `cl /std:c17 /W4 integer_limits.c /Fe:integer_limits.exe /Fo:integer_limits.obj` | PASS / 0 / 0 / 0 |
| E `unsigned_cycle.c` | `gcc -std=c17 -Wall -Wextra unsigned_cycle.c -o unsigned_cycle` | `cl /std:c17 /W4 unsigned_cycle.c /Fe:unsigned_cycle.exe /Fo:unsigned_cycle.obj` | PASS / 0 / 0 / 0 |
| F `floating_reading.c` | `gcc -std=c17 -Wall -Wextra floating_reading.c -o floating_reading` | `cl /std:c17 /W4 floating_reading.c /Fe:floating_reading.exe /Fo:floating_reading.obj` | PASS / 0 / 0 / 0 |
| G `character_label.c` | `gcc -std=c17 -Wall -Wextra character_label.c -o character_label` | `cl /std:c17 /W4 character_label.c /Fe:character_label.exe /Fo:character_label.obj` | PASS / 0 / 0 / 0 |

Listing SHA-256 values (same on GCC and MSVC):

| File | SHA-256 |
|---|---|
| `rack_stock.c` | `61d14ff73869c996407cd7a114cef14a42051eacb65605d67130e7b59bb62f43` |
| `type_sizes.c` | `ecc2f196ad34b135fa211a7c7f016e2e4dfe8668f4720dc5a0c01c9e883622d9` |
| `integer_records.c` | `6afbb189f3f71dbac5e3ff176b7f78cc9937609e5d3cbed222c61903029764fe` |
| `integer_limits.c` | `8f466dff15d79c6c14021b0f5f50b8454ee7945aaeced4234ab3908a5a11a66a` |
| `unsigned_cycle.c` | `ff1545e9a5f92b8f8f67ad29f2d48476934415aacbc91e9dbf89316ea1c97e4f` |
| `floating_reading.c` | `e054a2c9d4d7ef4f6a559954cbd98bd1eef7af40ef579eaf3eea29491f4447cf` |
| `character_label.c` | `46efe372a781cbaabef4e1e9d52b347b5512fabbe7ecd83003000d656bab181f` |

### Runtime stdout and observed portability measurements

The following are actual stdout records; code fences preserve tabs/line breaks. Every execution returned 0. No stdin was needed.

**A — `rack_stock.c`**

GCC and MSVC, identical:

```text
Stock: 20
Mass: 2.500 kg
```

**B — `type_sizes.c`**

GCC:

```text
char: 1
short: 2
int: 4
long: 8
long long: 8
float: 4
double: 8
long double: 16
temperature: 8
CHAR_BIT: 8
```

MSVC:

```text
char: 1
short: 2
int: 4
long: 4
long long: 8
float: 4
double: 8
long double: 8
temperature: 8
CHAR_BIT: 8
```

**C — `integer_records.c`**

GCC and MSVC, identical:

```text
Adjustment: -3
Boxes: 24
Recorded: 1200000 bytes
Archive: 5000000000 bytes
```

**D — `integer_limits.c`**

GCC:

```text
INT_MIN: -2147483648
INT_MAX: 2147483647
UINT_MAX: 4294967295
LONG_MIN: -9223372036854775808
LONG_MAX: 9223372036854775807
LLONG_MAX: 9223372036854775807
```

MSVC:

```text
INT_MIN: -2147483648
INT_MAX: 2147483647
UINT_MAX: 4294967295
LONG_MIN: -2147483648
LONG_MAX: 2147483647
LLONG_MAX: 9223372036854775807
```

**E — `unsigned_cycle.c`**

GCC and MSVC, identical:

```text
Before: 4294967295
After: 0
```

**F — `floating_reading.c`**

GCC and MSVC, identical:

```text
Sensor: 21.375
Total (2): 0.30
Total (17): 0.30000000000000004
Digits: 6 15
Maximum: 3.402823e+38 1.797693e+308
```

**G — `character_label.c`**

GCC and MSVC, identical:

```text
Label: R
Code: 82
Text: R
Quote: '
Folder: data\logs
Message: "Ready"
Column	Value
```

Observed byte counts, in order char/short/int/long/long long/float/double/long double:

- MSVC: **1 / 2 / 4 / 4 / 8 / 4 / 8 / 8**.
- GCC: **1 / 2 / 4 / 8 / 8 / 4 / 8 / 16**.
- Both CHAR_BIT=8, INT_MIN=-2147483648, INT_MAX=2147483647, UINT_MAX=4294967295, LLONG_MAX=9223372036854775807, FLT_DIG=6, DBL_DIG=15.
- LONG_MIN/LONG_MAX: MSVC **-2147483648 / 2147483647**; GCC **-9223372036854775808 / 9223372036854775807**.
- These are measurements of the stated compiler/target pairs, not universal C size/range rules. The reader-facing size table and long portability box are based on these actual observations.

### Temporary infrastructure, review and next task

- Windows verification run: https://github.com/cys123431-ship-it/Clanguagebooks/actions/runs/36814578505 — success; job ID `110216750101`. Logs contain compiler/VS metadata, complete build diagnostics, stdout, exit codes and hashes.
- Temporary workflow introduced by `0e028f9ecbcfde27a97c2f36523720cf80dce864` and removed by `3b8e5b7e0416edb9a1aa38f7d03ea4208ac375bb`. The removal tree exactly matches original baseline tree `f09c3c101da38b74291355899380d83157be9547`. No temporary workflow/test sources/binaries remain in the final repository. Scratch extraction scripts/results are outside the repository.
- Entire Chapter 4 reread for Korean clarity, correctness and depth. Every complete listing remains identical to the tested source. No VLA, unexplained global, main-form error, blanket warning suppression or unsafe executable demonstration.
- **14 exercises:** output prediction #1; find/fix #5/#10; write-from-scratch #8/#14; memory/size diagram #4. #14 retains 〔심화·도전〕. Questions and short hints only; no solutions created.
- **Unresolved verification: none for the claimed GCC/MSVC configurations.** Exact VS2022 execution was not performed; MSVC edition/version is explicitly recorded. Source OCR/reflow pagination differs from the older K&R catalogue. Types and floating behavior outside these tested environments are not asserted as measurements.
- Expected final content diff from the starting approved tip: only Chapter 4 manuscript, README and HANDOFF. Final manuscript commit: `docs: draft chapter 4 variables and data types`; obtain SHA from git log. Verify actual remote main after push.
- Next exact task: **Manager review of Chapter 4 Draft 1**.

## Chapter 4 manager final approval

- Date: 2026-10-01
- Approved manuscript: `book/part2/chapter04-variables-data-types.md`
- Manager review result: **APPROVED**. Draft 1 was reviewed end-to-end against the approved Chapter 4 scope, gap analysis, Chapter 3 continuity, and Chapter 5 boundary.
- Content checks passed: variable/declaration/initialization/assignment distinctions; accurate `const` treatment; `sizeof`/`size_t`/`%zu`; implementation-dependent type sizes; `<limits.h>`/`<float.h>` use; signed/unsigned preview; signed-overflow UB; unsigned modulo behavior; safe treatment of uninitialized automatic variables; floating approximation; `char` signedness; character-vs-string literals; escape sequences; optional C17 `bool`/`stdint.h` note.
- Toolchain gate passed before approval: 7 complete examples verified warnings-clean on GCC 13.3.0 (`-std=c17 -Wall -Wextra`) and MSVC 19.51.36257 (`/std:c17 /W4`), with runtime output and portability measurements recorded above.
- Exercise gate passed: 14 original exercises including output prediction, find/fix, write-from-scratch, and memory/size diagram work; no Chapter 4 solutions were created.
- Manager path correction: Chapter 4 is the first chapter of approved **PART 2**, so the manuscript was moved from the task-prompt's mistaken `book/part1/...` path to `book/part2/chapter04-variables-data-types.md`. This is a manager correction, not an authoring-agent error.
- Reader-facing Chapter 4 body required no substantive content rewrite during manager review.
- Result: **APPROVED**.
- Final-approved chapters: 4.
- Chapter 4 solutions: not yet created.
- Chapter 5: not started.
- Next exact task: create `book/solutions/part2/chapter04-solutions.md` Draft 1, then manager review before Chapter 5.
