# Gap Analysis (FINAL verdicts, manager-approved)

- Verdicts: CORE | REQUIRED BOX | RECOMMENDED | ADVANCED | REFERENCE ONLY | DEFER.
- Provenance preserved: [T]=textbook [K]=K&R [E]=modern/external addition.
- Baseline: C17. VS2022 primary, GCC secondary. C23 = notes only.
- Old coarse system (required/recommended/advanced/before-DS/can-wait/defer) replaced.

## A. Covered sufficiently (CORE, keep)

| # | Item | Source |
|---|---|---|
| A1 | basic types/printf/scanf/if/loops/functions/arrays | [T]+[K] |
| A2 | struct/enum/typedef basics; union brief-core | [T]+[K] |
| A3 | text/binary files, fseek | [T]+[K] |
| A4 | macros, cond-compile, include guards | [T]+[K] |
| A5 | malloc/calloc/realloc/free basics, list intro (now Ch18 bridge) | [T]+[K 6.5] |

## B. Clarification boxes

| # | Item | Source | Verdict | Placement |
|---|---|---|---|---|
| B1 | `char *` vs `char[]` literal mutability | [T] weak, [K 5.5] | REQUIRED BOX | Ch14 |
| B2 | array decay + `sizeof` in functions | [T] impl, [K 5.3] | REQUIRED BOX | Ch11/13 |
| B3 | `const` placement table | [T 14.6] | REQUIRED BOX | Ch12/16 |
| B4 | uninit vars; `static` zero-init | [T]+[K 4.9] | REQUIRED BOX | Ch4/9 |
| B5 | scanf return-value checking | [E] | REQUIRED BOX | Ch3 |
| B6 | getchar returns int / EOF rule | [K 1.5] | REQUIRED BOX | Ch14 |
| B7 | out-of-bounds = UB note | [E] | REQUIRED BOX | Ch11 |
| B8 | never return address of local | [E] | REQUIRED BOX | Ch12 |
| B9 | implicit-int/prototype story | [K 4.2] | RECOMMENDED (history) | Ch8, App D |
| B10 | `register` keyword | [K 4.7] | DEFER (1 line) | App D |
| B11 | fd vs FILE*; buffering | [K 8.x] | ADVANCED (teacher box) | Ch19 |
| B12 | string safe-input discipline | [T]+[K 1.5/7.7] | REQUIRED BOX | Ch14 |
| B13 | NULL-after-free: RECOMMENDED with limits (habit only, not safety) | [E] | RECOMMENDED | Ch17 |
| B14 | `sizeof *p` house style; malloc-failure checks | [E] | REQUIRED BOX | Ch17 |
| B15 | realloc temporary-pointer pattern | [E] | REQUIRED BOX | Ch17 |
| B16 | ownership model (aliases invalid after free) | [E] | CORE (Ch17 safety core) | Ch17 |

## C. Supplements

| # | Item | Source | Verdict | Placement |
|---|---|---|---|---|
| C1 | size_t / `%zu` | [E] | REQUIRED BOX | Ch4/11 |
| C2 | signed/unsigned compare + promotion basics | [E]+[K 2.7] | REQUIRED BOX | Ch4/5 |
| C3 | integer overflow basics | [E] | REQUIRED BOX | Ch4 |
| C4 | dangerous/unsequenced expr patterns (short) | [K 2.12] | REQUIRED BOX | Ch5 |
| C5 | UB/impl-defined/unspecified consolidation | [E] | ADVANCED (Ch24) | Ch24; beginner box Ch4 |
| C6 | dangling/UAF/double-free/leak discipline | [E] | CORE (before DS) | Ch17 |
| C7 | `#define`/`enum` array-size strategy; VLA policy (avoid in main) | [E] | REQUIRED BOX | Ch4/11 |
| C8 | `.c` vs `.cpp` warning (VS) | [E] | REQUIRED BOX | Ch2 |
| C9 | TU/compile-vs-link/header rules | [E]+[K A10-A11] | CORE | Ch9 def; Ch21 full |
| C10 | `static` linkage control | [T]+[K 4.6] | RECOMMENDED | Ch9/21 |
| C11 | `bool`/`stdint.h`/`_Static_assert`-era notes | [E] | RECOMMENDED | Ch4/23/24 |
| C12 | warnings (`-Wall -Wextra`, `/W4`); sanitizers RECOMMENDED (not Ch2 core) | [E] | RECOMMENDED | Ch2 brief; App A |
| C13 | debugger RECOMMENDED, introduced when useful (loops+) | [E] | RECOMMENDED | Ch7 box; App A |
| C14 | shift safety / signed shift | [E] | ADVANCED | Ch23 |
| C15 | `restrict`/`inline` survey; `_Generic` mention | [E] | REFERENCE ONLY | Ch24 |
| C16 | `setjmp`/`signal` survey | [K B8-B9] | REFERENCE ONLY | App B |
| C17 | alignment/padding: short adv box, NOT a DS prerequisite | [E] | ADVANCED | Ch15 |
| C18 | `errno`/`strerror` pattern | [E] | RECOMMENDED | Ch19 |
| C19 | CLI parsing mini-pattern; argc/argv | [T]+[K 5.10] | CORE (Ch19) | Ch19 |
| C20 | enum as API consts; typedef-ptr warning | [T]+[K 6.7] | RECOMMENDED | Ch15; void*-generics in Ch22/DS |
| C21 | function pointers/callbacks/qsort | [K 5.11] | ADVANCED (RECOMMENDED, not pre-DS) | Ch22 |
| C22 | volatile (HW note) | [T 14.6] | ADVANCED | Ch23 |
| C23 | endianness note | [E] | ADVANCED | Ch23 |
| C24 | C17 baseline box; C23 notes-only rule | [E] | CORE (policy) | Ch2 + Ch24 |

## External-source policy

- Allowed: public C standard drafts, GCC/Clang/MSVC docs, cppreference C, university notes. Tag [E].
- No C23 survey. No web research done in this task.
