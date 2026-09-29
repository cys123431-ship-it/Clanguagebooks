# PHASE 1 Architecture Review

- Reviewer role: C curriculum architecture review agent (first participation).
- Reviewed at: repo HEAD `5702048` (verified: `main`, clean tree, up to date with `origin/main`).
- Inputs read in full: README.md, HANDOFF.md, 01–06.
- Scope: architecture only. No body prose, no examples, no exercises. 05 is NOT edited; the manager decides what to adopt.
- Provenance tags used below:
  - **[SRC]**: derived from 01/02 (textbook / K&R outlines) or 03/04/05/06.
  - **[REC]**: reviewer technical/pedagogical recommendation.
  - **[EXT]**: externally verified modern-C fact (sources in §External sources).
- Chapter references: `T##` = textbook chapter, `K#.#` = K&R section, `05:Ch##` = chapter number in the proposed TOC (05).

---

## Executive assessment

The source analysis (01–03) is solid and usable. The proposed TOC (05) is **not**. While 05 reordered the textbook, it created two real prerequisite inversions: dynamic structs and linked lists come before struct fundamentals, and string implementation comes before string fundamentals. It also breaks one more dependency: `argc/argv` needs pointer arrays of strings, and it appears before strings are taught. 05's own "Dependency map" contradicts 05's chapter list, which shows the TOC was assembled inconsistently. For these specific topics, the textbook's original order (T10 arrays → T11 pointers → T12 strings → T13 structs → T14 advanced pointers → T17 dynamic memory) was already dependency-correct, and 05 made it worse.

Two things the project needs are never decided anywhere in PHASE 1:
- a **language-standard / toolchain baseline**. By default, MSVC compiles `.c` files as C89 plus extensions and has no VLAs [EXT].
- a **tiered policy for modern-C boxes**. The 04 verdicts are too coarse: many "required" items should be boxes, not core text.

Most fixes are reorders and relabels rather than new content. Chapter 1 does not depend on any of the blocked areas.

**Verdict: NEEDS MAJOR REVISION** of 05, plus targeted relabeling of 04 and 06. The fix is well defined (see §Proposed changes). Chapter 1 body writing can start as soon as the manager adopts the order and the toolchain baseline. It does not need to wait for the rest.

---

## Critical findings

### CR-1. Dynamic structs and linked lists come before struct fundamentals (prerequisite inversion) — manager hypothesis A: CONFIRMED

1. **Current design** [SRC 05]: PART 4 `05:Ch17 동적 메모리` covers "malloc family + discipline + struct-nodes + list intro (T17, K6.4-6.5)". The struct chapter `05:Ch19 구조체·공용체·열거형·typedef` comes later, in PART 5.
2. **Problem**: T17.4 (구조체를 동적 생성) and T17.5 (연결 리스트) need these, none of which is taught before 05:Ch19:
   - `struct` declaration,
   - `->`,
   - `typedef` (the node-typedef pattern),
   - self-referential struct declaration (K6.5).

   This is a hard dependency, not a stylistic one. A learner cannot read a single line of `Node *n = malloc(sizeof *n); n->next = NULL;` without struct knowledge. The textbook itself [SRC 01] places T13 before T17, so 05 introduced the inversion.
3. **Why it matters**:
   - The DS bridge is the most important hand-off in the book (README PHASE 1 completion criteria).
   - With the inversion, either the writer front-loads struct syntax inside the dynamic-memory chapter (duplication, and a later struct chapter that feels like review), or learners hit undefined terms.
   - Downstream, PART 9 (DS) inherits a weak foundation.
4. **Proposed change** [REC]:
   - Move struct fundamentals **before** dynamic memory.
   - Split the dynamic-memory chapter in two: dynamic memory itself (no structs needed), then a short **"dynamic structs → self-referential struct → linked list intro"** bridge chapter placed after both structs and dynamic memory.
   - Order: `struct → struct pointer (->) → [advanced pointers] → dynamic memory → dynamic struct → self-referential struct → linked-list intro`. Rationale: §Structures/dynamic-memory decision.
5. **Downstream impact**:
   - PART 4/5 boundaries change: strings and structs move before advanced pointers and dynamic memory, essentially restoring the textbook order.
   - The 05 chapter numbering changes.
   - The DS bridge becomes its own short chapter.
   - The chapter spec DS-flag moves to that chapter.

### CR-2. `char*`/`char[]` and string implementation come before string fundamentals; `argc/argv` comes before strings (second inversion)

1. **Current design** [SRC 05]:
   - `05:Ch14 배열-포인터 관계` includes "`char*/char[]`, string impl (K5.3/5.5, T11.6/12)".
   - `05:Ch15` includes "ptr-array" (whose canonical use is string tables, K5.6/5.8).
   - `05:Ch16` includes `argc/argv`.
   - `05:Ch18 문자와 문자열` (`'\0'`, ctype, string.h, safe input) comes **after** all of them.
2. **Problem**:
   - K5.5-style string implementation (`strcpy`/`strlen` via pointers) and the literal-mutability rule presuppose `'\0'`-terminated char arrays and string literals. Those are taught in 05:Ch18.
   - `argc/argv` is a `char *argv[]`: a pointer array of strings. It needs strings and pointer arrays.
   - This is a hard dependency, like CR-1.
3. **Why it matters**:
   - The strings chapter would either repeat 05:Ch14 content, or 05:Ch14 would silently teach string basics under a pointer title. Both damage the book's use as a reference: learners won't know where "strings" lives.
   - Separately, 05's own "Dependency map" line says `Ch10/12 arrays+strings -> Ch11/13-14 ptr (+struct) -> Ch17 heap`. That is the *correct* order, and it contradicts 05's chapter list. The TOC therefore can't be used as a writing contract as-is.
4. **Proposed change** [REC]:
   - Put strings **after** basic pointers and the pointer–array relationship, and **before** structs and advanced pointers. This matches the textbook order, T11 → T12 → T13 → T14.
   - Teach `char*` vs `char[]` and literal mutability **in the strings chapter**. It is the first place both prerequisites (decay and pointers) exist and the first place the distinction matters.
   - Move `argc/argv` to the file / program-interface chapter (see MJ-2).
5. **Downstream impact**:
   - 05:Ch14 shrinks to pure pointer↔array mechanics.
   - The strings chapter gains K5.5 as an enhancement.
   - The advanced-pointer chapter can use strings freely: pointer arrays as string tables, and the K5.9 layout contrast.

> Severity note: both are CRITICAL because they block the *final TOC* from being used as the writing order for PARTs 4–5. They do **not** block Chapter 1 writing, and both fixes are mechanical reorders.

---

## Major findings

### MJ-1. Mixed "advanced" chapter 05:Ch16 (const / volatile / void* / argc/argv / function pointers) — manager hypothesis B: CONFIRMED, with nuance

1. **Current** [SRC 05, T14.4/14.6–14.8]: one chapter bundles five unrelated concerns, inherited from T14's second half.
2. **Problem**: these topics have different prerequisites and different audiences:
   - `const` qualification is needed early. `strlen(const char *)` and `const T *` read-only parameters appear as soon as pointers are passed to functions.
   - `volatile` is a low-level / hardware concept (memory-mapped I/O, signal handlers). Beginners should not meet it next to `const`, because the pairing implies they are symmetric peers.
   - `void*` is first *needed* at `malloc` (dynamic memory), and next at generic code (`qsort`).
   - `argc/argv` is a program-interface topic that needs strings (CR-2).
   - Function pointers are an abstraction mechanism. They are useful but not mandatory before DS (see DS matrix).
   - Nuance: `void*`, `const`, and function pointers *do* meet coherently in `qsort` comparators (`int (*)(const void *, const void *)`). That meeting point is a valid chapter spine, but only after `const` and `void*` have been introduced earlier.
3. **Why it matters**:
   - A grab-bag chapter has no single learning goal, which violates 06 template item 1.
   - It also puts the core `const` pointer-parameter concept late, so earlier chapters (strings, structs) would need `const` without having taught it.
