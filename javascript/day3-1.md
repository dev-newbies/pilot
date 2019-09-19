# 함수를 써봅시다.
![함수 상자](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3b/Function_machine2.svg/440px-Function_machine2.svg.png)
엑셀의 함수를 생각해 봅시다. 시트에 아래와 같이 값이 채워져 있을 때 `B1` 셀에 A1~A5 셀의 합계를 구하려면 어떻게 해야할까요?

| \ | A | B |
-- | -- | --
 1 | 10 | `A1:A5`의 합계?
 2 | 20 
 3 | 30 
 4 | 40 
 5 | 100 

 ```
 =SUM(A1:A5)
 ```
 위와 같이 B1셀에 입력하면 의도한 대로 A1~A5 범위에 있는 값의 합계가 B1 셀에 표시됩니다. 여기서의 `SUM` 함수의 입력은 합계를 구할 셀의 범위(`A1:A5`)이고, 그 입력에 대한 결과인 `200`을 내뱉습니다.  
   
이처럼 함수는 무엇인가를 받고 무엇인가 처리하거나 계산을 한 후 무엇인가를 돌려줍니다. 프로그래밍 언어에서의 함수는 경우에 따라서 입력이 없을 수도 있고, 출력 또한 없을 수도 있고, 둘 다 없을 수도 있습니다.  
우선은 함수는 처리하거나 계산을 하는 하나의 단위라고 기억하고 다음으로 가보겠습니다.

## 1. 아무 것도 받지 않고 아무 것도 하지 않고 아무 것도 뱉지 않는 함수
함수의 가장 간단한 형태로 입력, 출력, 처리가 없는 함수를 만들어 보겠습니다. 가장 기본적인 형태의 함수입니다.
```javascript
function doNothing() {

}
```
그리고 이렇게 정의한 함수를 실행하기 위해서는 `doNothing()`과 같이 함수 이름에 괄호를 붙여주면 됩니다. 실행하지 않으면 함수는 그저 있을 뿐입니다.
  
`doNothing` 함수를 다시 살펴보겠습니다.
```
이건 함수!
   |     함수의 이름 
   |         |     비어있지만 여기가 입력을 받기 위한 부분
________ _________ __
function doNothing() {
  // 함수가 무엇인가 '처리' 할 때 그 '처리'를 위한 코드를 
  // 중괄호 사이에 작성합니다.
  // 함수의 몸통, 바디(Body), 구현부(Implementation) 이라고 합니다.
  // 열고 닫는 중괄호 사이를 블록(Block)이라고 합니다.
}
-
함수가 끝났음을 표시하는 중괄호 닫아주기
```

## 2. 아무 것도 받지 않지만 값을 뱉는  함수
이제 용어를 조금 다듬어서 함수가 받는 것을 **파라미터(Parameter)** 라고 하고, 함수가 뱉는 것을 **반환(Return)** 이라고 하겠습니다. 이번에 만들어 볼 함수는 파라미터는 없지만 항상 여러분의 이름을 반환하는 `getMyName` 입니다. 2일차에 스쳐지나갔던 네이밍(Naming) 기억하시나요? 함수는 보통 동사형의 단어를 사용하여 이름을 지어줍니다.
```javascript
function getMyName() {
    return 'Newt';
}
```
**return** 이라는 키워드가 등장했습니다. '반환한다'의 의미를 갖는 `return`은 값을 반환하고 함수를 종료합니다. 함수를 종료한다는 것은 함수 구현부에 작성한 소스코드를 순서대로 실행해 나가다가 `return`을 만나면 더 이상 진행하지 않고 처리를 마친다는 의미입니다.  
그래서 꼭 함수가 값을 반환하기 위해서만 `return`을 사용하는 것이 아니라 함수를 종료하기 위해서도 `return`을 사용하기도 합니다.
```javascript
function getMyName() {
    return 'Newt'; // 'Newt'라는 문자열을 반환하기 위한 return
}

function doNothing() {
    return; // 함수를 끝내기 위한 return
}
```

