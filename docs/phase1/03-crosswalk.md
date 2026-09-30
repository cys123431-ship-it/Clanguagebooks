# Textbook x K&R Crosswalk (concept level)

- Actions: CORE | K&R-ENHANCE | ADD | ADVANCED | LEGACY.
- Coverage: both | textbook | K&R | neither.
- `->` = placement in NEW architecture (Ch1-24 + App A-D). Source columns (Textbook/K&R) preserved unchanged.

## A. Intro / tooling (Txt Ch1-3)

| Textbook | Concept | K&R | Coverage | Action | Notes |
|---|---|---|---|---|---|
| Ch1 | programming/algorithm thinking | 1.x (tutorial use) | textbook | CORE | keep, trim history |
| Ch2 | edit-compile-link-run; VS2022 | - (preface/env) | textbook | CORE | modernize: gcc+VS both |
| Ch2 | error kinds (syntax/link/logic) | - | textbook | K&R-ENHANCE | add K&R-style terse examples purpose |
| Ch3 | main/#include/printf/scanf first use | 1.1, 7.2, 7.4 | both | CORE | order: output before input |
| Ch3 | `&` in scanf (preview) | 5.2 (full reason) | K&R stronger | K&R-ENHANCE | forward-ref to Ch12; VISUAL later |

## B. Types / operators (Txt Ch4-5)

| Textbook | Concept | K&R | Coverage | Action | Notes |
|---|---|---|---|---|---|
| Ch4 | variables/const/naming | 1.2, 2.1, 2.3, 2.4 | both | CORE | merge naming+literal rules |
| Ch4 | int/float/char sizes | 2.2 (+B11 limits) | both | K&R-ENHANCE | add `<limits.h>` peek |
| Ch4 | uninit variables | 4.9 | K&R stronger | K&R-ENHANCE | garbage demo purpose |
| Ch5 | arithmetic/relational/logical/`?:`/`,` | 2.5, 2.6, 2.10, 2.11 | both | CORE | - |
| Ch5 | `++/--` | 2.8 | K&R stronger | K&R-ENHANCE | idiom + abuse warning |
| Ch5 | bitwise ops | 2.9 | both | K&R-ENHANCE | mask/shift drills |
| Ch5 | conversions/casts | 2.7, A6 | K&R stronger | K&R-ENHANCE | promotion pitfalls |
| Ch5 | precedence/eval order | 2.12 | K&R only | K&R-ENHANCE | UB teaser (`i=i++`) -> modern-C note |
| Ch5 | overflow/signed-unsigned | A6/B11 (partial) | neither full | ADD | required; -> Ch4/5 boxes |

## C. Control flow (Txt Ch6-7)

| Textbook | Concept | K&R | Coverage | Action | Notes |
|---|---|---|---|---|---|
| Ch6 | if/else-if/switch/goto | 3.1-3.4, 3.8 | both | CORE | goto -> ADVANCED box |
| Ch6 | dangling-else | - (implied) | neither | ADD | recommended, 1-page |
| Ch7 | while/for/do-while | 1.2, 1.3, 3.5, 3.6 | both | CORE | - |
| Ch7 | break/continue | 3.7 | both | CORE | - |
| Ch8-lab | prime/combination loops | 1.x style | both | CORE | keep as drills |

## D. Functions / scope / program structure (Txt Ch8-9)

| Textbook | Concept | K&R | Coverage | Action | Notes |
|---|---|---|---|---|---|
| Ch8 | def/call/params/return/prototype | 1.7, 4.1, 4.2 | both | K&R-ENHANCE | implicit-int story -> why prototypes |
| Ch8 | call-by-value | 1.8 | K&R stronger | K&R-ENHANCE | swap-fails demo; VISUAL stack |
| Ch8 | rand/math lib | - (B4/B5) | textbook+B | CORE | keep; add seed note |
| Ch9 | scope/duration/linkage/auto/static/extern/register | 1.10, 4.3, 4.4, 4.6-4.8 | both | K&R-ENHANCE | unify terminology table |
| Ch9 | globals discipline | 4.3 | K&R stronger | K&R-ENHANCE | "minimize globals" rule |
| Ch9 | static (local+file) | 4.6 | both | CORE | LCG lab keep |
| Ch9 | recursion/Hanoi | 4.10 | both | K&R-ENHANCE | quicksort purpose-ref only (body in algo phase) |
| Ch9 | variadic (`...`) | 7.3 | K&R stronger | ADVANCED | -> Ch22 |
| Ch9 | init rules | 4.9 | K&R only | K&R-ENHANCE | -> Ch4 too |
| - | header-file interface thinking | 4.5 | K&R only | K&R-ENHANCE | -> Ch21 |
| - | `register` | 4.7 | K&R only | LEGACY | 1-line history note |

## E. Arrays / pointers / memory (Txt Ch10-11 + 14 + 17)

