# Source A Structure — C Express Rev.4 (textbook)

- SOURCE: Textbook scan `c언어 압축 (1).pdf` (750 PDF pp). TOC verified visually, PDF pp.10-17 = book pp.8-15.
- Body spot-check: PDF p.~455 (book p.453, `&` op + memory figs), PDF p.~595 (book p.593, `**q` double pointer + figs).
- Legend: titles = VERIFIED from TOC. `(i)` = concept label inferred from title (low-risk). `VISUAL` = figure-heavy page confirmed or strongly implied.
- Book p. = printed page number from TOC. PDF p. approx = book p. + 2.
- Copyright: titles + short labels only. No body/code copy.

## Chapter 01 프로그래밍의 개념 (book 18-45)

| Sec | Title | Concepts (i) | Syntax/API | Pre -> Next |
|---|---|---|---|---|
| 1.1 | 프로그래밍이란? | program=instruction list; universal machine; app | - | - -> 1.2 |
| 1.2 | 프로그래밍 언어 | low/high-level; compiler vs interpreter (i) | - | 1.1 -> 1.3 |
| 1.3 | C언어의 소개 | history; features; VS2022 (i) | - | 1.2 -> 1.4 |
| 1.4 | 알고리즘이란? | algorithm; flowchart; pseudo (i) | - | 1.3 -> Lab |
| Lab | 프린터 고장 수리 알고리즘 (verified book p.41) | repair-decision procedure | - | 1.4 |
| Lab | 성적 평균 계산기 | average algorithm | - | Lab |
| MiniProject | 숫자 리스트에서 최대값 찾는 알고리즘 | linear max scan (i) | - | Ch01 end |
| Q&A / Exercise | Ch01 review | - | - -> Ch02 |

## Chapter 02 프로그램 작성 과정 (book 50-86)

| Sec | Title | Concepts (i) | Syntax/API | Pre -> Next |
|---|---|---|---|---|
| 2.1 | 프로그램 개발 과정 | edit-compile-link-run; errors: syntax/link/logic (i) | cl / VS build | Ch01 -> 2.2 |
| 2.2 | 통합 개발 환경 | IDE; VS2022 | - | 2.1 -> 2.3 |
| 2.3 | 비주얼 스튜디오 설치 | install | - | 2.2 -> 2.4 |
| 2.4 | 비주얼 스튜디오 사용하기 | project; build; run | - | 2.3 -> 2.5 |
| 2.5 | 예제 프로그램의 간단한 설명 | first C program walkthrough (i) | `printf` | 2.4 -> 2.6 |
| 2.6 | 예제 프로그램의 응용 | modify-and-run (i) | - | 2.5 -> Lab |
| Lab | 간단한 계산기 해보자 | arithmetic program | `scanf`,`printf` | 2.6 |
| Lab | 구구단을 출력해보자 | loop preview (i) | - | Lab |
| 2.7 | 오류 수정 | compile errors; debugging basics (i) | - | Lab -> Mini |
| MiniProject | 오류를 처리해보자 | error-fix drill | - | -> Ch03 |
| Q&A/Summary/Exercise/Programming | review + first coding | - | - | - |

## Chapter 03 C 프로그램 구성요소 (book 88-120)

| Sec | Title | Concepts (i) | Syntax/API | Pre -> Next |
|---|---|---|---|---|
| 3.1 | 덧셈 프로그램 #1 | main; `#include`; `return` | `int main(void)` | Ch02 -> 3.2 |
| 3.2 | 주석 | `//`, `/* */` | - | 3.1 -> 3.3 |
| 3.3 | 전처리기 | `#include <stdio.h>`; directive vs statement (i) | `#include` | 3.2 -> 3.4 |
| 3.4 | 함수 | call; args; return (preview) | `printf` | 3.3 -> 3.5 |
| 3.5 | 변수 | declaration; `=`; memory box model | `int` | 3.4 -> 3.6 |
| 3.6 | 수식과 연산 | expression; operator preview | `+ - * / %` | 3.5 -> 3.7 |
| 3.7 | printf() | format specifiers | `%d %f %c %s`, `\n` | 3.6 -> 3.8 |
| Lab | 사칙 연산 | four operations | - | 3.7 |
| 3.8 | scanf() | input; address-of preview (`&`) | `%d`, `&` | 3.7 -> 3.9 |
| 3.9 | 덧셈 프로그램 #2 | assemble full program (i) | - | 3.8 -> Lab |
| Lab | 원의 면적 / 환율계산 / 평균 계산하기 | applied mini programs | - | 3.9 |
| MiniProject | 사각형의 둘레와 면적 (verified book p.116) | rect w*h, 2*(w+h); rect_area.c | - -> Ch04 | - |