4. **Proposed change** [REC]:
   - `const` on variables → Ch "변수와 자료형" (T4.1 already previews it).
   - `const T *` parameters → pointer-basics chapter.
   - The full `const` placement table (`const int *` / `int *const` / `const int *const`) → advanced-pointers chapter.
   - `void*` basics (what it is, implicit conversion in C, no deref) → dynamic-memory chapter, at `malloc`'s return type.
   - Function pointers + callbacks + `qsort`/`bsearch` + generic `void*` programming + declaration reading + variadic functions → one coherent **"함수 포인터와 제네릭 기법"** chapter in the advanced PART.
   - `argc/argv` + exit status + `stderr` → file / program-interface chapter.
   - `volatile` → a **"저수준 C"** chapter (bit ops advanced, bit-fields, unions for hardware, `volatile`, `<stdint.h>`), which is where T16.7's hardware lab and T13.6 unions already point.
5. **Downstream impact**:
   - The 05:Ch16 chapter disappears.
   - One advanced chapter is added: function pointers / generics.
   - One advanced chapter is re-scoped: low-level C.
   - T14 content is distributed across 4 chapters, so 01's T14 mapping must be recorded in the crosswalk.

### MJ-2. `argc/argv` placement and the "program interface" gap

1. **Current**: `argc/argv` sits in 05:Ch16. `stderr`/`exit` sits in 05:Ch20 (files). 04:C8 already groups "argc/argv + exit codes + stderr" [SRC 04].
2. **Problem**: 05 splits one coherent topic, "how a C program talks to its environment," across two PARTs, and places half of it before strings.
3. **Why it matters**: command-line tools are the natural next step after files, and files are where `stderr`, `exit(EXIT_FAILURE)`, and redirection actually matter. Examples like `mycopy src dst` need both.
4. **Proposed change** [REC]: close the streams/files chapter with a section on 명령행 인자와 프로그램 종료 상태: `argc/argv`, `EXIT_SUCCESS`/`EXIT_FAILURE`, `stderr`, `perror`, and redirection as a concept. The T14 Lab "프로그램 인수 사용하기" moves there.
5. **Impact**: small. It removes one forward dependency.

### MJ-3. No language-standard / toolchain baseline decision

1. **Current** [SRC 03 A-row, 05:Ch2]: "modernize: gcc+VS both", "warnings {-Wall}". No C standard version is chosen anywhere.
2. **Problem** [EXT]:
   - MSVC compiles `.c` files in a default mode that "implements ANSI C89, but includes several Microsoft extensions" unless `/std:c11` or `/std:c17` is given (available since VS 2019 16.8).
   - MSVC does not support VLAs, and "support isn't planned."
   - Visual Studio projects often add `.cpp` files by default, which silently compiles learners' C as C++. Differences that follow: a `malloc` cast becomes required; `const int N` works as an array size in C++ but not in C.
   - GCC 14 turned implicit function declarations, implicit int, int↔pointer conversion, and incompatible pointer types into **errors** by default.
   - The textbook's `gets_s` (T12.3) and the `scanf_s` family are MSVC/Annex K–specific and non-portable to gcc/glibc.
3. **Why it matters**: without a baseline, example code will compile on one toolchain and fail or differ on the other. The README code rules ("compilable, warnings-clean") are then unverifiable. This affects Chapter 2 immediately.
4. **Proposed change** [REC]:
   - **Baseline**: ISO **C17**.
     - C99 features are used freely: `//`, declarations in `for`, `<stdbool.h>`, `<stdint.h>`, `snprintf`.
     - C11 features only in advanced boxes.
     - C23 appears as notes only.
     - No VLAs anywhere in the main text.
   - **Toolchains**: VS2022 with `/std:c17 /W4`, `.c` extension mandatory; gcc/clang with `-std=c17 -Wall -Wextra`.
   - Portability box on `_CRT_SECURE_NO_WARNINGS` vs `scanf_s`/`gets_s`. The book's standard-conforming code uses `fgets`, `scanf` with field widths, and `snprintf`.
   - Every example must be compiled on both toolchains before publication (add to 06).
5. **Impact**: Chapter 2 content and the 06 code rules change. There is **no TOC impact** beyond Chapter 2 scope.

### MJ-4. 04 gap verdicts are too coarse ("required" overused) and have omissions

1. **Current** [SRC 04]: six verdict labels. Many items are "required", with mixed granularity. For example, C12 bundles warnings, sanitizers, and gdb, all as "required, Ch02".
2. **Problem**:
   - "Required" conflates *core body text* with *mandatory 1-box warnings*.
   - Several placements overload beginners: sanitizers and a debugger in Ch02, before the learner has written a loop.
   - Some flags are wrong: alignment/padding is marked "before-DS", but DS does not need padding knowledge.
   - Several genuinely core items are missing: `size_t`/`%zu`, checking `scanf`'s return value, `getchar()` returning `int` (EOF), out-of-bounds access as UB, returning a pointer to a local, `#define`/`enum` for array sizes (C has no `const int` constant expressions), and VLA policy.
3. **Why it matters**: 04 feeds the chapter briefs (the 06 header "Gap IDs"). Mis-tiered items either overload beginner chapters or get dropped.
4. **Proposed change**: adopt the six-tier scale CORE / REQUIRED BOX / RECOMMENDED / ADVANCED / REFERENCE ONLY / DEFER and the table in §Gap-analysis corrections.
5. **Impact**: 04 needs a relabel pass (manager). The 06 chapter briefs reference the new tiers.

### MJ-5. `free(p); p = NULL;` is stated as a discipline without its limits — manager hypothesis C: CONFIRMED (the wording risk is real)

1. **Current** [SRC 04:C4]: "dangling/UAF/double-free/leak discipline + NULL-after-free", verdict required (before-DS).
2. **Problem**: presented as a discipline rule, it implies memory safety that it does not give. Details in §Specific memory-safety review.
3. **Why it matters**:
   - The DS phase is full of aliases: `prev->next`, `tail`, `cur`, tree parent pointers. A learner who believes "I nulled `p`, so I'm safe" will write use-after-free bugs through aliases, and will not understand why `free_node(Node *p) { free(p); p = NULL; }` does nothing for the caller.
   - It is also the exact bug class AddressSanitizer reports as `heap-use-after-free`.
4. **Proposed change** [REC]:
   - Make the **ownership rule** the core rule: every allocation has one owner responsible for freeing it, and after `free`, *every* pointer into that block is invalid.
   - Demote `p = NULL` to a RECOMMENDED habit, with an explicit "what it does not do" list.
5. **Impact**: wording in the dynamic-memory and DS-bridge chapter briefs. No structural change.

### MJ-6. Standard-library PART 8 as a teaching PART would duplicate contextual teaching — manager hypothesis D: CONFIRMED

1. **Current** [SRC 05 PART 8, README PART 8]:
   - "stdio/stdlib/string/ctype/math/time/assert integrated + reference section".
   - The library is already taught contextually: T8.5/8.6 (`rand`, `math.h`), T12 (`ctype`, `string.h`, conversions), T15 (`stdio` files), T16 (`assert`), T14 lab (`qsort`).
2. **Problem**: a teaching PART after PART 7 re-teaches the same functions a third time (textbook chapter, K&R enhancement, PART 8). It also sits *after* the point where learners needed those functions.
3. **Why it matters**:
   - duplication cost (pages, token budget),
   - drift risk (two explanations of `strtol` that disagree),
   - no single place for lookup.
4. **Proposed change**: Option C, hybrid. See §Standard-library architecture decision.
5. **Impact**:
   - PART 8 becomes a **reference appendix**, not a teaching PART.
   - README PART numbering shifts: DS becomes PART 8 unless the manager keeps the numbering and labels it "PART 8 (Reference)".
   - Headers with no contextual home get homes: `time.h` → Ch8 box + reference; `setjmp`/`signal` → reference only.

### MJ-7. 06 chapter template is uniformly mandatory and doesn't fit intro/reference chapters

