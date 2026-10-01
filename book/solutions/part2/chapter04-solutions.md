<!--
Part: 2
Chapter: 4
Type: Solutions
Manuscript source: book/part2/chapter04-variables-data-types.md
Manuscript status: APPROVED
Solution status: Draft 1 (manager review pending)
Baseline: C17
Toolchains: MSVC /std:c17 /W4 | GCC -std=c17 -Wall -Wextra
Coverage: exercises 1–14, all subquestions; #14 retains 〔심화·도전〕.
Policy: Separate full solutions; approved student manuscript remains questions + short hints only.
Toolchain verification (2026-10-02):
  New complete solution programs: #8 problem8_limits.c, #14 problem14_storage_record.c.
  GCC 14.2.0 (Debian 14.2.0-19), Linux x86_64:
    gcc -std=c17 -Wall -Wextra — both PASS, each 0 warnings/0 errors, runtime exit 0.
  MSVC: GitHub-hosted Windows Server 2025, image windows-2025-vs2026 20260925.250.1;
    Visual Studio Enterprise 2026 18.10.2, cl.exe 19.51.36260 x64.
    cl /std:c17 /W4 — both PASS, each 0 warnings/0 errors, runtime exit 0.
  Exact source SHA-256:
    #8 b5d2b71c8d2eb501e4d57ee73ed21883b8d26a3dc88ea0dcd5e5002692376e89
    #14 9fa05c497db68b7907d6b0f4dce217b2e9a8f645fc91c8c9458de1db6574aca0
  #9 signed-overflow example and #10 uninitialized-read example were NOT executed.
  Temporary MSVC workflow removed before finalization.
-->

# Chapter 4. 변수와 자료형 — 정답과 상세해설

> 본 문서는 Chapter 4 승인 원고의 연습문제에 대한 별도 정답·상세해설이다.

## 문제 1. 선언·초기화·대입과 출력 예측

### 정답

값의 변화는 다음과 같다.

| 실행한 문장 | `stored` | `added` |
|---|---:|---:|
| `int stored = 9;` | 9 | 아직 선언 전 |
| `int added = 4;` | 9 | 4 |
| `stored = stored + added;` | 13 | 4 |
| `added = 2;` | 13 | 2 |

따라서 출력은 다음 두 줄이다.

```text
13 2
15
```

선언과 초기화가 함께 이루어지는 문장은 다음 두 개다.

```c
int stored = 9;
int added = 4;
```

이미 선언된 변수에 새 값을 저장하는 대입은 다음 두 문장이다.

```c
stored = stored + added;
added = 2;
```

### 상세해설

`stored = stored + added;`를 읽을 때는 오른쪽을 먼저 계산한다. 당시 `stored`는 9이고 `added`는 4이므로 오른쪽의 결과는 13이다. 그 결과 13이 다시 `stored`에 저장된다. 이후 `added = 2;`가 실행되면 `added`의 현재 값만 2로 바뀐다.

대입은 객체에 저장된 값을 바꾸지만 변수의 이름이나 선언된 자료형을 바꾸지는 않는다. 마지막 출력문에서는 현재 값 13과 2를 더하므로 15가 나온다.

## 문제 2. 이름 검토

### 정답

| 이름 | 사용 가능 여부 | 이유 |
|---|---|---|
| `room_total` | 가능 | 영문자와 밑줄로 이루어진 올바른 식별자다. |
| `4th_room` | 불가 | 식별자는 숫자로 시작할 수 없다. |
| `return` | 불가 | C가 정한 키워드다. |
| `room total` | 불가 | 공백은 하나의 식별자 안에 들어갈 수 없다. |
| `RoomTotal` | 가능 | 올바른 식별자이며 대문자도 사용할 수 있다. |
| `room_total2` | 가능 | 숫자가 첫 글자가 아니므로 사용할 수 있다. |

모범 이름은 다음과 같다.

- 상자 수: `box_count`
- 상자 한 개의 질량: `unit_mass`

### 상세해설