## Chapter 04 변수와 자료형 (book 124-162)

| Sec | Title | Concepts (i) | Syntax/API | VISUAL |
|---|---|---|---|---|
| 4.1 | 변수와 상수 | lvalue; naming rules; `const` preview | identifiers, `const` | - |
| 4.2 | 자료형 | type-size; `sizeof` (i) | `sizeof` | memory boxes |
| 4.3 | 정수형 | `short/int/long`; signed/unsigned; overflow (i) | `%d %u %ld`, limits | range figs |
| 4.4 | 부동 소수점형 | `float/double`; precision; rounding error (i) | `%f %e` | - |
| 4.5 | 문자형 | `char`; ASCII; escape seq | `%c`, `\n \t \\` | ASCII table |
| Lab | 변수의 초기값 | uninitialized garbage (i) | - | demo |
| MiniProject | 태양빛 도달 시간 계산 | distance/speed program | - | - |
| Q&A/Summary/Exercise/Programming | review | - | - | - |
## Chapter 05 수식과 연산자 (book 166-215)

| Sec | Title | Concepts (i) | Syntax/API |
|---|---|---|---|
| 5.1 | 수식과 연산자 | expression; precedence preview | - |
| 5.2 | 산술 연산자 | `+ - * / %`; int division trap | `/`, `%` |
| Lab | 거스름돈 계산하기 (verified book p.174) | change; `%`, `/`; change.c | - |
| 5.3 | 대입 연산자 | `=`; compound `+= -= *= /= %=` | `+=` etc |
| 5.4 | 관계 연산자 | `== != < > <= >=`; 0/1 result | - |
| 5.5 | 논리 연산자 | `&& \|\| !`; short-circuit (i) | - |
| Lab | 윤년 판단 | leap-year logic | - |
| 5.6 | 조건 연산자 | `?:` | `?:` |
| 5.7 | 콤마 연산자 | `,` sequencing (i) | `,` |
| 5.8 | 비트 연산자 | `& \| ^ ~ << >>`; bit demo | bit ops |
| Lab | 십진수를 이진수로 출력하기 | binary print | `>>`, `&` |
| Lab | XOR를 이용한 암호화 | XOR cipher | `^` |
| 5.9 | 형변환 | implicit vs `(type)` cast | cast |
| 5.10 | 연산자의 우선 순위와 결합 규칙 | precedence table | - |
| Lab | 화씨 온도를 섭씨로 바꾸기 | conversion formula | - |

## Chapter 06 조건문 (book 220-253)

| Sec | Title | Concepts (i) | Syntax/API |
|---|---|---|---|
| 6.1 | 제어문 | control flow; block `{}` | `{}` |
| 6.2 | if 문 | branching; dangling-else preview (i) | `if` |
| 6.3 | if-else 문 | two-way branch | `if-else` |
| 6.4 | 다중 if 문 | `else if` ladder | `else if` |
| Lab | 이차 방정식 | quadratic solver | - |
| Lab | 산술 계산기 | calculator with if | - |
| 6.5 | switch 문 | fall-through; `break` | `switch-case-break-default` |
| Lab | 산술 계산기(switch 버전) | same calc via switch | - |
| 6.6 | goto 문 | goto/label; discourage (i) | `goto` |
| MiniProject | 소득세 계산기 만들기 | bracket logic | - |

## Chapter 07 반복문 (book 258-308)

| Sec | Title | Concepts (i) | Syntax/API |
|---|---|---|---|
| 7.1 | 반복의 개념 | loop; counter pattern | - |
| 7.2 | while 문 | pre-test loop | `while` |
| 7.3 | 반복 루프에서 보조문 사용하기 | helper statements (accumulate) (i) | - |
| Lab | 최대 공약수 찾기 | Euclid (i) | `%` |
| Lab | 반감기 | half-life simulation | - |
| 7.4 | do...while 문 | post-test loop | `do-while`, `;` |
| Lab | 숫자 추측 게임 | guessing + `rand` preview | - |
| 7.5 | for 문 | init-cond-incr; for<->while equiv | `for` |
| 7.6 | 중첩 반복문 | nested loops; pattern print | - |
| Lab | 직각 삼각형 찾기 | Pythagorean triples (i) | - |
| 7.7 | 무한 루프와 break, continue | `break`; `continue`; infinite loop | `break`, `continue` |
| Lab | 파이 구하기 / 복리 이자 계산 / 자동으로 수학문제 생성하기 / 도박사의 확률 | numeric simulations | - |

