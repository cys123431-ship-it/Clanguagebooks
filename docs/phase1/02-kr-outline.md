# Source B Structure — K&R 2nd Ed (The C Programming Language)

- SOURCE: scan `C_Programming.pdf` (288 PDF pp). Full Contents verified visually, PDF pp.7-9 = book pp.v-vii.
- Section titles = VERIFIED verbatim. Concept/purpose rows derive directly from titles (compact, no body copy).
- Cols: `Diff` = E(easy) M(medium) H(hard). `Txt` = textbook chapter link. `Place` = suggested placement in our book.
- LEGACY tag = UNIX-era context to modernize, keep concept.

## Ch1 A Tutorial Introduction (book 5)

| Sec | Title (verified) | Core concept | Teaching purpose | Txt | Diff | Place |
|---|---|---|---|---|---|---|
| 1.1 | Getting Started | hello world; `main/printf/#include` | first run | Ch2/3 | E | intro |
| 1.2 | Variables and Arithmetic Expressions | vars; `while`; getchar loop; F-to-C | compute+loop taste | Ch3/4/7 | E | intro |
| 1.3 | The For Statement | `for` idiom | compact loop | Ch7 | E | basic |
| 1.4 | Symbolic Constants | `#define` vs magic numbers | named constants | Ch16 | E | basic |
| 1.5 | Character Input and Output | getchar/putchar; EOF; `wc` programs | stream thinking | Ch12/15 | M | basic |
| 1.6 | Arrays | counting array; histogram | array use | Ch10 | E | basic |
| 1.7 | Functions | power(); separation | first functions | Ch8 | E | basic |
| 1.8 | Arguments-Call by Value | value semantics; swap fails | value rule | Ch8/11 | M | core |
| 1.9 | Character Arrays | longest-line; string basics | char arrays | Ch10/12 | M | core |
| 1.10 | External Variables and Scope | extern; scope; `extern` decl | scope preview | Ch9 | M | core |

## Ch2 Types, Operators and Expressions (book 35)

| Sec | Title | Core concept | Teaching purpose | Txt | Diff | Place |
|---|---|---|---|---|---|---|
| 2.1 | Variable Names | naming; keywords | rules | Ch4 | E | basic |
| 2.2 | Data Types and Sizes | char/int/float/double; sizes impl-defined | type model | Ch4 | E | basic |
| 2.3 | Constants | literals; suffixes; string vs char | literal rules | Ch4 | E | basic |
| 2.4 | Declarations | decl syntax; init | declare+init | Ch4 | E | basic |
| 2.5 | Arithmetic Operators | `/ %` int traps | arithmetic | Ch5 | E | basic |
| 2.6 | Relational and Logical Operators | 0/1; `&& \|\|` | conditions | Ch5/6 | E | basic |
| 2.7 | Type Conversions | promotion; cast; pitfalls | conversion safety | Ch5 | M | core |
| 2.8 | Increment and Decrement Operators | `++/--`; idiom vs abuse | concise loops | Ch5/7 | M | core |
| 2.9 | Bitwise Operators | `& \| ^ ~ << >>`; masks | bit manipulation | Ch5 | M | advanced |
| 2.10 | Assignment Operators and Expressions | `op=`; assign-in-expr | compact assign | Ch5 | M | core |
| 2.11 | Conditional Expressions | `?:` | terse branch | Ch5 | E | core |
| 2.12 | Precedence and Order of Evaluation | table; UB (`i=i++`) preview | safe exprs | Ch5 | H | core |

## Ch3 Control Flow (book 55)

| Sec | Title | Core concept | Txt | Diff | Place |
|---|---|---|---|---|---|
| 3.1 | Statements and Blocks | `;` `{}` | Ch6 | E | basic |
| 3.2 | If-Else | branch; else-bind | Ch6 | E | basic |
| 3.3 | Else-If | ladder | Ch6 | E | basic |
| 3.4 | Switch | fall-through | Ch6 | E | basic |
| 3.5 | Loops-While and For | while/for; comma in for | Ch7 | E | basic |
| 3.6 | Loops-Do-while | post-test | Ch7 | E | basic |
| 3.7 | Break and Continue | early exit/skip | Ch7 | E | basic |
| 3.8 | Goto and Labels | goto; rare legit use | Ch6 | M | advanced |