C는 대소문자를 구별하므로 `RoomTotal`과 `room_total`은 서로 다른 식별자다. 문법에 맞는 이름이라고 해서 항상 좋은 이름인 것은 아니다. 역할을 알 수 있는 `box_count`, `unit_mass`처럼 의미가 드러나는 이름을 쓰는 편이 읽기 쉽다.

`box_count`와 `unit_mass`만 정답인 것은 아니다. 예를 들어 `box_total`, `mass_per_box`처럼 문법에 맞고 의미가 분명한 이름도 받아들일 수 있다.

## 문제 3. const의 의미

### 정답

1. **맞다.** `sample_limit`은 `const int`형 객체다.
2. **틀리다.** 이후 `sample_limit = 20;`처럼 그 객체에 새 값을 대입할 수 없다.
3. **틀리다.** 일반적인 지역 `const int sample_limit = 16;`의 이름은 C17에서 모든 정수 상수식 위치에 쓸 수 있다고 보장되지 않는다.
4. **틀리다.** `const` 객체와 `#define` 치환은 서로 다른 장치다.

정수 상수에 이름을 붙이는 한 가지 모범 예는 다음과 같다.

```c
#define SAMPLE_LIMIT 16
```

열거 상수를 사용하는 다음 형태도 가능하다.

```c
enum { SAMPLE_LIMIT = 16 };
```

### 상세해설

`const int sample_limit = 16;`은 자료형이 있는 객체를 만들고, 그 이름을 통해 값을 수정하지 못하게 한다. 반면 `#define SAMPLE_LIMIT 16`은 객체를 만드는 선언이 아니라 전처리 단계의 치환이다.

`enum { SAMPLE_LIMIT = 16 };`의 `SAMPLE_LIMIT`은 열거 상수이며 정수 상수식에 사용할 수 있다. 여기서는 열거형의 전체 기능을 배우려는 것이 아니라, “수정할 수 없는 객체”와 “컴파일 중 정수 값이 필요한 곳에서 쓸 수 있는 이름”이 같은 개념이 아니라는 점만 구별하면 된다.

## 문제 4. 변수 저장 도식과 크기

### 정답

초기 상태를 개념적으로 그리면 다음과 같다.

```text
pieces : int
┌─────────────┐
│      7      │
└─────────────┘

mass : double
┌─────────────┐
│    1.75     │
└─────────────┘
```

`pieces = 12;` 이후에는 `pieces`에 저장된 값만 바뀐다.

```text
pieces : int
┌─────────────┐
│     12      │
└─────────────┘

mass : double
┌─────────────┐
│    1.75     │
└─────────────┘
```

실제 바이트 수를 확인하는 식은 다음과 같다.

```c
sizeof(pieces)
sizeof(mass)
```

자료형 자체로 확인하려면 다음처럼 쓸 수도 있다.

```c
sizeof(int)
sizeof(double)
```

### 상세해설

그림의 상자 폭은 이름·자료형·현재 값을 구별하기 위한 **개념도**다. 실제 주소, 실제 바이트 수, 두 객체의 물리적인 폭 비율을 나타내지 않는다.

승인된 Chapter 4의 프로젝트 측정 환경에서는 GCC와 MSVC 모두 `sizeof(int) == 4`, `sizeof(double) == 8`이었다. 그러나 이 숫자는 해당 대상 환경에서 측정한 결과다. C 표준이 모든 구현에서 `int`를 반드시 4바이트, `double`을 반드시 8바이트로 만들도록 정한 것은 아니다.

## 문제 5. sizeof 코드 고치기

### 정답

`size_t`를 직접 선언하여 사용한다는 사실을 드러내려면 `<stddef.h>`를 포함하고 다음처럼 고칠 수 있다.

```c
#include <stddef.h>

size_t bytes = sizeof(long);
printf("%zu\n", bytes);
```

### 상세해설

`sizeof`의 결과형은 `size_t`다. 따라서 결과를 저장하는 변수도 `size_t`로 선언하는 것이 자연스럽고, `printf`에서는 `size_t`와 맞는 `%zu`를 사용한다.

현재 환경에서 `sizeof(long)`의 값이 4나 8처럼 작은 숫자라고 해서 `%d`를 사용해도 되는 것은 아니다. 형식 지정자는 숫자의 크기가 아니라 **실제로 전달하는 인수의 자료형**에 맞춰야 한다.