## Chapter 08 함수 (book 314-360)

| Sec | Title | Concepts (i) | Syntax/API |
|---|---|---|---|
| 8.1 | 함수란? | black-box; reuse | call syntax |
| 8.2 | 함수의 정의 | def vs call; `void` | `return` |
| 8.3 | 매개 변수와 반환값 | params; return value; call-by-value preview | - |
| Lab x6 | 생일 축하 / get_integer / add / 팩토리얼 / 온도 변환 / 조합 계산 | param/return drills | - |
| Lab | 소수 찾기 | prime test | - |
| 8.4 | 함수 원형 | prototype; header order (i) | prototype `;` |
| 8.5 | 표준 라이브러리 함수(난수) | `rand/srand/time` | `rand()`, `srand()` |
| Lab | 동전던지기 게임 / 자동차 경주 프로그램 | random sims | - |
| 8.6 | 표준 라이브러리 함수(수학 함수) | `<math.h>` link (`-lm` note) (i) | `sqrt pow sin cos` |
| Lab | 시간 맞추기 게임 / 나무 높이 측정 / 삼각함수 그리기 | applied math | - |
| 8.7 | 함수를 사용하는 이유 | decomposition; top-down (i) | - |
| MiniProject | 공학용 계산기 프로그램 작성 | multi-func program | - |
| Advanced Topic | 모듈이란? (verified book p.353) | modularization; cohesion/coupling | ADVANCED |
## Chapter 09 변수 범위와 순환 호출 (book 366-398)

| Sec | Title | Concepts (i) | Syntax/API |
|---|---|---|---|
| 9.1 | 변수의 속성 | scope vs duration vs linkage (i) | - |
| 9.2 | 지역 변수 | block scope; auto duration | `{}` scope |
| 9.3 | 전역 변수 | file scope; extern preview; overuse warn (i) | - |
| 9.4 | 생존 시간 | `auto/static/register` intro | `static` |
| Lab | 은행 계좌 구현하기 | static balance retains value | `static` |
| Lab | 한 번만 초기화하기 | one-time init | - |
| 9.5 | 연결 | internal/external linkage; `extern` (i) | `extern` |
| 9.6 | 어떤 저장 유형을 사용하여야 하는가? | storage-class guide | `auto static extern register` |
| Lab | 난수 발생기 작성(Linear Congruential Generator) | LCG with static state | - |
| 9.7 | 가변 매개 변수 함수 | `...`; `<stdarg.h>` preview (i) | `...` |
| 9.8 | 순환 호출 | recursion; base case; stack preview | - |
| MiniProject | 하노이 탑 | classic recursion | - |
| Advanced Topic | 스텁 기법 (verified book p.393) | stub-based top-down test | ADVANCED |

## Chapter 10 배열 (book 402-444)

| Sec | Title | Concepts (i) | Syntax/API | VISUAL |
|---|---|---|---|---|
| 10.1 | 배열이란? | contiguous; 0-index; `a[i]` | `int a[N]` | memory layout |
| 10.2 | 배열의 초기화 | init list; partial init zeros (i) | `{}` | - |
| Lab | 주사위 던지기 / 극장 예약 시스템 / 최소값 찾기 | frequency; seat map; min scan | - | - |
| 10.3 | 배열과 함수 | array decay preview; pass to func | `f(int a[], int n)` | decay fig |
| 10.4 | 정렬 | selection/bubble (i) | - | swap figs |
| 10.5 | 탐색 | linear/binary (i) | - | - |
| 10.6 | 2차원 배열 | row-major; `[r][c]`; init | `a[R][C]` | 2D layout |
| Lab | 영상 처리 | 2D pixel ops | - | image |
| MiniProject | TIC-TAC-TOE 게임 | 2D board game | - | - |

## Chapter 11 포인터 (book 452-489) — body verified p.453

