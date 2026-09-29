# Proposed C-Part TOC (draft, dependency-ordered)

- Skeleton: textbook 17 chapters. Reorder principles: functions before adv-pointers;
  array<->pointer taught together; struct+ptr+malloc = DS bridge; multi-file = practical.
- Tags: (Txx)=textbook ch, [Kx.y]=K&R boost, {+}=new per gap analysis.
- DS/Algo bodies: NOT in PHASE 1 (prereq list only).

## PART 1 — C와 프로그래밍 시작 (T01-03, K1.1)

1. 프로그래밍의 개념 (T01, trim history)
2. 프로그램 작성 과정: edit-compile-link-run, VS2022+gcc, warnings {-Wall} {+C12}
3. C 프로그램 구성요소: main/#include/printf/scanf (T03, K1.1/7.2/7.4)

## PART 2 — 기본 문법 (T04-07, K1-3)

4. 변수와 자료형 (T04, K2.1-2.4) + limits table [KB11] + overflow teaser {+C1}
5. 수식과 연산자 (T05, K2.5-2.12) + conversions {+C2} + precedence/UB box {+C3}
6. 조건문 (T06, K3.1-3.4/3.8) + dangling-else box {+B?} ; goto -> adv box
7. 반복문 (T07, K1.2/1.3/3.5-3.7) + Euclid/prime drills

## PART 3 — 함수와 프로그램 구조 (T08-09, K1.7-1.8/4.x)

8. 함수: def/call/value-params/prototype (T08, K1.7-1.8/4.1-4.2) + stack VISUAL
9. 변수 범위와 기억: scope/duration/linkage/static/extern (T09, K1.10/4.3-4.8) + globals rule
10. 순환 호출: recursion/Hanoi (T9.8, K4.10); quicksort = purpose-ref only
11. {+} TU/compile-vs-link preview -> full in PART 6 {+C9}

## PART 4 — 배열·포인터·메모리 (T10-11/14/17, K5.x) — heart of book

12. 배열: 1D/2D, decay, sort/search (T10, K1.6/1.9/5.7) VISUAL
13. 포인터 기초: `& *` NULL arithmetic (T11, K5.1-5.2/5.4) VISUAL + safety {+E-B}
14. 배열-포인터 관계: equivalence, `char*/char[]`, string impl (K5.3/5.5, T11.6/12) VISUAL
15. 포인터 심화: `**` ptr-array array-ptr decl-decode (T14.1-14.5, K5.6/5.8/5.9/5.12) VISUAL
16. const/volatile/void + argc/argv + function-ptr/callback (T14.6-14.8/14.4, K5.10-5.11) adv-split
17. 동적 메모리: malloc family + discipline + struct-nodes + list intro (T17, K6.4-6.5/B5, 8.7 teacher) VISUAL {+C4/C5}

## PART 5 — 문자·문자열·사용자정의 (T12-13, K5.5-5.6/6.x/7.7)

18. 문자와 문자열: ctype/string libs, safe I/O (T12, K5.5/B2-B3) + mutability rule
19. 구조체·공용체·열거형·typedef (T13, K6.1-6.4/6.7-6.8) + alignment adv {+C16}

## PART 6 — 파일·멀티파일·컴파일 (T15-16, K4.5/4.11/7.x/A10-11)

20. 스트림과 파일 입출력 (T15, K7.1/7.5-7.8) + stderr/exit/errno {+C8/C17}
21. 전처리와 다중 소스: macros/guards/headers/TU (T16, K1.4/4.5/4.11) + bit-field adv

## PART 7 — C 심화 (adv boxes collected)

22. UB/impl-defined/signed-shift/bit safety; `restrict/inline` survey; setjmp/signal survey {+C3/C13-15}

## PART 8 — 표준 라이브러리 (K App.B map)

23. stdio/stdlib/string/ctype/math/time/assert integrated + reference section (B1-B7/B10)

## PART 9+/10+ — DS/Algo connection (no body in PHASE 1)

- Prereqs before DS: functions, scope, arrays, pointers, strings, structs, dyn-mem, recursion, multi-file.
- Bridge nodes: 6.5 self-ref, Ch17 list, K4.10 quicksort-purpose, K6.6 lookup-design.

## Dependency map (short)

Ch2 tools -> Ch3 first-program -> Ch4/5 types+ops -> Ch6/7 flow -> Ch8/9 func+scope ->
Ch10/12 arrays+strings -> Ch11/13-14 ptr (+struct) -> Ch17 heap -> Ch15/16 files+multifile -> P7/P8.
Recursion (Ch10) after functions+stack idea. 2D arrays (Ch12) before array-ptr (Ch14).