## 문제 6. 측정값과 표준의 보장

### 정답

승인된 Chapter 4의 프로젝트 측정값은 다음과 같다.

| 자료형 | Linux / GCC 13.3.0 | Windows / MSVC 19.51.36257 |
|---|---:|---:|
| `char` | 1 | 1 |
| `short` | 2 | 2 |
| `int` | 4 | 4 |
| `long` | 8 | 4 |
| `long long` | 8 | 8 |
| `float` | 4 | 4 |
| `double` | 8 | 8 |
| `long double` | 16 | 8 |
| `CHAR_BIT` | 8 | 8 |

문장의 분류는 다음과 같다.

1. `sizeof(char) == 1` → **C의 보장이다.**
2. “이 실습에서 `CHAR_BIT`가 8이었다.” → **측정 결과다.**
3. “이 실습에서 `sizeof(long)`의 결과가 4 또는 8이었다.” → **측정 결과다.** 프로젝트에서는 MSVC가 4, GCC가 8이었다.
4. “같은 이름의 자료형이면 모든 환경에서 바이트 수가 같다.” → **틀린 주장이다.**

4번은 다음처럼 고칠 수 있다.

> 표준이 허용하는 범위 안에서 기본 자료형의 정확한 크기는 구현에 따라 달라질 수 있으므로, 대상 환경에서 `sizeof`와 한계 헤더를 확인한다.

### 상세해설

`sizeof(char)`가 1이라는 사실과 “1바이트가 8비트다”라는 주장은 다르다. C에서 바이트는 `char` 객체 하나의 크기를 기준으로 하는 단위이고, 한 바이트의 비트 수는 `CHAR_BIT`로 확인한다. 이번 프로젝트 두 환경에서는 `CHAR_BIT`가 8이었지만 이것을 모든 C 환경의 보장으로 바꾸어 말하면 안 된다.

이 표는 **모범 프로젝트 측정값**이다. 학습자가 자신의 다른 컴파일러나 대상 환경에서 측정하면 값이 달라질 수 있다.

## 문제 7. 정수형과 출력 형식 선택

### 정답

| 변수 | 자료형 | 맞는 형식 지정자 |
|---|---|---|
| `offset` | `int` | `%d` |
| `count` | `unsigned int` | `%u` |
| `distance` | `long` | `%ld` |
| `total` | `long long` | `%lld` |

`6000000000`을 저장할 때 `long`을 무조건 고르면 안 된다. `long`의 표현 범위가 구현에 따라 다를 수 있기 때문이다.

승인 원고의 프로젝트 측정값은 다음과 같았다.

- Windows / MSVC: `LONG_MAX = 2147483647`
- Linux / GCC: `LONG_MAX = 9223372036854775807`

따라서 6000000000은 이 GCC 환경의 `long`에는 들어가지만, 이 MSVC 환경의 `long`에는 들어가지 않는다.

확인할 매크로는 `LONG_MIN`과 `LONG_MAX`이다. `long long`의 최대 범위를 확인하려면 `LLONG_MAX`도 사용할 수 있다.

### 상세해설

형식 지정자는 값이 “작아 보이는가, 커 보이는가”로 정하지 않는다. `distance`가 90000이라는 비교적 작은 값을 가지고 있어도 자료형이 `long`이므로 `%ld`를 사용한다. 마찬가지로 `total`은 `long long`이므로 `%lld`를 사용한다.

자료형을 선택할 때는 현재 저장값뿐 아니라 앞으로 필요한 값의 범위가 해당 구현의 한계 안에 들어가는지도 확인해야 한다.

## 문제 8. 한계 조회 프로그램 작성

### 정답

다음은 한 가지 모범 프로그램이다.

```c
#include <stdio.h>
#include <limits.h>

int main(void)
{
    printf("INT_MIN: %d\n", INT_MIN);
    printf("INT_MAX: %d\n", INT_MAX);
    printf("LONG_MIN: %ld\n", LONG_MIN);
    printf("LONG_MAX: %ld\n", LONG_MAX);
    printf("UINT_MAX: %u\n", UINT_MAX);
    return 0;
}
```