| Sec | Title | Concepts (i) | Syntax/API | VISUAL |
|---|---|---|---|---|
| 11.1 | 포인터란? | address per byte; var->memory mapping | address | memory boxes, confirmed |
| 11.2 | 간접 참조 연산자 * | `&` address-of; `*` dereference | `&`, `*`, `int *p` | `&i &c &f` fig |
| Lab | 임베디드 프로그래밍 체험 #1 | address/hardware taste | - | - |
| 11.3 | 포인터 사용시 주의할 점 | uninit; NULL; dangling preview (i) | `NULL` | - |
| 11.4 | 포인터 연산 | `p+1` scales by type size (i) | `p++, p--, p+n` | arithmetic fig |
| 11.5 | 포인터와 함수 | call-by-address; out-param; swap | `swap(&a,&b)` | stack fig |
| 11.6 | 포인터와 배열 | `a == &a[0]`; `*(p+i)` | `*(p+i)` | array-ptr fig |
| Lab | 영상 처리 | ptr-based pixels | - | image |
| 11.7 | 포인터 사용의 장점 | why pointers exist (i) | - | - |
| MiniProject | 자율 주행 자동차 | applied (sensor/loop) (i) | - | - |

## Chapter 12 문자와 문자열 (book 496-538)

| Sec | Title | Concepts (i) | Syntax/API |
|---|---|---|---|
| 12.1 | 문자와 문자열 | `char` vs `char[]`; `'\0'` | `'\0'` |
| 12.2 | 문자 입출력 라이브러리 | `getchar/putchar` | `getchar`, `putchar` |
| 12.3 | 문자열 입출력 라이브러리 | `gets_s/fgets/puts` safety (i) | `fgets`, `puts` |
| 12.4 | 문자 처리 라이브러리 | `<ctype.h>` | `isalpha isdigit toupper` |
| Lab | 단어 세기 / 유효한 암호 확인 | count; validate | - |
| 12.5 | 문자열 처리 라이브러리 함수 | `<string.h>` | `strlen strcpy strcat strcmp` |
| Lab | 단답형 퀴즈 | string compare quiz | `strcmp` |
| 12.6 | 문자열 수치 변환 | `atoi/atof/strtol` (i) | `atoi`, `atof` |
| Lab | 영상 파일 이름 자동 생성 | `sprintf` names | `sprintf` |
| 12.7 | 문자열 여러 개를 저장하는 방법 | `char *argv[]`-style ptr array (i) | `char *s[]` |
| Lab | 한영 사전의 구현 / 메시지 암호화 | lookup; cipher | - |
| MiniProject | 행맨 게임 | string game | - |
## Chapter 13 구조체 (book 544-585)

| Sec | Title | Concepts (i) | Syntax/API |
|---|---|---|---|
| 13.1 | 구조체란 무엇인가? | heterogeneous aggregate | `struct` |
| 13.2 | 구조체의 선언, 초기화, 사용 | tag; member `.`; init | `struct S {...};`, `.` |
| Lab | 2차원 공간 상의 점을 구조체로 / 사각형을 점과 구조체로 | point/rect modeling | - |
| 13.3 | 구조체의 배열 | array of struct | `struct P arr[N]` |
| 13.4 | 구조체와 포인터 | `->`; struct ptr | `->` |
| 13.5 | 구조체와 함수 | pass by value vs ptr (i) | - |
| Lab | 벡터 연산 | vector add/dot (i) | - |
| 13.6 | 공용체 | `union`; shared storage | `union` |
| 13.7 | 열거형 | `enum`; named constants | `enum` |
| 13.8 | typedef | alias; `POINT` pattern | `typedef` |
| Lab | 점을 POINT 타입으로 정의하기 | typedef drill | - |
| MiniProject | 사자 성어 퀴즈 프로그램 | struct table quiz | - |

## Chapter 14 포인터 활용 (book 592-624) — body verified p.593

| Sec | Title | Concepts (i) | Syntax/API | VISUAL |
|---|---|---|---|---|
| 14.1 | 이중 포인터 | `int **q`; `*` count = level (verified) | `**` | `**q` boxes, confirmed |
| 14.2 | 포인터 배열 | `int *a[N]`; string tables | `*a[N]` | table fig |
| 14.3 | 배열 포인터 | `int (*p)[N]` vs `int *p[N]` contrast | `(*p)[N]` | contrast fig |
| 14.4 | 함수 포인터 | `int (*f)(...)`; callback; dispatch (i) | `(*f)()` | - |
| 14.5 | 다차원 배열과 포인터 | decay of 2D; ptr arithmetic on rows (i) | - | row figs |
| 14.6 | const 포인터와 volatile 포인터 | `const int*` vs `int* const`; volatile HW (i) | `const`, `volatile` | - |
| 14.7 | void 포인터 | generic ptr; cast required | `void*` | - |
| 14.8 | main 함수의 인수 | `argc/argv`; envp (i) | `argv` | - |
| Lab | 프로그램 인수 사용하기 / qsort() 함수 사용하기 | CLI args; `qsort`+comparator | `qsort` | - |
| MiniProject | 이분법으로 근 구하기 | bisection w/ func ptr (i) | - | - |