## Ch4 Functions and Program Structure (book 67)

| Sec | Title | Core concept | Teaching purpose | Txt | Diff | Place |
|---|---|---|---|---|---|---|
| 4.1 | Basics of Functions | def/call/return; grep example | structure | Ch8 | E | core |
| 4.2 | Functions Returning Non-integers | declare before use; implicit-int trap (LEGACY C89 note) | prototypes matter | Ch8 | M | core |
| 4.3 | External Variables | globals; `extern` | sharing state | Ch9 | M | core |
| 4.4 | Scope Rules | 4 scopes summary | scope model | Ch9 | M | core |
| 4.5 | Header Files | `.h` interface; `my.h` pattern | modularity | Ch16 | M | core |
| 4.6 | Static Variables | persistent local; `static` | state hiding | Ch9 | M | core |
| 4.7 | Register Variables | `register` hint (LEGACY: modern compiler ignores) | history | Ch9 | E | LEGACY |
| 4.8 | Block Structure | nested scope; shadowing | shadowing | Ch9 | M | core |
| 4.9 | Initialization | init rules; uninit trap | safe init | Ch4/10 | M | core |
| 4.10 | Recursion | quicksort example; recursion model | recursion depth | Ch9 | H | core |
| 4.11 | The C Preprocessor | `#include/#define/cond` full tour | macro model | Ch16 | M | core |

## Ch5 Pointers and Arrays (book 93) — KEY chapter

| Sec | Title | Core concept | Teaching purpose | Txt | Diff | Place |
|---|---|---|---|---|---|---|
| 5.1 | Pointers and Addresses | `& *`; addr model | pointer basis | Ch11 | M | core |
| 5.2 | Pointers and Function Arguments | swap; `getint` (scanf model) | out-params | Ch11 | M | core |
| 5.3 | Pointers and Arrays | `*(pa+i)` == `a[i]` | array-ptr unity | Ch10/11 | H | core, VISUAL |
| 5.4 | Address Arithmetic | scaled arithmetic; `strcmp/alloc` idioms | ptr math | Ch11 | H | core, VISUAL |
| 5.5 | Character Pointers and Functions | `char *` vs `char[]`; strcpy family | string impl | Ch12 | H | core |
| 5.6 | Pointer Arrays; Pointers to Pointers | `char *argv[]`; `**` | tables of strings | Ch14 | H | advanced |
| 5.7 | Multi-dimensional Arrays | `int a[2][3]` row model | 2D truth | Ch10/14 | H | advanced, VISUAL |
| 5.8 | Initialization of Pointer Arrays | month-name table | lookup tables | Ch14 | M | advanced |
| 5.9 | Pointers vs. Multi-dimensional Arrays | `a` vs `char *p[]` layout contrast | layout truth | Ch14 | H | advanced, VISUAL |
| 5.10 | Command-line Arguments | `argc/argv`; mini-grep/echo | CLI programs | Ch14 | M | practical |
| 5.11 | Pointers to Functions | `(*f)()`; qsort/bisection use | callbacks | Ch14 | H | advanced |
| 5.12 | Complicated Declarations | `dcl` parser; reading types clockwise | decode decls | Ch14 | H | advanced |
## Ch6 Structures (book 127)

| Sec | Title | Core concept | Txt | Diff | Place |
|---|---|---|---|---|---|
| 6.1 | Basics of Structures | struct decl; `.` | Ch13 | E | core |
| 6.2 | Structures and Functions | struct ops; pass/return | Ch13 | M | core |
| 6.3 | Arrays of Structures | table of structs | Ch13 | M | core |
| 6.4 | Pointers to Structures | `->`; malloc-linked preview | Ch13/17 | M | core, VISUAL |
| 6.5 | Self-referential Structures | `struct tnode`; tree/list bridge | Ch17 | H | bridge-to-DS |
| 6.6 | Table Lookup | hash/binsearch on structs | Ch13 | H | advanced |
| 6.7 | Typedef | aliases; `Treeptr` | Ch13 | E | core |
| 6.8 | Unions | variant storage | Ch13 | M | advanced |
| 6.9 | Bit-fields | `:n`; flags (LEGACY impl-defined note) | Ch16 | M | advanced |