1. **Current** [SRC 06]: 16 items, "every chapter".
2. **Problem**:
   - T01 (programming concepts) has no memory model, bad/correct code, or meaningful K&R note.
   - The library reference has none of the narrative items.
   - Items overlap: 10 "Common mistakes" vs 11 "Bad/Correct code"; 14 "Summary" vs 16 "Next bridge"; 7 "Execution flow" vs 9 "Worked example".
   - Items are missing:
     - source-tag labeling (README's 🟢/🟡/🔵/🟣 classification is never enforced in 06),
     - a dual-toolchain verification requirement,
     - optional/심화 skip markers,
     - an answer-key policy.
3. **Why it matters**: mechanical 16-slot chapters inflate page count and produce empty filler sections. Missing traceability undermines the README's own tracking rule.
4. **Proposed change**: §Chapter-template review (mandatory / optional / topic-specific split).
5. **Impact**: 06 revision only.

### MJ-8. Separate "TU/compile-vs-link preview" chapter (05:Ch11) is mis-sized and mis-ordered

1. **Current** [SRC 05]: `05:Ch11 {+} TU/compile-vs-link preview -> full in PART 6`, placed **after** `05:Ch09` (which teaches linkage and `extern`).
2. **Problem**:
   - Linkage *is defined in terms of* translation units, so a TU preview after linkage is backwards.
   - A whole chapter for a preview is also overweight.
   - Compile vs link is already introduced in T2.1 (edit → compile → link → run; link errors).
3. **Why it matters**: 9.5 (연결) becomes unteachable without "what a TU is". The extra chapter adds a thin, low-value unit to the beginner path.
4. **Proposed change** [REC]:
   - Delete 05:Ch11.
   - Ch2: preprocess → compile → link model, with error types by stage.
   - Scope/linkage chapter: a one-paragraph TU definition just before the linkage section, plus a 2-file micro-demo of `extern`/`static`. That demo is the only multi-file code before PART 7.
   - Multi-file chapter: full declaration/definition, header design, and build.
5. **Impact**: the chapter count drops by one. No content is lost.

---

## Minor findings

| ID | Finding | Recommendation |
|---|---|---|
| MN-1 | Pointer arithmetic is in `05:Ch13` (basics), separated from the array relationship (05:Ch14). Arithmetic on a pointer to a non-array object is only valid up to one-past (C17 6.5.6); teaching it without arrays invites UB demos. [SRC T11.4 before T11.6] | Teach arithmetic inside the pointer↔array chapter. Keep only `p == &x`, `*p` and parameters in basics. |
| MN-2 | Object-like `#define` is taught in T16 (preprocessor), yet arrays (T10) need a compile-time size. In C, `const int N = 10; int a[N];` is a VLA (rejected by MSVC [EXT]), not a constant array. | Introduce `#define N 10` and `enum { N = 10 }` in the variables/constants chapter (K1.4 symbolic constants already supports this). |
| MN-3 | Variadic functions (T9.7) are "moved out of Ch09 core" [SRC 03] but not placed anywhere in 05. The item is orphaned. | Place in the function-pointer / advanced-functions chapter as ADVANCED. |
| MN-4 | Bit-fields sit in the preprocessor/multi-file chapter (inherited from T16.7). They are a struct feature with implementation-defined layout. | Move to the low-level C chapter, with unions and `volatile`. |
| MN-5 | Complicated declarations (K5.12) are in the advanced-pointer core (05:Ch15, "decl-decode"). | Core: a right-left reading method for ≤2 levels (`int *a[N]`, `int (*p)[N]`, `int (*f)(int)`). The full `dcl`-style decoding is ADVANCED, in the function-pointer chapter. |
| MN-6 | The preprocessor and multi-file topics share one chapter (T16). Multi-file is a DS/project enabler and deserves its own chapter. | Split into "전처리기" and "다중 소스 파일과 빌드". |
| MN-7 | Sorting/searching in the arrays chapter (T10.4–10.5) will overlap PART 10. | Keep as array-practice labs (selection sort, linear/binary search), mark "알고리즘 PART에서 분석". No complexity theory here. |
| MN-8 | README PART 7 lists `const`, bit ops, `union`, function pointers, `argc`, complex declarations, varargs, alignment, and UB. 05 PART 7 lists only UB, surveys, and bit safety. README and 05 disagree. | Reconcile once the manager adopts the order (README edit is the manager's call). |
| MN-9 | `goto` is an "adv box" in 05, but K3.8 notes a legitimate use (breaking out of nested loops, cleanup paths). | Keep as a short box. Add "single-exit cleanup (`goto fail`)" as an ADVANCED pattern in the file / dynamic-memory error handling. |
| MN-10 | 06 minimal-example rule "no unexplained constructs" conflicts with Ch3 (`#include`, `int main(void)` must appear before being explained). | Allow explicit "뒤에서 설명" markers. |
| MN-11 | Recursion is its own chapter (05:Ch10), split from T09. | Fine. Keep it separate. Add "recursion on arrays (binary search)" as a forward reference to PART 10. |
| MN-12 | `getchar()` returning `int` / EOF (K1.5) is absent from 03/04. | REQUIRED BOX in the strings/character I/O chapter. |
| MN-13 | T08 Advanced Topic "모듈이란?" and T09 "스텁 기법" have no placement in 05. | "모듈이란?": optional box at the end of the functions chapter, reprised as core design guidance in the multi-file chapter. "스텁 기법": optional box in the functions chapter (top-down development). T17 "수동 vs 자동 메모리 관리": optional box at the end of the dynamic-memory chapter. |

---

## Dependency audit

Legend: → = "must precede". Severity: CRITICAL / MAJOR / MINOR / NONE.

| # | Dependency (prerequisite → dependent) | 05 status | Severity | Correction |
|---|---|---|---|---|
| D1 | program basics → variables/types | Ch3 → Ch4 | NONE | — |
| D2 | variables/types → expressions/operators | Ch4 → Ch5 | NONE | — |
| D3 | `#define` constants → array sizes | T16 → T10 | MINOR | `#define`/`enum` in the constants chapter (MN-2) |
| D4 | expressions → control flow | Ch5 → Ch6/7 | NONE | — |
| D5 | control flow → functions | Ch7 → Ch8 | NONE | — |
| D6 | functions → scope/storage/linkage | Ch8 → Ch9 | NONE | — |
| D7 | TU concept → linkage | Ch11 after Ch9 | MAJOR | TU definition inside the linkage section (MJ-8) |
| D8 | functions + stack model → recursion | Ch8 → Ch10 | NONE | — |
| D9 | functions → arrays-as-parameters | Ch8 → Ch12 | NONE | — |
| D10 | arrays → pointer↔array relationship | Ch12 → Ch14 | NONE | — |
| D11 | basic pointers → pointer arithmetic | Ch13 | MINOR | move arithmetic next to arrays (MN-1) |
| D12 | char arrays / `'\0'` / literals → `char*` vs `char[]`, string impl | Ch18 **after** Ch14 | **CRITICAL** | strings after the pointer↔array chapter (CR-2) |
| D13 | strings → pointer arrays as string tables, K5.9 contrast | Ch18 **after** Ch15 | MAJOR | advanced pointers after strings (CR-2) |
| D14 | strings + pointer arrays → `argc/argv` | Ch18 **after** Ch16 | MAJOR | `argc/argv` in the files/program-interface chapter (MJ-2) |
| D15 | pointer params → `const T *` params | const in Ch16 (late) | MAJOR | `const T *` in pointer basics (MJ-1) |
| D16 | struct basics → struct pointers `->` | Ch19 | NONE | — |
| D17 | struct + `->` → dynamic struct / self-ref / list | Ch19 **after** Ch17 | **CRITICAL** | CR-1 |
| D18 | pointers + `sizeof` → dynamic memory | Ch13 → Ch17 | NONE | — |
| D19 | `void*` basics → `qsort`/generic code | void in Ch16, malloc in Ch17 | MINOR | `void*` basics at malloc; generic use later (MJ-1) |
| D20 | double pointers → "modify caller's pointer" in list insert | Ch15 → Ch17 | NONE | keep |
| D21 | strings + structs → files (text parsing, binary struct I/O) | Ch18/19 → Ch20 | NONE | keep files after structs |
| D22 | preprocessor → headers / include guards → multi-file | Ch21 | NONE | split chapters (MN-6) |
| D23 | compile/link model → multi-file | Ch2 → Ch21 | NONE | — |
| D24 | UB concept → first UB-triggering topic (uninit, overflow, `i=i++`, out-of-bounds) | UB core in PART 7 (Ch22), boxes in Ch5 | MAJOR | define UB in Ch4 as a REQUIRED BOX; PART 7 consolidates (see gap table) |
| D25 | all core + dynamic memory + recursion → DS | PART 9 | NONE (after fixes) | see DS matrix |
| D26 | library functions → used where needed | PART 8 after use | MAJOR (duplication) | MJ-6 |

### Ordered dependency list (after corrections)

```text
toolchain/build model
 → program skeleton (main, printf, scanf)
 → types, sizeof/size_t, constants (#define/enum), UB concept box
 → operators, conversions, evaluation-order box
 → selection → iteration
 → functions (call-by-value, prototypes, call stack)
 → scope / storage duration / linkage (TU defined here)
 → recursion
 → arrays (1D, 2D usage, arrays as params)
 → pointers: &, *, NULL, pointer params, const T* params, dangling-local
 → pointer↔array: arithmetic, decay, equivalence
 → characters & strings: '\0', literals, char* vs char[], string.h, safe input
 → structs: ., arrays of structs, ->, struct params, typedef, enum (+union short)
 → advanced pointers: **, pointer arrays, pointer-to-array + multidim, const table
 → dynamic memory: malloc/calloc/realloc/free, void*, ownership, memory errors
 → dynamic structs → self-referential struct → linked-list intro   [DS bridge]
 → streams/files → program interface (argc/argv, exit status, stderr)
 → preprocessor → multi-file & build (headers, TU, static/extern, modules)
 → [advanced, optional-order] function pointers/generics/variadic;
    low-level C (bits, bit-fields, unions, volatile, stdint);
    UB/portability consolidation
 → DS PART
```

---

## Recommended final concept order

Chapter-level. `T##`/`K#.#` = source mapping. ★ = DS-prerequisite chapter. ◇ = optional / advanced (skippable on the first pass).

**PART 1 — C와 프로그래밍의 시작**
1. 프로그래밍의 개념 (T01)
2. 프로그램 작성 과정과 개발 도구 (T02): preprocess → compile → link → run; error kinds by stage; VS2022 (`/std:c17 /W4`, `.c`) + gcc/clang (`-std=c17 -Wall -Wextra`). Debugger: first taste only.
3. C 프로그램 구성요소 (T03, K1.1, K7.2, K7.4): printf/scanf; box "check scanf's return value".

**PART 2 — 기본 문법**
4. 변수와 자료형 (T04, K2.1–2.4, K4.9, KB11): `sizeof`, `size_t`, limits, signed/unsigned, overflow (signed = UB, unsigned = wrap), float precision, `char`, `const` variables, `#define`/`enum` constants; REQUIRED BOX "UB란 무엇인가"; RECOMMENDED boxes `stdint.h`, `stdbool.h`.
5. 수식과 연산자 (T05, K2.5–2.12): int division, `++/--`, short-circuit, `?:`, basic bitwise (T5.8 labs kept), conversions (simplified), casts, precedence; REQUIRED BOXES: signed/unsigned comparison, unsequenced modification / order of evaluation.
6. 조건문 (T06, K3.1–3.4): `bool` usage; dangling-else box; `goto` box.
7. 반복문 (T07, K3.5–3.7): RECOMMENDED tool box "debugger: breakpoint / step / watch".

**PART 3 — 함수와 프로그램 구조**
8. ★ 함수 (T08, K1.7–1.8, K4.1–4.2): call-by-value, prototypes, `(void)`, history box on implicit declarations, `rand`/`math.h`, call-stack VISUAL; ◇ boxes: 모듈이란? (T08 AT), 스텁 기법 (T09 AT).
9. ★ 변수의 범위·생존 기간·연결 (T9.1–9.6, K1.10, K4.3–4.8): TU defined, 2-file `extern`/`static` micro-demo, globals discipline, `register` history note.
10. ★ 재귀 (T9.8, K4.10 purpose-ref): Hanoi.

**PART 4 — 배열과 포인터**
11. ★ 배열 (T10, K1.6, K1.9): bounds (UB), arrays as parameters (size passed separately), sort/search labs, 2D arrays (usage only).
12. ★ 포인터 기초 (T11.1–11.3, 11.5, 11.7, K5.1–5.2): `&`, `*`, NULL, pointer params (swap, out-params, why `scanf` needs `&`), `const T *` params, never return the address of a local.
13. ★ 포인터와 배열 (T11.4, 11.6, K5.3–5.4): arithmetic, decay (+ exceptions: `sizeof`, `&`), `a[i] ≡ *(a+i)`, `sizeof` in functions, `ptrdiff_t` box.

**PART 5 — 문자열과 구조체**
14. ★ 문자와 문자열 (T12, K1.5, K1.9, K5.5, K7.7): `'\0'`, literals, `char*` vs `char[]` + mutability, `getchar` → `int`/EOF, `fgets`, `ctype`, `string.h` (+ pointer implementations as the K&R enhancement), buffer overflow / `strncpy` caveats, `strtol` / `snprintf`; `char[N][M]` table (simple).
15. ★ 구조체와 사용자 정의 자료형 (T13, K6.1–6.4, K6.7–6.8): struct, init, arrays of structs, `->`, pass/return (value vs `const T *`), `typedef`, `enum`; union short section; REQUIRED sentence "sizeof(struct) ≥ sum of members"; ◇ padding box.

**PART 6 — 포인터 심화와 동적 메모리**
16. 포인터 심화 (T14.1–14.3, 14.5, 14.6-const, K5.6–5.9): `**` (modify caller's pointer), pointer arrays / string tables, pointer-to-array + multidimensional arrays **together**, K5.9 layout contrast, full `const` table, reading declarations (≤2 levels).
17. ★ 동적 메모리 (T17.1–17.3, K8.7 teacher-only): storage durations recap, `malloc`/`free`, `void*`, `sizeof *p` house style, NULL checks, `calloc`, `realloc` temp-pointer idiom, dynamic arrays/strings/2D, **ownership rule**, memory errors, sanitizer box; ◇ 수동 vs 자동 메모리 관리 (T17 AT).
18. ★ 동적 구조체와 연결 리스트 입문 (T17.4–17.5, K6.4–6.5): node allocation, self-referential struct, build/traverse/insert-head/free-all, `Node **` vs return-new-head, 영화 관리 MiniProject. **DS bridge.**

**PART 7 — 파일과 프로그램 구성**
19. 스트림·파일 입출력과 프로그램 인터페이스 (T15, T14.8, K5.10, K7.1, K7.5–7.7): text/binary (struct I/O), random access, `stderr`, `perror`/`errno` (POSIX caveat), exit status, `argc/argv`; ◇ fd vs `FILE*` / buffering box (K8.1–8.5).
20. 전처리기 (T16.1–16.5, K1.4, K4.11): macros, parenthesization and side-effect traps, conditional compilation, `assert`.
21. 다중 소스 파일과 빌드 (T16.6, K4.5, KA10–A11): TU, declaration vs definition, header design rules, include guards, `static`/`extern` revisited, module design (T08 AT reprise), VS multi-file projects + `gcc a.c b.c`; ◇ make/CMake mention.

**PART 8 — C 심화 (◇ optional order; recommended before DS: 22)**
22. ◇ 함수 포인터와 제네릭 기법 (T14.4, 14.7, T9.7, K5.11–5.12, K7.3): function pointers, callbacks, dispatch tables, `void*` generics, `qsort`/`bsearch`, declaration decoding, variadic functions; 이분법 MiniProject.
23. ◇ 저수준 C (T5.8 advanced, T13.6 HW, T14.6-volatile, T16.7, K2.9, K6.8–6.9): masks, shift safety, bit-fields, unions/type punning caveats, `volatile` (correct scope), `stdint.h`, endianness.
24. ◇ 정의되지 않은 동작과 이식성 (consolidation): UB / implementation-defined / unspecified taxonomy, integer rules in full, alignment (`alignof`), `_Static_assert`; survey: `inline`, `restrict`, `_Generic`; C23 notes.

**Appendices (reference)**
- A. 개발 도구 (VS2022, gcc/clang, warnings, debugger, sanitizers)
- B. **표준 라이브러리 레퍼런스** (by header; replaces the teaching PART 8)
- C. 연산자 우선순위 / 형식 지정자 / ASCII
- D. C의 역사와 K&R 스타일 읽기 (implicit int, old-style definitions, C89 → C23)

Then **DS PART → Algorithms PART → Projects PART** (README PART 9–11, renumbered by the manager).

---

## Arrays/pointers/strings decision

| Question | Decision | Reason |
|---|---|---|
| Arrays before basic pointers? | **Yes** [SRC T10 → T11; REC] | Arrays are usable without pointers (indexing, loops). They give pointers a motivating context (decay, pass-to-function) and match the textbook. |
| Where does array decay appear? | Preview in arrays (Ch11: "array parameter is really a pointer; pass the size"), full rule in Ch13 | Learners need the practical rule (pass length) before they have pointer vocabulary. |
| Strings before or after the full pointer relationship? | **After Ch13 (pointer↔array), before advanced pointers** | String library use and implementation both depend on decay and `char*`. String tables and `argv` depend on strings. |
| `char*` vs `char[]`: pointer unit or string unit? | **String unit** (Ch14) | It is only meaningful with string literals. Ch13 may preview "arrays are not pointers" via `sizeof`. |
| Pointer arithmetic | In Ch13 (with arrays), not in basics | Validity is defined relative to array objects (MN-1). |
| Pointer arrays | Ch16 (after strings) | The canonical use is string tables / `argv`. A `char[N][M]` table first appears simply in Ch14. |
| Double pointers | Ch16; the "modify caller's pointer" pattern is reused in Ch18 | Needed for list-head update. The rest is advanced. |
| Multidimensional arrays and pointer-to-array | **Together in Ch16**; 2D *usage* stays in Ch11 | `int (*p)[C]` exists to explain 2D decay and 2D parameters. Teaching them apart duplicates the row-decay explanation (T14.3 and T14.5 are adjacent in the source, and K5.7/5.9 already pair them). |
| Function pointers | Postponed to Ch22 (optional, before DS) | Needed only for generic DS / callbacks (DS matrix: DURING DS). |
| Complex declarations | Core ≤2 levels in Ch16; full decoding in Ch22 ◇ | Avoids overengineering (MN-5). |

---

## Structures/dynamic-memory decision

**Chosen order** [REC], essentially the manager's candidate order with advanced pointers slotted in:

```text
struct basics → arrays of structs → struct pointer (->) → struct & functions → typedef/enum
 → (advanced pointers: **, pointer arrays)
 → dynamic memory (no structs required; void*, ownership, errors)
 → dynamic struct (malloc(sizeof *p) of a struct)
 → self-referential struct
 → linked-list intro
```

Why this order and not the alternatives:
- **Structs before dynamic memory (not the reverse)**: dynamic memory can be taught fully with `int`/`char` buffers. Dynamic *structs* need structs. The reverse ordering (05) forces struct syntax into the heap chapter.
- **Dynamic memory before self-referential structs**: a self-referential struct can be *declared* without the heap, and K6.5 shows the declaration. But every realistic use (an unbounded chain of nodes) needs `malloc`. Teaching self-reference with static node arrays is possible but artificial for this audience. So self-reference goes in the bridge chapter, right after dynamic memory, where it is immediately usable.
- **Why not move structs all the way before pointers?** It would be possible: `.` access needs no pointers. But `->` and struct parameters by pointer are the struct features DS needs, and strings (a common struct member type) need pointers. Keeping structs after strings follows the source order and avoids a second struct chapter.
- **Linked-list bridge: delayed or kept before PART 7 (files)?** Keep it immediately after dynamic memory (Ch18). It is the natural payoff of the heap chapter. Scope it tightly to create / traverse / insert-at-head / free-all, so it does not pre-empt the DS PART (no deletion-by-key, no sorted insert, no doubly linked lists).
- **Union**: short section in Ch15 (source-derived, T13.6). Hardware / type-punning use goes to Ch23.
- **Should dynamic memory move later (after files)?** No. Files do not depend on the heap, and the heap does not depend on files. Keeping the heap in PART 6 keeps pointers, heap, and bridge contiguous, which is the core of the book.

---

## Functions/scope/module decision

| Topic | Placement | Note |
|---|---|---|
| definition / call / params / return / call-by-value / prototypes | Ch8 (core) | Prototypes plus a `(void)` rule; history box on implicit declarations (errors in GCC 14 [EXT]). |
| scope / storage duration / linkage | Ch9 (core, **right after functions**) | Source-derived (T09), and correct: learners need local vs static lifetime before pointers (dangling locals, Ch12) and before the heap (Ch17 contrasts three storage durations). |
| TU definition | Ch9, just before linkage | Fixes D7. Full treatment in Ch21. |
| `static` (local persistence + file-private) | Ch9 core; revisited Ch21 | 04:C10 "recommended" → **CORE** (textbook 9.4/9.5 already teaches it; DS libraries hide helpers with it). |
| `extern` | Ch9: concept + 2-file micro-demo; Ch21: header pattern | Avoids teaching `extern` purely in the abstract. |
| recursion | Ch10 | After the stack model. |
| compile/link | Ch2 (model + error-by-stage), Ch9 (linkage requires the link step), Ch21 (full) | Three-stage spiral; no separate chapter (MJ-8). |
| header files / module thinking | Ch8 ◇ box (T08 AT "모듈이란?": cohesion/coupling as *design idea*), Ch21 core (headers as interfaces) | The concept early, the mechanism later. A module without headers is only a design idea; that is fine as a box. |
| stub technique (T09 AT) | Ch8 ◇ box | Relates to top-down decomposition (T8.7), not scope. |
| variadic (T9.7) | Ch22 ◇ | Needs `stdarg`, and `printf`-family understanding. |

---

## Advanced-topic grouping decision

Replace 05:Ch16 with the distribution below. Grouping principle: **one chapter = one learning goal**.

| Current 05:Ch16 element | New home | Tier |
|---|---|---|
| `const` (variables) | Ch4 | CORE |
| `const T *` parameters | Ch12 | CORE |
| `const` placement table (`int *const`, etc.) | Ch16 | CORE (table) |
| `volatile` | Ch23 | ADVANCED box: *not* a thread-synchronization tool; valid for MMIO, `setjmp`-surviving locals, and signal flags (with `sig_atomic_t`) |
| `void*` basics | Ch17 (at `malloc`) | CORE |
| `void*` generic programming | Ch22 | ADVANCED |
| `argc/argv` | Ch19 | CORE (practical) |
| function pointers / callbacks / `qsort` | Ch22 | RECOMMENDED before DS, ◇ |

---

## Gap-analysis corrections

Tiers: **CORE** (main text) · **REQUIRED BOX** (short mandatory box at the first trigger point) · **RECOMMENDED** · **ADVANCED** · **REFERENCE ONLY** (appendix) · **DEFER** (not in the C part).

| Current item (04 ID) | Current verdict | Recommended verdict | Reason / placement |
|---|---|---|---|
| signed/unsigned pitfalls (C1) | required | **REQUIRED BOX** | Ch5 (comparison `-1 < 0u`), repeated in Ch14 (`strlen` returns `size_t`, reverse loops). A box, not a section. |
| integer overflow (C1) | required | **CORE** | Ch4 integer section. Frame precisely: signed overflow = UB; unsigned = modulo wrap. Verify the textbook's T4.3 demo does not present signed wraparound as defined. |
| integer promotions (C2) | required | **REQUIRED BOX** | Ch5: "operands smaller than `int` become `int`". Full rank rules → Ch24. |
| usual arithmetic conversions (C2) | required | **CORE** (int/double mixing, `1/2`) + **REFERENCE ONLY** (full rank table) | Beginners need the int-vs-floating part; the rank algorithm is reference material. |
| undefined behavior (C3) | required, "adv box Ch05 + PART 7" | **REQUIRED BOX in Ch4** (definition) + **CORE** recurring labels + **ADVANCED** Ch24 taxonomy | Must be defined at the first UB trigger (uninitialized read, overflow), not in Ch5 or PART 7. Phrase uninitialized reads as "never do this; indeterminate value, possibly UB", not "garbage value" only. |
| implementation-defined behavior (C3) | required | **REQUIRED BOX** (Ch4: `sizeof(int)`, `char` signedness) + **ADVANCED** (Ch24) | Keep light. |
| order of evaluation (C3) | required | **REQUIRED BOX** (Ch5) | "Don't modify a variable twice in one expression; argument order is unspecified." |
| dangling pointers (C4) | required | **CORE** | Ch12 (address of a local) and Ch17 (after `free`). |
| use-after-free (C4) | required | **CORE** | Ch17, with the ownership rule. |
| double free (C4) | required | **CORE** | Ch17. |
| memory leaks (C4) | required | **CORE** | Ch17 and Ch18 (free-all list). |
| NULL-after-free (C4) | required | **RECOMMENDED** (with limits) | See §Specific memory-safety review. |
| malloc failure (C5) | required | **CORE** | Ch17. Include the `realloc` temp-pointer idiom. |
| `sizeof *p` idiom (C5) | required | **RECOMMENDED** (house style) | Use consistently in all book code. Explain once. Not a correctness requirement. |
| `enum` API constants / typedef-pointer warning (C6) | recommended | **RECOMMENDED** | Ch15 box. |
| function pointers / callbacks (C7) | advanced (before-DS) | **RECOMMENDED** (Ch22), DS: during-DS | See DS matrix. |
| argc/argv + exit + stderr (C8) | required | **CORE** | Ch19. |
| translation units (C9) | required | **CORE** | Ch9 (definition), Ch21 (full). |
| compile vs link (C9) | required | **CORE** | Ch2 model; Ch21 full. |
| header design (C9) | required | **CORE** | Ch21: declarations only; no object definitions in headers; guards; self-contained headers. |
| static linkage (C10) | recommended | **CORE** | Ch9 / Ch21 (see functions decision). |
| volatile (C11) | recommended | **ADVANCED** | Ch23 box, correctly scoped. |
| `_Static_assert` (C11) | recommended | **ADVANCED** | Ch24 (C11 keyword `_Static_assert`; C23 `static_assert` [EXT]). |
| `stdbool` / `bool` (C11) | recommended | **RECOMMENDED** → house style from Ch6 | `bool`/`true`/`false` are keywords in C23 [EXT]; `<stdbool.h>` works on C99–C17 and MSVC. |
| `stdint.h` (C11) | recommended | **RECOMMENDED** (Ch4 box) + **CORE** in Ch23 | Fixed-width types matter for binary files and bits, not for beginner arithmetic. |
| compiler warnings (C12) | required, Ch02 | **CORE** (Ch2) | `/W4` and `-Wall -Wextra`; "treat warnings as questions". |
| sanitizers (C12) | required, Ch02 | **RECOMMENDED** (Ch13/Ch17 boxes + Appendix A) | Meaningless before pointers. MSVC supports ASan only (`/fsanitize=address`, VS 2019 16.9+); UBSan is gcc/clang [EXT]. |
| debugger basics (C12) | required, Ch02 | **RECOMMENDED** (first real use in Ch7/Ch8) | Stepping loops and calls is where debugger use pays off. Ch2 gets a pointer only. |
| bit ops safety (C13) | advanced | **ADVANCED** (Ch23) | Keep. |
| restrict (C14) | can-wait | **REFERENCE ONLY** | Explain only when reading `memcpy`/`strcpy` prototypes (Appendix B). |
| inline (C14) | can-wait | **ADVANCED** (Ch24 survey; `static inline` in headers) | C `inline` semantics differ from C++; don't teach casually. |
| `_Generic` (C14) | can-wait | **DEFER** (1-line mention in Ch24) | No beginner or DS need. |
| setjmp / signal (C15) | defer | **REFERENCE ONLY** (Appendix B) | Keep deferred. |
| alignment/padding (C16) | advanced (before-DS) | **REQUIRED sentence** in Ch15 + **ADVANCED** box; **drop the "before-DS" flag** | DS needs only "use `sizeof`, never add member sizes". |
| errno / strerror (C17) | recommended | **RECOMMENDED** (Ch19), prefer `perror` | ISO C does not require `fopen` to set `errno`; POSIX does [EXT]. Phrase accordingly. |
| cmd-line parsing mini-pattern (C18) | recommended | **RECOMMENDED** (Ch19 lab) | Keep. |
| B1 `char*` vs `char[]` | required | **CORE** (Ch14) | — |
| B2 array decay + `sizeof` in functions | required | **CORE** (Ch13; preview Ch11) | — |
| B3 const placement | required | **CORE** (split: Ch12 params, Ch16 table) | — |
| B4 uninit / static zero-init | required | **CORE** (Ch4, Ch9) | — |
| B5 implicit-int / prototype story | recommended | **HISTORICAL NOTE box** (Ch8) + Appendix D | — |
| B6 `register` | defer | **HISTORICAL NOTE** (1 line, Ch9) | — |
| B7 fd vs `FILE*`, buffering | advanced | **ADVANCED** (Ch19 box) | — |
| B8 safe string input | required | **CORE** (Ch14) | — |
| **NEW** `size_t` / `%zu` | — (missing) | **CORE** (Ch4; reused Ch11/14/17) | Appears with `sizeof`, `strlen`, and `malloc`. |
| **NEW** checking `scanf`'s return value / input validation | — | **REQUIRED BOX** (Ch3), CORE pattern (Ch14: `fgets` + `strtol`) | Beginner programs otherwise loop forever on bad input. |
| **NEW** `getchar()` returns `int` (EOF) | — | **REQUIRED BOX** (Ch14) | K1.5 idiom; classic bug. |
| **NEW** out-of-bounds access = UB | — | **CORE** (Ch11) | Not explicit in 04. |
| **NEW** `#define`/`enum` for array sizes; no `const int` constants | — | **CORE** (Ch4) | MN-2. |
| **NEW** VLA policy | — | **REFERENCE ONLY** (Ch24 note; not used in the book) | MSVC: no VLA support planned; VLAs are optional since C11 [EXT]. |
| **NEW** C standard / toolchain baseline | — | **CORE decision** (Ch2) | MJ-3. |
| **NEW** `.c` vs `.cpp` in Visual Studio | — | **REQUIRED BOX** (Ch2) | Otherwise the learner is compiling C++. |

---

## Specific memory-safety review

Statement under review [SRC 04:C4]: "NULL-after-free" as part of a required discipline.

**What `p = NULL` after `free(p)` does help with:**
- A later `free(p)` through **the same variable** becomes a no-op (`free(NULL)` does nothing), which prevents that particular double free.
- A later dereference through **the same variable** becomes a null dereference. That is still UB, but in practice usually an immediate crash rather than silent heap corruption, so the bug surfaces early.
- It lets the variable itself encode state ("currently owns a block / owns nothing"), which is useful for long-lived pointers such as struct members, globals, and cache pointers.

**What it does NOT solve:**
- **Aliases**: `q = p; free(p); p = NULL;` leaves `q` dangling. In DS code this is the normal case (`prev->next`, `tail`, `cur`, parent pointers, array-of-pointers entries).
- **Copies in other scopes**: `void destroy(Node *n) { free(n); n = NULL; }` nulls only the local parameter. The caller's pointer is still dangling. It would need `Node **` or a caller-side assignment (a good teaching link to Ch16).
- **Interior pointers** into the freed block (e.g. `char *mid = buf + 5`).
- **`realloc` invalidation**: when `realloc` moves the block, all old pointers dangle, and `p = NULL` is irrelevant.
- **Stack dangling**: pointers to locals of a returned function.
- **Leaks**: nulling *before* freeing, or overwriting the only pointer, creates leaks. The habit does not detect them.
- It is not a replacement for tools (ASan reports heap-use-after-free and double-free [EXT]).

**Recommended phrasing policy:**
- **Core rule** (Ch17, boxed): "`free` 이후에는 그 블록을 가리키던 **모든** 포인터가 무효다. 누가 이 메모리를 해제할 책임이 있는지(소유자)를 항상 하나로 정하라."
- **Habit** (RECOMMENDED): "해제 후 그 포인터 변수를 계속 쓸 가능성이 있으면 `NULL`을 대입해 둔다. 단, 이것은 **그 변수 하나만** 바꾼다." Always shown together with an alias counter-example.
- **Beginner habit? Yes**, but only framed as a debugging aid for the variable itself. Never call it "안전하게 만드는 방법".
- The DS bridge (Ch18) must show `free_list(&head)` with `Node **` (or `head = free_list(head)`) to make the caller-visible nulling explicit.

---

## K&R modernization decisions

| K&R item | Decision | Conceptual value kept | Outdated part |
|---|---|---|---|
| Implicit `int` (K4.2, App C) | **HISTORICAL NOTE** (Ch8 box, App D) | Why prototypes exist | Removed in C99; error by default in GCC 14 [EXT] |
| Implicit function declaration | **HISTORICAL NOTE + MODERNIZE** | "Declare before use" | Same as above |
| Old-style (K&R) function definitions | **HISTORICAL NOTE** (App D only) | Reading legacy code | Removed in C23 [EXT] |
| Empty parameter list `f()` | **MODERNIZE** → always `f(void)` | — | `()` meant "unspecified parameters" before C23 |
| `main()` without `int` / without `return` | **MODERNIZE** → `int main(void)`, `return 0;` | — | — |
| `register` (K4.7) | **HISTORICAL NOTE** (1 line) | Cannot take its address | Optimization hint obsolete |
| `auto` storage class (T9.4/9.6 teach it too) | **MODERNIZE**: mention it is redundant for locals; C23 gives `auto` a type-inference meaning | Automatic storage duration concept | The keyword itself |
| UNIX system interface (K8) | **ADVANCED** (concept boxes) / **OMIT FROM CORE** | fd vs `FILE*`, buffering (8.5), allocator (8.7) | Syscall API specifics; 8.6 directory listing omitted |
| Low-level file descriptors `read`/`write`/`open` | **ADVANCED** box, labeled POSIX (MSVC `_open`/`_read` note) | Layering of stdio over the OS | Not ISO C |
| K8.7 storage allocator | **ADVANCED** (optional reading in Ch17 or DS) | Heap mental model, free lists, fragmentation | — |
| K5.4 `alloc`/`afree` | **KEEP** as a pointer-arithmetic illustration (purpose only) | Pointer comparison within one array | — |
| Pointer copy idioms (`while ((*s++ = *t++))`) | **KEEP as reading skill, MODERNIZE** | Pointer / `'\0'` mechanics | Not house style for beginners; explain `-Wparentheses` |
| `char *p = "literal"` | **MODERNIZE** → `const char *` | Literal storage | Modifying a literal is UB |
| Casting `malloc`'s result (K6.5 `talloc`) | **MODERNIZE** → no cast in C | — | Cast hides a missing `<stdlib.h>` in C89; needed only in C++ |
| K&R's own `getline` (K1.9, K4.1) | **MODERNIZE**: rename (e.g. `read_line`) | Line-reading design, buffer ownership | Clashes with POSIX `getline` on glibc |
| K&R `atoi`/`itoa` hand implementations | **KEEP** as exercises | Digit arithmetic | Production code uses `strtol` |
| Preprocessor patterns (K4.11) | **KEEP** (parenthesization, guards); **MODERNIZE** (prefer `enum`/`const`/functions where possible) | Macro expansion model | Multi-statement macro `do{}while(0)` → ADVANCED |
| Symbolic constants (K1.4) | **KEEP**, move early (Ch4) | Magic-number avoidance | — |
| `dcl` parser (K5.12) | **ADVANCED** (Ch22) | Declaration reading | Full parser omitted |
| Table lookup / hash (K6.6) | **KEEP → DS PART** (hash table) | Hashing on structs | — |
| `tnode` binary tree (K6.5) | **KEEP → Ch18 preview + DS trees** | Self-reference, recursion on trees | — |
| Quicksort (K4.10) | **KEEP → Algorithms PART** | Recursion + partition | — |
| Bit-fields (K6.9) | **KEEP** with implementation-defined caveats (Ch23) | Flags, HW registers | Layout is non-portable |
| Appendix A reference manual | **REFERENCE ONLY** (writer-internal), superseded by public C17/C23 drafts | Precise grammar | Pre-C99 content |
| Appendix B library | **REFERENCE ONLY**, extended with C99+ headers (`stdbool`, `stdint`, `inttypes`) | Header map | Missing modern headers |

---

## Standard-library architecture decision

**Choice: OPTION C, hybrid**, with a specific shape:

1. **Contextual teaching (primary)**: every library function is taught in the chapter where the learner first needs it:
   - `printf`/`scanf` → Ch3
   - `rand`/`srand`/`time(NULL)`/`math.h` → Ch8
   - `ctype`/`string`/`strtol`/`snprintf` → Ch14
   - `malloc` family → Ch17
   - `stdio` files/`errno`/`exit` → Ch19
   - `assert` → Ch20
   - `qsort`/`bsearch` → Ch22
   - `stdint` → Ch4/23
   - `limits`/`float` → Ch4
2. **Reference appendix (Appendix B), not a teaching PART**:
   - Organized by header.
   - Per function: prototype | one-line semantics | return / error convention | top pitfall | "taught in Ch##".
   - Headers with no teaching chapter get *reference-only* entries (`setjmp`, `signal`, `locale`, `wchar`, `time.h` beyond `time()`).
   - Small usage snippets are allowed for reference-only entries.
3. **No third explanation.** The reference cross-links to the chapter and never re-explains the concept.

Why:
- **Beginners** get functions at the point of need, with a motivation, which is how the textbook already works [SRC 01].
- **Reference use** gets one lookup location with uniform entries.
- **Duplication** is minimal because each concept has exactly one explanation.
- Option A (a dedicated teaching PART) arrives too late for beginners and duplicates everything. Option B (contextual only) leaves no lookup structure and orphans headers without a natural chapter.

---

## DS prerequisite matrix

Manager hypothesis E: **PARTIALLY CONFIRMED**. 05's list slightly over-requires (strings, multi-file). The bigger problem is that it **omits** real prerequisites: memory ownership discipline and `sizeof`/`size_t`.

| Concept | Verdict | Reason |
|---|---|---|
| functions | **MANDATORY BEFORE DS** | Every DS operation is a function. |
| scope / storage duration | **MANDATORY BEFORE DS** | Local vs heap lifetime explains why nodes are `malloc`'d. |
| arrays | **MANDATORY BEFORE DS** | Array stacks / queues / heaps / hash buckets. |
| pointers | **MANDATORY BEFORE DS** | Linking. |
| `sizeof` / `size_t` | **MANDATORY BEFORE DS** | Every allocation. |
| structures | **MANDATORY BEFORE DS** | Nodes, containers. |
| struct pointers (`->`) | **MANDATORY BEFORE DS** | Node access. |
| dynamic memory (`malloc`/`free`, NULL checks) | **MANDATORY BEFORE DS** | Unbounded structures. |
| memory ownership / leak / UAF discipline | **MANDATORY BEFORE DS** | Deletion and destroy operations. |
| recursion | **MANDATORY BEFORE DS** (before trees) | Tree traversal, DFS. Lists / stacks / queues don't need it. |
| double pointers | **USEFUL BEFORE DS** | `Node **head` insertion. The alternative (return the new head) works. Teach both in Ch18. |
| pointer arithmetic | **USEFUL BEFORE DS** | Indexing suffices for array-based DS. |
| `typedef` | **USEFUL BEFORE DS** | Readability only. |
| strings | **USEFUL BEFORE DS** | String keys (hash tables, word BSTs). Integer-keyed DS need none. |
| multi-file programs | **USEFUL BEFORE DS** | DS as reusable `.h`/`.c` modules. The DS PART can start single-file. |
| `realloc` | **USEFUL BEFORE DS** | Growable arrays, hash resize. Covered in Ch17 anyway. |
| `const` pointer parameters | **USEFUL BEFORE DS** | Read-only API signatures. |
| `assert` | **USEFUL BEFORE DS** | Invariant checks. |
| enum | **CAN LEARN DURING DS** | Node colors, visit states. |
| function pointers | **CAN LEARN DURING DS** | Generic compare / visit. |
| callbacks | **CAN LEARN DURING DS** | Traversal visitors. |
| `void*` generics | **CAN LEARN DURING DS** | Generic containers (advanced DS). |
| bit operations | **CAN LEARN DURING DS** | Bitsets, hash mixing. |
| unions | **NOT REQUIRED** | — |
| file I/O | **NOT REQUIRED** | Useful for loading graphs in projects. |
| command-line args | **NOT REQUIRED** | Project-level. |

Consequence for the TOC: the DS-prerequisite chapters are ★ Ch8–18. PART 7–8 are not DS gates. Ch22 is recommended but optional before DS.

---

## Chapter-template review

**Assessment of 06:**
- **Too repetitive**: items 10/11 overlap, and 14/16 overlap.
- **Too expensive per chapter**: 16 mandatory slots.
- **Unsuitable** for T01/T02 and the reference appendix.
- **Missing**:
  - source-tag labeling,
  - dual-toolchain verification,
  - optional / 심화 markers,
  - an answer-key policy,
  - a portability note slot.

### MANDATORY (every teaching chapter)

1. **Brief header** (existing 06 header), plus: `Tier markers used | Toolchain-verified: MSVC/gcc`.
2. **Learning goals** (3–5, verb-based; DS flag).
3. **Prerequisite link** (2 lines; merge "previous chapter connection" + "next bridge" as an opening and a closing line).
4. **Motivation** ("why this exists"; a short problem-first paragraph).
5. **Core explanation with syntax** (merge terminology + syntax; terminology table only when ≥3 new terms).
6. **Compilable examples** (minimal first, then one worked program). Verified on both toolchains, warnings-clean. Expected output recorded.
7. **Common mistakes** (one table; bad→correct trio embedded where code is involved).
8. **Summary** (5–8 bullets).
9. **Exercises** (keep the 06 quota).
10. **Source-tag labeling** of sections: 🟢 기본 / 🟡 보강 / 🔵 추가 / 🟣 심화 (enforces the README classification).

### OPTIONAL (writer's judgment)

- Execution-flow trace (use when control flow is non-obvious: loops, recursion, calls).
- K&R enhancement box (only when a K&R point adds something; no empty boxes).
- Modern C / portability box (only at real trigger points).
- ◇ Advanced Topic box (T08/T09/T17 AT, K8 concepts).
- Tool box (debugger, sanitizer, compiler flag) at its first useful point.
- Historical note box.

### TOPIC-SPECIFIC (mandatory only for the listed chapters)

| Element | Required in |
|---|---|
| Memory diagram (VISUAL) | Ch4 (vars), Ch8 (stack), Ch11–18 |
| Bad / Why / Correct trio | Ch11–19 (arrays, pointers, strings, structs, heap, files) |
| UB / safety REQUIRED BOX | Chapters where 04 REQUIRED BOX items trigger (Ch3/4/5/11/12/14/17) |
| "Draw memory" exercise | Ch11–18 (keeps the 06 rule) |
| Build / toolchain steps | Ch2, Ch9 (2-file demo), Ch21 |
| DS-bridge checklist | Ch18 |
| Reference-entry format (prototype / semantics / errors / pitfall / taught-in) | Appendix B only |
| Chapter template reduced to goals + concept + summary + exercises | Ch1 (T01), Ch2 (T02) |

### Additional rules to add to 06

- Answer-key policy (where solutions live: an end-of-book appendix or a separate file).
- Example code lives in the repo as compilable files once body writing starts (enables verification).
- Every UB statement is phrased as "정의되지 않은 동작(UB): 결과를 보장하지 않는다", never as a specific observed result.

---

## Proposed changes to 05-proposed-c-book-toc.md

Do not apply until the manager approves. The target structure is §Recommended final concept order.

1. **PART 4 split and reorder**: replace 05:Ch12–17 with:
   - Ch11 배열
   - Ch12 포인터 기초
   - Ch13 포인터와 배열
   - Strings and structs move up as PART 5 (Ch14 문자열, Ch15 구조체).
2. **New PART 6 "포인터 심화와 동적 메모리"**:
   - Ch16 포인터 심화 (`**`, pointer arrays, pointer-to-array + multidim, const table, ≤2-level declarations)
   - Ch17 동적 메모리 (no structs)
   - Ch18 동적 구조체와 연결 리스트 입문 (new chapter, DS bridge; takes T17.4–17.5)
3. **Delete 05:Ch16** (const/volatile/void/argc/fptr). Distribute per §Advanced-topic grouping decision.
4. **Delete 05:Ch11** (TU preview chapter). Move the TU definition into the scope/linkage chapter; Ch2 carries the build model.
5. **Remove "char*/char[], string impl"** from the pointer↔array chapter and move it to the strings chapter.
6. **Move `argc/argv`** into the streams/files chapter as a closing "program interface" section.
7. **Split 05:Ch21** into Ch20 전처리기 and Ch21 다중 소스 파일과 빌드. Move bit-fields out to Ch23.
8. **Replace PART 7 (05:Ch22)** with three optional advanced chapters:
   - Ch22 함수 포인터와 제네릭 기법 (+ variadic, + declaration decoding)
   - Ch23 저수준 C (bits, bit-fields, unions-HW, `volatile`, `stdint`)
   - Ch24 UB와 이식성 (taxonomy, integer rules, alignment, `_Static_assert`, inline/restrict/_Generic survey)
9. **Replace PART 8 (05:Ch23)** with Appendix B 표준 라이브러리 레퍼런스. Add Appendices A (tools), C (tables), D (history / K&R style).
10. **Ch2**: add the toolchain baseline (C17; `/std:c17 /W4`, `.c` extension; `-std=c17 -Wall -Wextra`). Remove sanitizers/gdb from Ch2 scope (they move to boxes and Appendix A).
11. **Ch4**: add `size_t`, `#define`/`enum` constants, and the UB definition box. Overflow wording: signed = UB.
12. **Move `const T *` parameters** into pointer basics.
13. **Place T08 AT, T09 AT, T17 AT** as ◇ boxes (Ch8, Ch8, Ch17). Reprise "모듈" in Ch21.
14. **Rewrite the "Dependency map"** to match the new chapter list (the current map contradicts the current list).
15. **Rewrite the "Prereqs before DS" line** to match the DS matrix: mandatory = functions, scope/lifetime, arrays, pointers, `sizeof`/`size_t`, structs, `->`, dynamic memory, ownership discipline, recursion. Strings and multi-file become useful, not mandatory.
16. **Retag chapters** with ★ (DS prerequisite) and ◇ (optional) markers.

Documents also affected (manager integration):
- 04: relabel to the six tiers.
- 06: template split.
- README: PART 7/8 descriptions and PART numbering.
- 03: T14 row destinations.

---

## Questions / unresolved decisions

Only items requiring manager judgment:

1. **Standard baseline**: C17 (recommended) vs C11 vs "C23 with fallbacks". Recommendation: C17, with C23 notes only.
2. **Primary toolchain for screenshots / instructions**: VS2022 (source-faithful, Korean classroom default) with gcc as secondary (recommended), or equal weight.
3. **PART numbering**: removing the stdlib teaching PART shifts DS/Algo/Projects to PART 8–10 (README says 9–11). Renumber, or keep the numbers and label PART 8 as the "C 심화" group?
4. **Ch18 bridge**: a separate chapter (recommended; keeps Ch17 focused and gives the DS PART a clean entry point) vs the final section of Ch17 (closer to the source).
5. **Unions**: short section in Ch15 (source-faithful, recommended) vs entirely in Ch23.
6. **Is Ch22 (function pointers) a soft gate before DS?** Recommended: optional, but read before DS generic-container chapters.

---

## Final recommendation

**NEEDS MAJOR REVISION**

- The foundation is sound: source outlines 01/02 and crosswalk 03 are reliable.
- The **proposed TOC 05** has two CRITICAL prerequisite inversions (CR-1 struct/heap, CR-2 strings) and several MAJOR structural issues (MJ-1 grab-bag chapter, MJ-3 no standard/toolchain baseline, MJ-6 duplicate stdlib PART, MJ-8 TU-preview misorder).
- **04** needs tier relabeling and additions (MJ-4). **06** needs a mandatory/optional split (MJ-7).
- All fixes are well defined above. Most restore the textbook's own order.
- **Chapter 1 body writing** may proceed once the manager has adopted §Recommended final concept order and decided Q1–Q2. Ch1 (T01) is independent of the restructured regions.

---

## External sources

- Microsoft Learn, `/std (Specify Language Standard Version)`: default C mode = C89 plus extensions; `/std:c11`, `/std:c17` since VS 2019 16.8; VLAs not planned. https://learn.microsoft.com/en-us/cpp/build/reference/std-specify-language-standard-version
- Microsoft Learn, AddressSanitizer: `/fsanitize=address`, VS 2019 16.9+; detects double-free and heap-use-after-free; UBSan listed only as a possible future sanitizer. https://learn.microsoft.com/en-us/cpp/sanitizers/asan
- GCC 14 porting guide: implicit int, implicit function declaration, int-conversion, and incompatible-pointer-types are errors by default. https://gcc.gnu.org/gcc-14/porting_to.html
- cppreference, `fopen`: POSIX (not ISO C) requires `errno` to be set on failure. https://en.cppreference.com/w/c/io/fopen
- cppreference, C23: published as ISO/IEC 9899:2024; removal of function definitions without prototypes; `true`/`false`/`static_assert` become keywords; `nullptr`. https://en.cppreference.com/w/c/23
- Items cited by clause without a link (C17 6.5.6 pointer arithmetic; signed-overflow UB; `free(NULL)` no-op) are standard ISO C facts. Re-verify against the public C17 draft (N2176) during writing if a box quotes them. The C23 `auto` type-inference and `()`-means-`(void)` changes come from WG14 papers N3007 / N2841. Confirm them against the C23 draft (N3220) before a Ch9/App D box states them.