이번 해설 검증의 Linux/GCC 실제 출력은 다음과 같았다.

```text
INT_MIN: -2147483648
INT_MAX: 2147483647
LONG_MIN: -9223372036854775808
LONG_MAX: 9223372036854775807
UINT_MAX: 4294967295
```

Windows/MSVC 실제 출력은 다음과 같았다.

```text
INT_MIN: -2147483648
INT_MAX: 2147483647
LONG_MIN: -2147483648
LONG_MAX: 2147483647
UINT_MAX: 4294967295
```

### 상세해설

`INT_MIN`, `INT_MAX`, `LONG_MIN`, `LONG_MAX`, `UINT_MAX`는 `<limits.h>`가 제공하는 한계 매크로다. 숫자를 소스에 직접 복사하지 않고 대상 구현이 제공하는 한계를 조회하므로, 다른 환경에서도 같은 소스를 다시 빌드하여 그 환경의 값을 확인할 수 있다.

위 숫자는 실제 검증 환경에서 나온 **구현별 측정 결과**이지, 모든 C 구현이 반드시 똑같은 숫자를 사용해야 한다는 뜻은 아니다. 특히 `long`의 결과가 두 환경에서 달랐다는 점이 중요하다.

#### 실제 빌드·실행 확인

새로 작성한 위 프로그램을 실제로 검증했다.

- GCC 14.2.0, Linux x86_64: `gcc -std=c17 -Wall -Wextra problem8_limits.c -o problem8_limits` → PASS, 경고 0, 오류 0, exit 0.
- MSVC 19.51.36260 x64 / Visual Studio Enterprise 2026 18.10.2: `cl /std:c17 /W4 problem8_limits.c` → PASS, 경고 0, 오류 0, exit 0.

`scanf`를 사용하지 않으므로 C4996 조정은 필요하지 않았다.

## 문제 9. 범위를 넘는 계산 분류

### 정답

①의 코드는 **정의되지 않은 동작**을 일으킬 수 있는 오류 분석용 코드다.

```c
int signed_count = INT_MAX;
signed_count = signed_count + 1;
```

`INT_MAX + 1`은 `int`로 표현할 수 있는 범위를 넘는다. 따라서 결과가 항상 `INT_MIN`으로 순환한다고 예측하면 안 된다. 이 코드는 실행 결과를 관찰할 실험으로 사용하지 않는다.

②는 부호 없는 정수 연산의 정의된 규칙을 따른다.

```c
unsigned int unsigned_count = UINT_MAX;
unsigned_count = unsigned_count + 1U;
```

마지막 `unsigned_count`의 값은 **0**이다.

### 상세해설

부호 없는 정수 연산은 표현 가능한 범위를 기준으로 순환하는 규칙이 정의되어 있다. `UINT_MAX` 다음 값은 다시 0이 된다.

하지만 “언어 규칙이 정의되어 있다”와 “업무 결과가 올바르다”는 다른 문제다. `unsigned_count`가 실제 재고나 처리 건수를 뜻한다면 최대값 다음에 0이 되는 결과는 프로그램 요구사항에서는 오류일 수 있다. 따라서 `unsigned`를 모든 오버플로 문제의 해결책처럼 사용하면 안 된다.

이 해설에서는 ①의 부호 있는 오버플로 코드를 **실행하지 않았다.**

## 문제 10. 초기화 누락 찾기

### 정답

문제는 `processed`를 처음 읽을 때까지 값이 저장되지 않았다는 것이다.

원래 코드의 이 부분은 오른쪽에서 `processed`의 기존 값을 읽는다.

```c
processed = processed + received;
```

“처리한 개수는 0부터 시작한다”는 의도에 맞는 수정은 다음과 같다.

```c
int processed = 0;
int received = 5;
processed = processed + received;
printf("%d\n", processed);
```

수정한 코드의 출력은 다음과 같다.

```text
5
```

### 상세해설

초기화하지 않은 지역 자동 변수 `processed`의 값은 읽기 전에 정해져 있지 않다. 이 상태에서 오른쪽 피연산자로 읽는 것은 유효한 초기값을 얻는 방법이 아니며, 이 경우 정의되지 않은 동작으로 이어질 수 있다.