| Textbook | Concept | K&R | Coverage | Action | Notes |
|---|---|---|---|---|---|
| Ch10 | 1D arrays/init/0-index | 1.6, 1.9 | both | CORE | VISUAL layout |
| Ch10 | array->function (decay) | 1.9, 5.3 | K&R stronger | K&R-ENHANCE | decay rule explicit |
| Ch10 | sort/search | - (6.6 lookup adjacent) | textbook | CORE | selection+binary keep |
| Ch10 | 2D arrays row-major | 5.7 | K&R stronger | K&R-ENHANCE | VISUAL rows |
| Ch11 | address/`&`/`*`/NULL | 5.1 | both | K&R-ENHANCE | memory figs keep |
| Ch11 | pointer arithmetic (scaled) | 5.4 | K&R stronger | K&R-ENHANCE | critical; VISUAL |
| Ch11 | pointers as function args | 5.2 | K&R stronger | K&R-ENHANCE | swap/getint pattern |
| Ch11 | array-pointer equivalence | 5.3 | both | K&R-ENHANCE | critical; VISUAL |
| Ch11 | pointer safety (uninit/dangle) | - (implied) | textbook | ADD | required: harden 11.3 |
| Ch14 | `**` / ptr-array / array-ptr | 5.6, 5.8, 5.9 | both | K&R-ENHANCE | -> Ch16; 5.9 layout contrast critical; VISUAL |
| Ch14 | function pointers/callbacks | 5.11 | K&R only | ADVANCED | -> Ch22 (RECOMMENDED, not pre-DS) |
| Ch14 | complicated declarations | 5.12 | K&R only | ADVANCED | -> Ch16 moderate + Ch22 |
| Ch14 | const/volatile/void ptr | - (partial) | textbook | K&R-ENHANCE | SPLIT: const -> Ch16 (+Ch12 params); volatile -> Ch23; void* basics -> Ch17 |
| Ch14 | argc/argv | 5.10 | K&R stronger | K&R-ENHANCE | -> Ch19 (not adv pointers) |
| Ch17 | malloc/calloc/realloc/free | B5 + 8.7 (impl) | textbook | K&R-ENHANCE | 8.7 as teacher-only heap truth; VISUAL |
| Ch17 | struct+malloc; linked list | 6.4, 6.5 | both | K&R-ENHANCE | -> Ch18 separate DS-bridge chapter |
| - | malloc discipline (leak/double-free/UAF) | - | neither | ADD | required; Ch17 OWNERSHIP core |
| - | UB / impl-defined behavior | 2.12 tension | neither full | ADD | required; -> Ch24 (beginner box Ch4) |

## F. Strings / structs (Txt Ch12-13)

| Textbook | Concept | K&R | Coverage | Action | Notes |
|---|---|---|---|---|---|
| Ch12 | `'\0'`; char vs string | 1.9, 5.5 | both | K&R-ENHANCE | - |
| Ch12 | ctype/string libs | B2, B3 | both | CORE | keep labs |
| Ch12 | safe input (fgets vs gets) | 1.5, 7.7 | K&R stronger | K&R-ENHANCE | buffer-ownership note |
| Ch12 | `char*` vs `char[]` | 5.5 | K&R only | K&R-ENHANCE | critical literal-mutability rule |
| Ch12 | sscanf/sprintf numbers | 7.2, 7.4 | both | CORE | - |
| Ch12 | ptr-array string tables | 5.6, 5.8 | K&R stronger | ADVANCED | -> Ch16 string tables |
| Ch13 | struct/`.`/`->`/array/func | 6.1-6.4 | both | CORE | VISUAL |
| Ch13 | typedef/enum/union | 6.7, 6.8 | both | CORE | typedef-ptr warning |
| Ch13 | self-ref structs | 6.5 | K&R stronger | K&R-ENHANCE | -> Ch18 (after struct fundamentals) |
| Ch13 | table lookup design | 6.6 | K&R only | ADVANCED | project fodder |

## G. Files / preprocess / multi-file (Txt Ch15-16)

| Textbook | Concept | K&R | Coverage | Action | Notes |
|---|---|---|---|---|---|
| Ch15 | streams/FILE*/text+bin/random | 7.1, 7.5-7.8 | both | K&R-ENHANCE | add stderr/exit (7.6) |
| Ch15 | fopen modes/error check | B1, 7.5 | both | CORE | "always check fopen" rule |
| Ch15 | buffering (why flush) | 8.5 (teaching value) | K&R-impl | ADVANCED | teacher note, 1 box |
| Ch16 | macros/func-macros/assert | 1.4, 4.11 | both | CORE | paren/side-effect traps |
| Ch16 | cond-compile/platform split | 4.11 | both | CORE | - |
| Ch16 | headers/guards/multi-file | 4.5 + A10/A11 | K&R stronger | K&R-ENHANCE | -> Ch21; TU defined Ch9 first |
| Ch16 | bit-fields | 6.9 | both | ADVANCED | -> Ch23 |
| Ch8-ish | low-level fd/read/write | Ch8 (8.1-8.4) | K&R only | LEGACY | -> Ch19 optional adv box; POSIX note |
| - | compile-vs-link mental model | A10/A11 | neither full | ADD | required; Ch9 brief + Ch21 full |

## H. Stdlib survey (Appendix B -> our Appendix B reference)

| Area | Textbook | K&R | Action |
|---|---|---|---|
| stdio/stdlib/string/ctype/math/time/assert | scattered labs | B1-B7, B10 | CORE: teach contextually + App B lookup |
| stdarg/setjmp/signal | 9.7 preview | B6-B9 | variadic -> Ch22; setjmp/signal REFERENCE ONLY (App B) |
| limits/float | - | B11 | CORE: 1 table in Ch4 |

## Counts

- Rows: ~60. CORE ~25 | K&R-ENHANCE ~25 | ADD ~8 | ADVANCED ~12 | LEGACY ~3.
- Top K&R-ENHANCE targets: 1.8, 2.7, 2.12, 4.2, 5.2-5.5, 5.9-5.12, 6.5, 7.6.