## Chapter 15 스트림과 파일 입출력 (book 630-664)

| Sec | Title | Concepts (i) | Syntax/API |
|---|---|---|---|
| 15.1 | 스트림 | stream abstraction; stdin/stdout/stderr | - |
| 15.2 | 파일의 기초 | `FILE*`; open modes | `fopen`, `fclose` |
| 15.3 | 텍스트 파일 읽기와 쓰기 | `fprintf/fscanf/fgets/fputs` | text API |
| Lab | 파일에서 특정 문자열 탐색 | grep-lite | - |
| 15.4 | 이진 파일 읽기와 쓰기 | `fread/fwrite`; text vs binary | `fread`, `fwrite` |
| Lab | 이진 파일에 학생 정보 저장하기 / 이미지 파일 복사하기 / 파일 압축(RLE) / 파일 암호화(XOR) | struct dump; copy; RLE; XOR | - |
| 15.5 | 임의 접근 | `fseek/ftell/rewind` | `fseek`, `ftell` |
| MiniProject | 주소록 만들기 | file DB program | - |

## Chapter 16 전처리 및 다중 소스 파일 (book 670-706)

| Sec | Title | Concepts (i) | Syntax/API |
|---|---|---|---|
| 16.1 | 전처리기란? | translation phases preview (i) | `#` directives |
| 16.2 | 단순 매크로 | `#define` const/expr; paren pitfalls (i) | `#define` |
| 16.3 | 함수 매크로 | params; side-effect trap (i) | `#define F(x)` |
| Lab | ASSERT 매크로 / 비트 매크로 작성 | assert; bit macros | `assert` |
| 16.4 | #ifdef, #endif | conditional compile | `#ifdef #endif` |
| Lab | 여러 가지 버전 정의하기 / 리눅스 버전과 윈도우 버전 분리 | platform split | - |
| 16.5 | #if, #else, #endif | expr conditionals | `#if #else` |
| 16.6 | 다중 소스 파일 | TU; header/impl; include guard | `#ifndef GUARD` |
| Lab | 헤더 파일 중복 포함 막기 | guard drill | - |
| 16.7 | 비트 필드 구조체 | `struct { unsigned f:3; }` | `:n` bits |
| Lab | 비트 필드와 공용체를 이용한 하드웨어 제어 | HW register map | - |
| MiniProject | 전처리기 사용하기 | applied macros | - |

## Chapter 17 동적 메모리 (book 712-740)

| Sec | Title | Concepts (i) | Syntax/API | VISUAL |
|---|---|---|---|---|
| 17.1 | 동적 할당 메모리란? | heap vs stack; lifetime (i) | - | heap fig |
| 17.2 | 동적 메모리 할당의 기본 | `malloc/free`; NULL check | `malloc`, `free` | alloc fig |
| Lab | 동적 배열을 이용한 성적 처리 | dyn array scores | - | - |
| 17.3 | calloc()과 realloc() | zero-init; resize/move (i) | `calloc`, `realloc` | - |
| Lab | 어떤 문자들이라도 저장하는 동적 메모리 | growable buffer | - | - |
| 17.4 | 구조체를 동적 생성해보자 | `malloc(sizeof(Node))`; `->` | `sizeof` | node fig |
| 17.5 | 연결 리스트란? | self-ref struct; traverse/insert (i) | - | list figs |
| Lab/MiniProject | 영화 관리 프로그램 | linked-list app | - | - |
| Advanced Topic | 수동 메모리 관리 vs 자동 메모리 관리 (verified book p.736) | manual-vs-GC; motivates free-discipline | ADVANCED | - |
| 찾아보기 (743) | index | - | - | - |

## Coverage check

- [x] 17/17 chapters, all numbered sections + Labs + MiniProjects from TOC.
- Titles verified 2026-09-29 vs scan: Ch03 Mini "사각형의 둘레와 면적" (p.116); Ch05 Lab "거스름돈 계산하기" (p.174); Ch08 Lab "자동차 경주 프로그램" (p.340, already correct). No approx markers remain.
- Ch08/Ch09/Ch17 Advanced Topics verified with titles+class in-table (pp.353/393/736).
