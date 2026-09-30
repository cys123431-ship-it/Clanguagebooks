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
- Exact solution path: `book/solutions/part1/chapter02-solutions.md`. Exercises 1–8 are all covered; Exercise 8 remains 〔심화·도전〕. No Chapter 3 work started.
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
- README.md — checkpoint 8 checked, setup/kickoff progress 8/8; Chapter 1 manuscript+solutions APPROVED; Chapter 2 manuscript APPROVED; Chapter 2 solutions Draft 1 recorded; final-approved chapters = 2.

## Incomplete files

- Chapter 1 manuscript and Chapter 1 solution manuscript are both manager-approved.
- Chapter 2 manuscript: **APPROVED** (`book/part1/chapter02-program-development-tools.md`). Chapter 2 solution file is **Draft 1 / manager review pending**. No Chapter 3 work started.
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

**Begin Chapter 3 manuscript: `Chapter 3 — C 프로그램 구성요소`.**

## Draft 1 self-review and checks

- PASS: full manuscript reread for Korean clarity, beginner scope, concise history, terminology, compiler/interpreter distinctions, algorithm-before-code progression and the Chapter 2 bridge.
- PASS: original prose, contexts, numerical data, diagrams and questions; no copied source paragraphs, code, exercise wording or diagrams.
- PASS: 5 learning goals, 7 summary points, 8 conceptual exercises; balanced Markdown fences/HTML comments; all code fences contain text rather than C.
- PASS: worked arithmetic and the locker flowchart's 0/1 boundary checked. A local verification script translated the maximum-finding procedure and compared it with the expected maximum for 3,905 nonempty inputs (lengths 1-5, values from {-8, -3, -1, 0, 4}). These checks supplement, not replace, the prose reasoning about correctness and termination.
- NOT APPLICABLE: MSVC/GCC execution, since the chapter contains no executable C examples.
- No PDF/DOCX or later chapter created. Source PDFs, OCR, rendered pages and check scripts stay outside the repository.

## README status

- Checkpoints 1-8 checked; preparation/writing kickoff = 8/8.
- Overall content percentage is not calculated from that milestone. Chapters 1–2 manuscripts are manager-approved; final-approved chapters = 2.
- Chapter 1 solution file is APPROVED; exercises 1–8 are covered.
- Chapter 2 manuscript is APPROVED; Chapter 2 solution file is Draft 1 / manager review pending and covers exercises 1–8.
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
- Chapter 1 manuscript and solutions are approved. Chapter 2 manuscript is approved and its solution file now exists as Draft 1. The next exact task is manager review of `book/solutions/part1/chapter02-solutions.md`; do not start Chapter 3 until that review is complete.
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
