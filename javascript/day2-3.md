# 자바스크립트 시작하기
## 1. 소스코드를 작성하기 전에
- 자바스크립트에서의 대문자와 소문자는 서로 다른 것으로 판단합니다.
    - kakaopay와 **K**akao**P**ay는 사람이 보기엔 비슷하지만 자바스크립트에서는 전혀 다른 것으로 판단합니다.
- 소스코드의 가장 작은 단위 단위를 토큰(Token)이라고 합니다.
    - `100 + 200` 이라고 입력했을 때 `100`, `+`, `200`이 각각 토큰입니다.
- 공백 문자는 스페이스를 포함하여, 탭 문자, 줄바꿈 문자를 지칭하며, 여러 개의 공백 문자를 써도 무방합니다.
    - `100 + 200` 이라고 써도 되고, `100               +   200` 이라고 써도 되며,
        ```
        100
        +           200
        ```
        처럼 써도 됩니다. 적당한 공백 문자를 이용해 읽기 쉬운 소스코드를 작성할 수 있습니다.
- 연산이 수행되는 최소한의 단위를 문장이라고 하며, 문장 끝에는 자연어에서의 마침표 역할을 하는 세미콜론(`;`)을 써줍니다.
    - `100;`
    - `console.log('Hello World!');`
    - 세미콜론을 생략해도 자바스크립트는 동작할 수 있으며, 코딩 스타일에 따라서 항상 표시해주거나, 생략할 수 있습니다.
- 주석(Comment): 주석이란 소스코드를 설명하기 위해 사용하며, 소스코드의 실행에는 영향을 미치지 않습니다. 적절한 주석은 소스코드를 파악하는데 도움을 줍니다.
    - 한 줄 주석(`//`)
        ```javascript
        // 빈 줄에 //를 쓰고 주석을 추가하거나
        console.log('Hello World!'); // 문장 뒤에 쓸 수도 있습니다.
        ```
    - 여러줄 주석(`/* ... */`)
        ```javascript
        /* //를 이용한 한 줄 주석은 한 줄의 주석을 작성할 수 있지만,
        여러줄 주석은 여러줄 주석의 끝을 표시하기 전까지는
        줄을 바꿔 주석을 계속 작성할 수 있습니다. */
        ```
  
## 2. 변수(Variable)
컴퓨터에는 CPU, 주기억장치(RAM), 보조기억장치(HDD, SSD, USB 드라이브 등)가 있습니다.  
우리가 자바스크립트 파일(`.js`)을 작성하면 이는 보조기억장치에 저장이 되고, 실행하면 컴퓨터가 이해할 수 있는 형태로 번역되어 주기억장치(메모리)로 불러들입니다(Load).
또한 메모리에는 프로그램에서 다루는 데이터를 저장하는 영역이기도 합니다.  
**변수**는 데이터를 담기 위한 메모리 상자로 생각할 수 있으며, 엑셀이나 구글 시트의 셀 한칸과 같이 값을 담는 역할을 합니다.

### 변수 선언하기
변수는 이름을 가지며 '특정 이름을 가진 변수를 사용하겠다'고 표현하는 것을 보고 '선언'한다고 합니다. 변수 선언을 위해 `var 변수이름` 과 같이 씁니다.
```
var sum; // 합계
```
위의 문장이 실행되면 sum 이라는 변수가 만들어져 데이터를 담을 수 있는 준비가 되었습니다. 데이터를 담을 때는 대입 연산자(`=`)를 이용하여 아래와 같은 형식으로 사용합니다.
```
sum = 1; // sum 변수에 1이라는 값을 담기
```
변수의 변(變)은 변한다는 의미이며, 스프레드 시트 셀의 값을 바꿀 수 있는 것과 마찬가지로 대입 연산자(`=`)를 이용해 다시 값을 대입할 수 있습니다.
변수에 데이터를 대입하는 것을 다른 말로 할당(Assign)한다고 합니다.
```
sum = 'hello'; // 1이라는 값이 들어있던 변수에 'hello'라는 값을 할당하기
```