## Ch7 Input and Output (book 151)

| Sec | Title | Core concept | Txt | Diff | Place |
|---|---|---|---|---|---|
| 7.1 | Standard Input and Output | stdin/stdout; redirection (LEGACY unix flavor, concept keeps) | Ch15 | E | core |
| 7.2 | Formatted Output-Printf | full printf model | Ch3 | E | basic |
| 7.3 | Variable-length Argument Lists | `<stdarg.h>` min-printf | Ch9 | H | advanced |
| 7.4 | Formatted Input-Scanf | scanf model; `&` rationale | Ch3 | M | core |
| 7.5 | File Access | fopen/fclose/fgets file copy | Ch15 | M | core |
| 7.6 | Error Handling-Stderr and Exit | stderr; `exit`; ferror | Ch15 | M | practical |
| 7.7 | Line Input and Output | getline impl; buffer ownership | Ch12/15 | M | core |
| 7.8 | Miscellaneous Functions | system/ungetc etc survey | Ch15 | E | reference |

## Ch8 The UNIX System Interface (book 169) — mostly LEGACY-adapt

| Sec | Title | Core concept | Keep-as | Txt |
|---|---|---|---|---|
| 8.1 | File Descriptors | fd vs FILE* | concept only | Ch15 |
| 8.2 | Low Level I/O-Read and Write | `read/write` syscalls | concept only (POSIX note) | Ch15, ADVANCED |
| 8.3 | Open, Creat, Close, Unlink | low-level lifecycle | concept only | Ch15 |
| 8.4 | Random Access-Lseek | offset model | maps to fseek | Ch15 |
| 8.5 | Example-An Implementation of Fopen and Getc | stdio on syscalls | teaching value: buffering | Ch15, ADVANCED |
| 8.6 | Example-Listing Directories | dirent walk | skip or project idea | - |
| 8.7 | Example-A Storage Allocator | malloc impl (free-list) | teaching value: heap truth | Ch17, ADVANCED, VISUAL |

## Appendix A Reference Manual (book 191) — reference use only

A1 Intro; A2 Lexical; A3 Syntax notation; A4 Identifiers; A5 Objects/Lvalues; A6 Conversions;
A7 Expressions; A8 Declarations; A9 Statements; A10 External decls; A11 Scope/Linkage;
A12 Preprocessing; A13 Grammar.
- Use: disambiguation during writing (decl syntax, precedence, linkage). Not student-facing.

## Appendix B Standard Library (book 241) — maps to our PART 8

B1 `<stdio.h>`; B2 `<ctype.h>`; B3 `<string.h>`; B4 `<math.h>`; B5 `<stdlib.h>`;
B6 `<assert.h>`; B7 `<stdarg.h>`; B8 `<setjmp.h>`; B9 `<signal.h>`;
B10 `<time.h>`; B11 `<limits.h>`/`<float.h>`.
- B8/B9 = survey-only (advanced). Rest = integrate per-chapter + reference section.

## Appendix C Summary of Changes (book 259)

- C89 vs old-C delta. LEGACY value: explains implicit-int, void, prototypes.
- Our use: 1-page "why prototypes/manifest" note. Nothing student-facing beyond that.

## Coverage check

- [x] Ch1-8 all sections (titles verified). [x] App A/B/C surveyed.
- K&R examples analyzed by purpose only (no code copied): e.g. 1.5 char-count idioms -> stream chapter;
  4.10 quicksort -> recursion+partition preview (body stays in algorithm phase); 8.7 allocator -> heap mental model.
