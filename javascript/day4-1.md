# 연산자(Operator) 살펴보기
## 우리에게 익숙한 사칙연산 - 산술연산자
- `+` 덧셈 연산자
    - `1 + 2` => 3
    - `'문자열' + 15` => `'문자열15'`
- `-` 뺄셈 연산자
    - `15 - 30` => `-15`
- `*` 곱하기 연산자
    - `10 * 100` => `1000`
- `/` 나누기 연산자
    - `24 / 5` => `4.8`
    - `10 / 3` => `3.3333333333333335`
- `%` 나머지 연산자
    - `10 % 3` => `1`
    - `% 2` 는 어떻게 쓸 수 있을까요?
        - `0 % 2` => `0`
        - `1 % 2` => `1`
        - `2 % 2` => `0`
        - `3 % 2` => `1`
        - `4 % 2` => `0`
        - `5 % 2` => `1`
        - `6 % 2` => `0`
        - `7 % 2` => `1`
        - `8 % 2` => `0`
        - `9 % 2` => `1`
- 값의 부호를 반대로 바꿔보기(음수 -> 양수, 양수 -> 음수)


## 1씩 더하고, 1씩 빼기 - 증감연산자
- `++` 증가 연산자
    ```javascript
    var number = 0;
    console.log(number); // 0 출력

    number++;
    console.log(number); // 1 출력

    console.log(number++); // 1 출력 후 number의 값은 1이 증가된 1
    console.log(number); // 2 출력

    console.log(++number); // 값이 먼저 증가되어 3 출력, number의 값도 3
    ```
- `--` 감소 연산자
    ```javascript
    var number = 5;
    console.log(number); // 5 출력

    number--;
    console.log(number); // 4 출력

    console.log(number--); // 4 출력 후 number의 값은 1이 감소된 3
    console.log(number); // 3 출력

    console.log(--number); // 값이 먼저 감소되어 2 출력, number의 값도 2
    ```
- 먼저 증감하는지, 값을 전달하고 증감하는지 순서는 있지만 아래를 줄여쓴 것과 같아요
    ```javascript
    var number = 0;

    number = number + 1; // number의 값에 1을 더한 후 다시 대입

    number = number - 1; // number의 값을 1을 뺀 후 다시 대입
    ```
## 줄여서 쓰기 - 산술 대입 연산자
- `+=` 덧셈 산술 연산자
    - 바로 위의 `number = number + 1`을 줄여서 쓸 수 있는 방법이예요.
    - `number += 1` 은 `number = number + 1`과 같은 구문입니다.
    ```javascript
    var number1 = 10;
    var number2 = 20;

    number1 += 1; // number1 변수에 1 더하기
    // number1 = number1 + 1; 과 같아요

    number2 += number1; // number2 변수에 number1 변수 더하기
    // number2 = number2 + number1; 과 같아요
    ```
- `-=` 뺄셈 산술 연산자
- `*=` 곱하기 산술 연산자
- `/=` 나누기 산술 연산자

## 값을 비교해 봅시다 - 관계(비교) 연산자
- `==` => 값이 같은 지 비교하여 true/false의 값으로 표현
    - `1 == 1` => `true`
    - `1 == 2` => `false`
- `!=` => 값이 다른 지 비교하여 true/false의 값으로 표현 (`==`와 반대)
    - `1 != 1` => `false`
    - `1 != 2` => `true`
- `===` => 값과 타입이 같은 지 비교하여 true/false의 값으로 표현
    - `1 === 1` => `true`
    - `1 === 2` => `false`
    - 응? `==`와 다른게 뭐죠..?
        - `1 == '1'` => true
        - `1 === '1'` => false
- `!==` => 값과 타입이 **다른** 지 비교하여 true/false의 값으로 표현
    - `1 !== 1` => `false`
    - `1 !== '1'` => `true`
    - `1 !== 2` => `true`
- `<` => 왼쪽의 값이 **작으면** true, 아니면 false
    - `1 < 2` => `true`
    - `1 < 1` => `false`
    - `5 < 1` => `false`
- `>` => 왼쪽의 값이 **크면** true, 아니면 false
    - `2 > 1` => `true`
    - `1 > 1` => `false`
    - `1 > 5` => `false`
- `<=` => 왼쪽의 값이 **작거나 같으면** true, 아니면 false
    - `1 <= 2` => `true`
    - `1 <= 1` => `true`
    - `5 <= 1` => `false`
- `>=` => 왼쪽의 값이 **크거나 같으면** true, 아니면 false
    - `2 >= 1` => `true`
    - `1 >= 1` => `true`
    - `1 >= 5` => `false`

## 참인가 거짓인가 - 논리 연산자
- `&&` AND 연산자 (논리 곱)
    - true를 1, false를 0 이라고 두면, `&&` 연산자를 논리 값을 곱하는 것과 같습니다.
    - `1 * 1` => `1` 에서 `1`을 `true`로, `*`을 `&&`로 바꾸면?
        - `true && true` => `true`
    - `true && false` => `false`
    - `false && true` => `false`
    - `false && false` => `false`
    - `&&` 연산자는 양 쪽의 값이 모두 `true`일 때만 `true`이고 나머지는 `false`가 돼요.
- `||` OR 연산자 (논리 합)
    - AND와 마찬가지로 true를 1, false를 0으로 두면, `||` 연산자는 논리 값을 더하는 것과 같아요.
    - `1 + 0` => `1` 에서 `1`을 `true`로, `+`를 `||`로 바꾸면?
        - `true || false` => `true`
    - `true && false` => `true`
    - `false && true` => `true`
    - `false && false` => `false`
    - `||` 연산자는 양 쪽의 값 중에 하나라도 `true`라면 `true`예요, 모든 값이 `false`일 때만 `false`입니다.
- `!` NOT 연산자 (논리 반전)
    - `!` 연산자는 `true`를 `false`로, `false`를 `true`로 반전시키는 연산자입니다.
    - `!true` => `false`
    - `!false` => `true`
!

## 이 값들은 true나 false가 될 수 있어요.
```
0, '', NaN, null, undefined
0아닌 숫자, 빈 문자열을 제외한 문자열, 객체
```
## 삼항 연산자
```
? :
```
## 01011101 비트의 세계로 - 비트 연산자
```
&
|
^
~
<<
>>
>>>
```
## 그 외의 연산자
```
typeof
void
delete
new
in
instanceof
typeof
```
## 연산자의 우선순위
## 얘네도 연산자예요
- 객체의 속성에 접근하기 위한 `.` 연산자
- 배열의 요소에 접근하기 위한 `[]` 연산자
- 파라미터나 변수를 구분하기 위한 `,` 연산자
```javascript
console.log('Hello'); // . 은 연산자에요
```

