# Proposed C-Part TOC (FINAL architecture, manager-approved)

- Baseline: ISO C17 portable. C99 features free (`//`, for-decls, stdbool/stdint, snprintf); C11 adv-boxes only; C23 = notes only. Toolchain: VS2022/MSVC primary, GCC secondary verify. No VLAs.
- Skeleton: textbook 17 chapters reordered per prerequisite fixes. Tags: (Txx)=textbook ch, [Kx.y]=K&R boost, {Gxx}=gap ID.
- Stdlib = Appendix B reference (NOT a teaching PART). PART 9/10/11 = DS/Algo/Projects.
- DS/Algo bodies: NOT in PHASE 1 (prereq lists only).

## Global rules

- No VLAs in main examples. `.c` files; MSVC `/std:c17 /W4`; GCC `-std=c17 -Wall -Wextra`. No MSVC-only API as canonical solution (labeled notes only).
- Prereq fixes applied: struct fundamentals before dynamic structs/lists; strings before char*/argv material; TU defined before linkage; argc/argv in program-interface area.

## PART 1 — C와 프로그래밍의 시작

- Ch1 프로그래밍의 개념 (T01, trim history)
- Ch2 프로그램 작성 과정과 개발 도구: preprocess/compile/link/run; C17 baseline; VS2022 primary + GCC secondary; warnings {-Wall /W4}; sanitizer/debugger = brief mention only; portability box: `_CRT_SECURE_NO_WARNINGS` vs scanf_s/gets_s (standard code: fgets/widths/snprintf)
- Ch3 C 프로그램 구성요소: main/#include/printf/scanf (T03, K1.1/7.2/7.4) + mandatory scanf-return-value note

## PART 2 — 기본 문법

- Ch4 변수와 자료형 (T04, K2.1-2.4): sizeof, size_t, limits [KB11], signed/unsigned, overflow basics {GC1}, float, char, const vars, symbolic consts; #define/enum as compile-time consts; UB = short beginner box only
- Ch5 수식과 연산자 (T05, K2.5-2.12): arithmetic/assign/compare/logic/`?:`/`,`/basic-bit/casts/conversions/precedence + boxes: signed-vs-unsigned compare, promotion basics, unsequenced-expression dangers
- Ch6 조건문 (T06, K3.1-3.4/3.8); goto -> adv box
- Ch7 반복문 (T07, K1.2/1.3/3.5-3.7) + Euclid/prime drills; debugger basics = tool box here

## PART 3 — 함수와 프로그램 구조

- Ch8 함수 (T08, K1.7-1.8/4.1-4.2): def/call/params/return/value-params/prototype + stack VISUAL; "모듈이란?"/"스텁 기법" = optional boxes (not core)
- Ch9 변수의 범위·생존 기간·연결 (T09, K1.10/4.3-4.8): scope/duration/linkage/static/extern/globals-discipline; TU defined briefly BEFORE linkage; max tiny 2-file example; NO separate TU chapter
- Ch10 재귀: Hanoi stays (T9.8, K4.10); quicksort = purpose-ref only (full in Algorithms)

## PART 4 — 배열과 포인터

- Ch11 배열 (T10, K1.6/1.9/5.7): 1D/2D use/init/func-args/sort+search practice; no complexity analysis; VISUAL
- Ch12 포인터 기초 (T11, K5.1-5.2): address/`&`/`*`/NULL/init/ptr-params/swap/out-params/scanf-`&` rationale/`const T*` params/dangling basics/never-return-local; NO advanced arithmetic; VISUAL
- Ch13 포인터와 배열: ptr arithmetic IN array context, decay, a[i] vs *(a+i), sizeof behavior, arrays-to-functions (K5.3-5.4)

## PART 5 — 문자열과 구조체

- Ch14 문자와 문자열 (T12, K1.5/5.5/7.7, B2-B3): chars/`'\0'`/arrays/literals/char*-vs-char[]/literal-mutability/getchar-int-EOF/fgets/ctype/string.h/safe-input/strtol/snprintf; K&R ptr-string impls = enhancement concepts only
- Ch15 구조체와 사용자 정의 자료형 (T13, K6.1-6.4/6.7): struct/init/array-of-struct/`.`/`->`/passing/struct-ptrs/typedef/enum; union = brief core section; padding/alignment = short adv box

