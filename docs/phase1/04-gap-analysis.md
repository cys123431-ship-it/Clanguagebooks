# Gap Analysis — what both books still lack

- Verdicts: required | recommended | advanced | before-DS | can-wait | defer.
- SOURCE tags: [T]=textbook [K]=K&R [E]=modern-C reference (general, no deep C23 survey per scope).

## A. Covered sufficiently (keep, no action)

| # | Item | Source |
|---|---|---|
| A1 | basic types/printf/scanf/if/loops/functions/arrays | [T]+[K] |
| A2 | struct/enum/union/typedef basics | [T]+[K] |
| A3 | text/binary files, fseek | [T]+[K] |
| A4 | macros, cond-compile, include guards | [T]+[K] |
| A5 | malloc/calloc/realloc/free basics, linked-list intro | [T]+[K 6.5] |

## B. Covered but needs clarification (add boxes/sections)

| # | Item | Problem | Verdict |
|---|---|---|---|
| B1 | `char *` vs `char[]` literal mutability | [T] weak, [K 5.5] strong | required |
| B2 | array decay + `sizeof` inside functions | [T] implied, [K 5.3] strong | required |
| B3 | `const` placement (`const int*` vs `int* const`) | [T 14.6] brief | required |
| B4 | uninit vars; `static` zero-init | [T]+[K 4.9] scattered | required |
| B5 | implicit-int/prototype story | [K 4.2] LEGACY context | recommended (history box) |
| B6 | `register` keyword | [K 4.7] only | defer (1-line note) |
| B7 | fd vs FILE*; buffering | [K 8.x] impl view | advanced (teacher box) |
| B8 | string safe-input discipline | [T]+[K 1.5/7.7] | required |

## C. Missing / modern supplement candidates

| # | Item | Verdict | Placement |
|---|---|---|---|
| C1 | signed/unsigned pitfalls, overflow | required | Ch04/05 |
| C2 | integer promotion + usual arithmetic conversions | required | Ch05 |
| C3 | UB / impl-defined / unspecified (incl `i=i++`, order-of-eval) | required | adv box Ch05 + PART 7 |
| C4 | dangling/UAF/double-free/leak discipline + NULL-after-free | required (before-DS) | Ch17 end |
| C5 | malloc-failure handling; `sizeof *p` idiom | required | Ch17 |
| C6 | `enum` as API constants; `typedef` pointer warning | recommended | Ch13 |
| C7 | function pointers + callbacks + `qsort` comparator | advanced (before-DS) | Ch14 adv |
| C8 | `argc/argv` + exit codes + stderr usage | required | Ch14/15 practical |
| C9 | TU / compile-vs-link / header design rules | required | Ch16 open |
| C10 | `static` linkage control (file-private) | recommended | Ch09/Ch16 |
| C11 | `volatile`/`_Static_assert`-era notes; `bool`/`stdint.h` | recommended | Ch04/13 adv boxes |
| C12 | warnings (`-Wall -Wextra`), sanitizers, gdb basics | required | Ch02 + appendix |
| C13 | bit ops safety (shift width, signed shift) | advanced | Ch05 adv |
| C14 | `restrict`/`inline`/`_Generic` mention-only | can-wait | PART 7 survey |
| C15 | `setjmp/signal` survey-only | defer | PART 8 survey |
| C16 | alignment/padding (`sizeof` surprises) | advanced (before-DS) | Ch13 adv |
| C17 | `errno`/`strerror` file-error pattern | recommended | Ch15 |
| C18 | command-line parsing mini-pattern | recommended | Ch14 lab |

## External-source policy

- Allowed only: C standard drafts (public), GCC/Clang/MSVC docs, cppreference C, university notes. Tag [E].
- No full C23 survey in PHASE 1. Modern notes limited to table C11-C14 above.
- No web search was needed for PHASE 1 skeleton; [E] lookups deferred to writing phase.