따라서 원래 프로그램이 어떤 “쓰레기 값”을 출력한다고 숫자를 예측해서는 안 된다. 의도가 누적 개수를 0에서 시작하는 것이라면 처음부터 `int processed = 0;`으로 초기화해야 한다.

원래 잘못된 코드는 **실행하지 않았다.**

## 문제 11. 부호 혼합 검토

### 정답

`int adjustment = -2;`와 `unsigned int stock = 3U;`를 비교할 때 “수학적으로 −2가 3보다 작다”는 사실만으로 C의 비교 결과를 판단하면 충분하지 않다.

서로 다른 정수형을 함께 비교하거나 계산하면 비교 전에 정수 변환이 일어날 수 있기 때문이다.

이 장에서 권장할 점검 습관은 다음과 같다.

1. 두 피연산자의 실제 자료형과 부호 여부를 먼저 확인한다.
2. 불필요한 signed/unsigned 혼합을 피한다.
3. 표현하려는 값의 영역에 맞는 자료형을 일관되게 선택한다.
4. 경고를 없애기 위한 목적으로 이유를 이해하지 못한 형변환을 덧붙이지 않는다.

### 상세해설

이 문제의 핵심은 아직 Chapter 5의 전체 변환 규칙표를 외우는 것이 아니다. 값만 보고 수학식처럼 비교하지 말고, **자료형도 계산의 일부**라는 사실을 인식하는 것이다.

어떤 변환이 정확히 적용되는지는 Chapter 5에서 다룬다. 지금 단계에서는 부호 혼합이 보이면 먼저 자료형과 필요한 범위를 확인하는 습관을 가지면 된다.

## 문제 12. 부동 소수점 관찰 해석

### 정답

승인 원고의 예제 F에서 두 검증 환경 모두 다음과 같이 관찰되었다.

```text
Total (2): 0.30
Total (17): 0.30000000000000004
```

`%.2f`를 `%.17f`로 바꾸어 표시해도 `total`을 다시 계산하는 것은 아니다. 같은 `total` 값을 서로 다른 출력 정밀도로 표시한 것이다.

### 상세해설

세 단계를 구별하면 이해하기 쉽다.

| 단계 | 이 예제에서의 의미 |
|---|---|
| 저장 | `first`, `second`, `total`이 `double` 객체에 값을 보관한다. |
| 계산 | `total = first + second;`에서 한 번 덧셈한다. |
| 표시 | `%.2f` 또는 `%.17f`가 같은 `total`을 몇 자리까지 화면에 보일지 정한다. |

이번에 사용한 구현의 유한한 2진 부동 소수점 표현에서는 0.1과 0.2 같은 많은 10진 소수를 정확히 표현할 수 없다. 더 긴 출력은 이미 계산된 근삿값의 특성을 더 잘 드러낸다. 출력 자릿수를 늘렸다고 저장된 값이나 계산 자체가 더 정확해진 것은 아니다.

또한 `FLT_DIG`는 “소수점 아래 정확한 자리 수”가 아니다. `float`의 **유효한 10진 자릿수 특성**과 관련된 매크로다. 소수점 앞뒤를 합친 유효 자릿수의 관점으로 이해해야 한다.

`0.30000000000000004`라는 정확한 마지막 문자열은 이번 프로젝트의 검증 환경에서 관찰된 결과다. 모든 C 구현이 반드시 같은 마지막 문자열을 출력한다고 일반화하지 않는다.

## 문제 13. 문자·문자열·이스케이프 구별

### 정답

| 표현 | 종류 |
|---|---|
| `'R'` | 문자 상수 |
| `"R"` | 문자열 리터럴 |
| `'\n'` | 줄바꿈 문자를 나타내는 문자 상수 |
| `"\n"` | 줄바꿈 문자 하나를 담은 문자열 리터럴 |

문자 하나를 `char`에 저장하려면 다음이 적합하다.

```c
char label = 'R';
```

문자열 리터럴을 `printf`로 출력할 때는 `%s`를 사용한다.