## PART 6 — 포인터 심화와 동적 메모리

- Ch16 포인터 심화 (T14.1-14.5, K5.6/5.8/5.9/5.12): `**`/ptr-arrays/string-tables/ptr-to-array/multidim/const-placement-table/moderate-decl-reading; EXCLUDES argc-argv/volatile/function-ptr-core; VISUAL
- Ch17 동적 메모리 (T17, KB5): malloc/calloc/realloc/free/void*-basics/`sizeof *p`/NULL-checks/realloc-tmp-ptr/dyn-arrays-strings-2D/OWNERSHIP model/leak-UAF-double-free; NULL-after-free = local habit only (does not fix aliases); Adv box "수동 메모리 관리 vs 자동 메모리 관리"; VISUAL
- Ch18 동적 구조체와 연결 리스트 입문 — SEPARATE, formal DS BRIDGE (not full DS chapter): dyn-struct-alloc/self-ref-struct/node/build/traverse/insert/free-all/head-update (return-new-head vs Node**)

## PART 7 — 파일과 프로그램 구성

- Ch19 스트림·파일 입출력과 프로그램 인터페이스 (T15, K7.x): FILE*/text/bin/random/stderr/exit-status/basic-errors + argc/argv HERE (not in adv pointers); low-level fds = optional adv box
- Ch20 전처리기 (T16.1-16.5, K1.4/4.11): #define/func-macros/parens/side-effects/cond-compile/assert
- Ch21 다중 소스 파일과 빌드 (T16.6, K4.5/A10-A11): TU/decl-vs-def/headers/guards/static-extern/interface-design/VS-multifile + gcc-multifile example; "모듈이란?" referenced again

## PART 8 — C 심화 (optional/advanced first pass)

- Ch22 함수 포인터와 제네릭 기법 (T14.4, K5.11): func-ptrs/callbacks/dispatch/void*-generic/qsort-bsearch/decl-decode/variadic; RECOMMENDED/ADVANCED, NOT mandatory before basic DS
- Ch23 저수준 C: adv-bit/shift-safety/bit-fields (T16.7, K6.9)/union-revisit/volatile/stdint/endianness/representation cautions
- Ch24 정의되지 않은 동작과 이식성: UB/impl-defined/unspecified/integer-rules/alignment/static-assert/inline-restrict-survey/_Generic-mention/C23-notes (not a C23 survey)

## Appendices (architecture only, no body)

- App A 개발 도구: VS2022/GCC/warnings/debugger/sanitizers
- App B 표준 라이브러리 레퍼런스 (lookup only; taught contextually; per-entry: prototype/semantics/return-errors/pitfall/where-taught — later)
- App C 빠른 참고표: precedence/formats/ASCII
- App D C의 역사와 K&R 스타일 읽기: implicit-int/old-defs/register/C89-delta/later-standards

## DS prerequisites (FINAL)

- MANDATORY BEFORE DS: functions; scope/duration; arrays; pointers; sizeof/size_t; structs; struct-ptrs; dyn-mem; NULL-checks; ownership-leak-UAF discipline.
- Recursion: mandatory before tree/graph-recursive units only (not for first list/stack/queue).
- USEFUL BEFORE DS: `**`; ptr-arithmetic; typedef; strings; multifile; realloc; const-ptr-params; assert.
- CAN LEARN DURING DS: enum; func-ptrs; callbacks; void*-generics; bit-ops.
- NOT REQUIRED: union; file-IO; argv.

## Dependency map

Ch2 tools -> Ch3 first-program -> Ch4/5 types+ops -> Ch6/7 flow -> Ch8/9/10 func+scope+recursion ->
Ch11 arrays -> Ch12/13 basic-ptr+array-ptr -> Ch14/15 strings+structs -> Ch16/17/18 adv-ptr+heap+list-bridge ->
Ch19/20/21 files+preprocess+multifile -> P8 adv -> App.