함수를 끝내기 위해서 `return`을 쓸 때는 반환할 값을 써주지 않고 `return`만 써줍니다.

값을 반환하는 `return`을 썼을 때 반환된 값은 어떻게 될까요? 그냥 반환 값이 있는 함수를 그냥 호출하기만 했을 때는 반환 값은 쓰이지 않습니다.
```javascript
getMyName(); // 위에서 작성한 getMyName 함수를 호출하기
```
작성한 파일을 `node day3-1.js`와 같이 실행하면 터미널에서는 아무것도 나타나지 않습니다.
```javascript
// 반환된 값을 로그로 출력하기
console.log(getMyName());

// 반환될 값을 변수에 담았다가 로그로 출력하기
var myName = getMyName();
console.log(myName);
```
위의 코드에서 보는 것과 같이 함수의 반환 값은 다른 함수(`console.log` 함수)의 파라미터로 전달하거나, 변수(`myName`)에 담을 수 있습니다.

## 3. 파라미터도 있고, 반환도 하는 함수
먼저 그런 함수를 한번 정의해 봅시다.
```
             파라미터의 이름
               |
              ____
function echo(name) {
    return name;
}
```
지금까지 비워져있던 함수 이름 오른 쪽의 괄호 안에 `name`이 생겼습니다. 저 괄호 안에 위치하게 되는 것들이 파라미터입니다. 금방 작성한 `echo` 함수는 전달받은 파라미터를 그대로 반환하고 있습니다. 'A'를 전달하면 'A'를 그대로 반환하는 함수입니다. 어떻게 사용하는지 한 번 호출해 볼까요?
```javascript
// echo를 호출하고 반환 값을 echoed에 담기
var echoed = echo('Hello Parameter?');

// echoed 변수에 담긴 값을 출력하기
console.log(echoed);
```
힘수를 정의할 때와 마찬가지로 함수를 호출할 때 역시 파라미터를 전달하기 위해서 괄호 사이에 전달할 파라미터를 써줍니다.
```
'Hello Parameter' ===> name 파라미터에 담겨서 함수가 호출됨
```
이렇게 파라미터로 전달된 값을 전달인자(Argument)라고 합니다. 파라미터는 `name`이고, `name`에 담긴 `'Hello Parameter'`라는 값이 전달인자입니다.  
  
여러 개의 파라미터를 정의할 수도 있습니다. 이번에는 두 개의 숫자를 파라미터로 전달받아, 그 둘을 더한 값을 반환하는 함수를 정의해 보겠습니다.
```javascript
function sum(firstValue, secondValue) {
    var result = firstValue + secondValue;
    return result;
}

/* 아래처럼 쓸 수도 있어요.
function sum(firstValue, secondValue) {
    return firstValue + secondValue;
}
*/
```
파라미터가 2개 이상일 때는 각각의 파라미터를 콤마(`,`) 기호로 구분해 주면 됩니다. 눈치채신 분도 있겠지만 사실 파라미터는 변수와 마찬가지로 값을 담고 있는 역할을 합니다. `sum` 함수를 실행해 볼까요?
```javascript
console.log(sum(1, 2));
console.log(sum('Hello', ' World'));
console.log(sum(3.14, 6.28));
console.log(sum(sum(1, 2), 2));
console.log(sum(sum(1, 3), sum(7, 9)));
console.log(sum(sum(sum(1,1), 1), 'ㅎㅎ'));
```
## 4. 로그 출력과 반환 구분하기
- TODO

## 5. 나중에 더 살펴볼 것들
- 붕어빵 틀이 클래스고, 붕어빵을 객체에 비유한다면 함수는 붕어빵 틀이 될 수 있습니다.
- 꼬리에 꼬리를 무는 재귀 함수
- 객체의 속성에 값이 아닌 함수를 넣어보기