화면에 `data\today`를 한 줄로 표시하려면 다음과 같이 쓴다.

```c
printf("data\\today\n");
```

화면에 큰따옴표까지 포함한 `"Open"`을 표시하려면 다음과 같이 쓴다.

```c
printf("\"Open\"\n");
```

### 상세해설

작은따옴표로 둘러싼 `'R'`은 문자 상수이고, 큰따옴표로 둘러싼 `"R"`은 문자열 리터럴이다. 화면에서 둘 다 R처럼 보일 수 있어도 같은 종류의 표현이 아니다.

문자열 안에서 `\\`는 출력할 역슬래시 하나를 나타낸다. 따라서 소스의 `"data\\today\n"`에는 역슬래시를 표시하기 위한 이스케이프가 있고, 실제 출력에는 역슬래시 하나만 나타난다.

마찬가지로 `\"`는 문자열의 끝을 뜻하는 큰따옴표가 아니라, 문자열 안에 포함하여 출력할 큰따옴표를 나타낸다.

## 문제 14. 보관 기록 프로그램 작성 〔심화·도전〕

### 정답

요구사항을 모두 반영한 한 가지 모범 프로그램은 다음과 같다.

```c
#include <stdio.h>
#include <stddef.h>
#include <limits.h>

int main(void)
{
    int sample_count = 24;
    const double unit_mass = 0.0625;
    char zone = 'M';

    double total_mass = sample_count * unit_mass;
    size_t total_mass_bytes = sizeof(total_mass);

    printf("Samples: %d\n", sample_count);
    printf("Zone: %c\n", zone);
    printf("Total mass: %.4f kg\n", total_mass);
    printf("Total mass size: %zu bytes\n", total_mass_bytes);
    printf("INT_MAX: %d\n", INT_MAX);

    return 0;
}
```

수학적으로 총질량은 다음과 같다.

```text
24 × 0.0625 = 1.5
```

따라서 표시 결과에는 다음 줄이 포함된다.

```text
Total mass: 1.5000 kg
```

이번 GCC/MSVC 검증에서는 전체 출력이 다음과 같았다.

```text
Samples: 24
Zone: M
Total mass: 1.5000 kg
Total mass size: 8 bytes
INT_MAX: 2147483647
```

### 상세해설

각 형식 지정자의 선택 이유는 다음과 같다.

| 출력 대상 | 형식 | 이유 |
|---|---|---|
| `sample_count` | `%d` | `int` 값을 출력한다. |
| `zone` | `%c` | 문자 코드 값을 문자로 표시한다. |
| `total_mass` | `%.4f` | `double` 값을 소수점 아래 네 자리까지 표시한다. |
| `total_mass_bytes` | `%zu` | `size_t` 값을 출력한다. |
| `INT_MAX` | `%d` | `INT_MAX`가 나타내는 `int` 최댓값을 `int` 형식에 맞춰 출력한다. |

`unit_mass`는 문제에서 바꾸지 않는 기준 질량이므로 `const double`로 선언했다. `total_mass`는 `sample_count * unit_mass`의 계산 결과를 저장한다. `sizeof(total_mass)`의 결과형은 `size_t`이므로 별도 변수도 `size_t`로 선언했다.

이번 검증 환경에서는 `sizeof(double)`이 8이어서 `Total mass size: 8 bytes`가 출력되었고, `INT_MAX`는 2147483647이었다. 이 두 숫자는 해당 구현에서 관찰한 결과다. C 표준의 모든 구현에서 객체 크기와 모든 한계값이 반드시 같은 숫자라고 일반화하지 않는다.

#### 실제 빌드·실행 확인

새로 작성한 위 프로그램을 실제로 검증했다.

- GCC 14.2.0, Linux x86_64: `gcc -std=c17 -Wall -Wextra problem14_storage_record.c -o problem14_storage_record` → PASS, 경고 0, 오류 0, exit 0.
- MSVC 19.51.36260 x64 / Visual Studio Enterprise 2026 18.10.2: `cl /std:c17 /W4 problem14_storage_record.c` → PASS, 경고 0, 오류 0, exit 0.

두 환경 모두 실제 stdout가 위 모범 출력과 일치했다.
