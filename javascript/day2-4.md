# 자바스크립트의 데이터 타입
데이터 타입이란 프로그래밍 언어에서 데이터의 종류를 구분하는 것을 의미하며, 타입별로 구분되는 특징을 갖습니다.

## 원시(Primitive) 타입
원시 타입은 언어가 가지는 기본적인 데이터 타입이며, 아래와 같은 Primitive 타입들이 있습니다.
- 논리값(Boolean)
    - 참: `true`
    - 거짓: `false`
- 숫자(Number) - 64비트의 부동소수점
    - 정수
        - 10진수(Decimal Number): `12345` - 0~9로 표현
        - 16진수(Hexadecimal Number): `0xacebabe` - 0~9, a~f로 표현, F는 10진수로 16
        - 8진수(Octal Number): `0o12345670` - 0~7로 표현(ES6부터 사용 가능)
        - 2진수(Binary Number): `0b0110010` - 0,1로 표현(ES6부터 사용 가능)
    - 소수점(부동소수점 Floating Point)
        - `3.1415`
        - IEEE 754 표기법: `6.293e2` => `6.293 x 10^2` => `629.3`
    - 특수한 값
        - `Infinity`: 양의 무한대
        - `NaN`: 숫자가 아닌 것(Not a Number) - `0 / 0`, `Infinity / Infinity`
        - `Number.POSITIVE_INFINITY`: 양의 무한대
        - `Number.NEGATIVE_INFINITY`: 음의 무한대
        - 그 외 Number에 정의된 상수들이 있습니다.
- `undefined`: 정의되지 않은 상태를 의미
- `null`: 비어 있는 상태를 의미
- 문자열(String): 문자열은 일반적인 텍스트를 의미하며, 문자들의 나열입니다. 개발자인지 아닌지 궁금할 때 String이 뭐예요? 라고 물어보면 됩니다.
    - 문자열은 `'문자열'`과 같이 작은 따옴표로 감싸거나, `"문자열"`처럼 큰 따옴표로 감싸서 표현합니다.
    - 문자열은 길이라는 속성을 갖습니다. `'string'`의 길이는 6이며, `'string'.length`로 확인할 수 있습니다.
    - 길이가 0인 비어있는 문자열은 `''` 또는 `""`로 표현합니다.
    - ES6에서는 템플릿 리터럴이라는 문자열 표현방법이 추가되었습니다.
    - 이스케이프: 작은 따옴표(`''`)안의 문자열에서 작은 따옴표를 표시하려면 어떻게 해야할까요? 이런 경우를 위해 이스케이프 문자를 활용합니다.    

| 이스케이프 문자 | 설명 |
| --- | --- |
| \' | 문자열안에서 작은 따옴표 표시 |
| \" | 문자열 안에서 큰 따옴표 표시 |
| \t | 탭(Tab) 문자 |
| \n | 줄바꿈 문자 |
| \\ | 역슬래시(`\`) 문자 - 이스케이프 문자 앞에 `\`를 쓰므로 `\` 자체를 문자로 표현할 때 |

## 객체 타입
### 객체
원시 타입을 제외한 모든 타입은 모두 객체(Object) 타입이라고 합니다. 간단하게 설명하면 객체는 데이터의 덩어리로 생각할 수 있습니다.  
사람을 표현하려면 이름, 생년월일, 생물학적 성별 등 여러 정보들로 구성해야 합니다. 이를 원시 타입으로만 표현하기에는 한계가 있습니다.  
객체를 데이터의 덩어리라고 했는데, 사람이라는 데이터는 위에서 말한 여러 정보들의 덩어리로 구성할 수 있으며, 자바스크립트에서 객체는 아래와 같이 표현할 수 있습니다.
```javascript
{
  name: 'newt',
  birth: '1900-01-01',
  sex: 'male',
  isAdult: true
}
```
중괄호 안에 속성(Property)의 이름, 콜론(`:`), 그리고 해당 속성의 값을 쓰고, 속성이 여러개라면 콜론(`,`)으로 구분하여 줍니다. 원시 타입과 마찬가지로 변수에 대입할 수 있습니다.
```javascript
var newt = {
  name: 'newt',
  birth: '1900-01-01',
  sex: 'male',
  isAdult: true
}
```
또한 객체 안에는 중첩해서 객체를 넣을 수도 있고, 변수의 값을 넣어줄 수도 있습니다.
```javascript
var name = 'newt';

var newt = {
  name: name, // 위에서 선언한 name 변수를 name 속성에 대입
  birth: '1900-01-01',
  sex: 'male',
  isAdult: true,
  school: {
    elementary: '페이 초등학교',
    middle: '페이 중학교',
    high: '페이 고등학교'
  }
}
```
#### 생성한 객체의 속성에 접근하기
객체의 속성에 접근하기 위해서는 `.` 연산자 또는 `[]` 연산자를 사용할 수 있습니다. `[]` 연산자를 사용할 때는 `['속성이름']`의 형식으로 사용하며, 속성이름은 문자열로 전달합니다.
```javascript
console.log(newt); // newt 객체 전체를 콘솔로 출력

console.log(newt.name); // '.' 연산자로 newt 객체의 name 속성을 콘솔로 출력

console.log(newt['name']); // '[]' 연산자로 newt 객체의 name 속성을 콘솔로 출력

var propertyName = 'birth'; // 'birth'를 값으로 갖는 propertyName 변수를 선언
console.log(newt[propertyName]); // 변수에 담긴 문자열을 속성의 이름으로 사용
console.log(newt.propertyName); // 이건 안됩니다.
```

#### 선언한 후에 객체에 속성 추가하기
```javascript
console.log(newt.hairColor); // 정의되지 않았으므로 undefined가 출력됩니다.

newt.hairColor = 'dark brown'; // newt 객체에 hairColor라는 속성을 추가하고 'dark brown'을 할당
// 또는 newt['hairColor'] = 'dark brown';

console.log(newt.hairColor); // 할당했던 'dark brown'을 출력
```

#### 속성 지우기
delete 키워드를 이용해 객체에 정의된 속성을 지울 수 있습니다.
````javascript
console.log(newt.hairColor);

delete newt.hairColor; // delete 키워드로 hairColor 속성을 제거

console.log(newt.hairColor); // undefined 출력
```
### 배열(Array)
객체가 데이터의 덩어리였다면, 배열은 데이터의 목록입니다. 실세계에서의 할 일(To-Do) 의 목록, 연락처 목록과 같은 것들을 배열로 표현할 수 있습니다.  
```
var todoList = ['아침먹기', '점심먹기', '저녁먹기'];
var values = ['hello', 3.14, newt, true, false];

var nestedArray = ['this', 'is', 'array', values, [], [1,2,3, [4, 5, [6]]]]
```
객체와 마찬가지로 변수에 배열을 할당할 수 있고, 여러 타입을 배열에 담을 수 있으며, 객체와 마찬가지로 배열 안에 배열을 충첩해서 넣을 수도 있습니다. 배열을 담는 변수나 속성의 이름은 일반적으로 복수형으로 표현하거나, List를 붙입니다(`studentList`).  
  
배열 내에 담긴 데이터는 배열의 요소(Element)라고 합니다. `[]`만 쓰고 요소를 쓰지 않으면 비어있는 배열이 됩니다.  
배열은 문자열과 마찬가지로 `length`라는 속성을 갖습니다. `length` 속성을 통해 배열에 담긴 요소의 수를 알 수 있습니다.
```
var array = [];
console.log(array.length); // 비어있으므로 0이 출력됩니다.

var names = ['newt', 'newton', 'news'];
console.log(names.length); // 3개의 요소가 담겨 있으므로 3이 출력됩니다.
```

### 배열의 n번 째 요소에 접근하기
배열에는 요소가 순서대로 담겨져 있습니다. 그래서 배열의 요소에 담긴 값을 가져올 때 몇 번째에 있는 요소인지를 전달하여 요소에 접근할 수 있습니다.  
이 때 객체와 유사하게 `[]` 연산자를 사용하며, `[]` 안에는 몇 번째 요소인지 요소의 인덱스(index)를 전달합니다.  
배열의 인덱스는 0부터 시작합니다. 즉 첫 번째 요소의 인덱스는 0입니다. 그리고 배열의 마지막 요소의 인덱스는 항상 배열의 길이(`length` 속성) - 1입니다.
```javascript
var values = [2,4,6,8,10]; // 다섯 개의 요소가 담긴 배열을 선언하여 values 변수에 대입

console.log(values); // 배열 전체를 출력하기
console.log(values[0]); // 배열의 첫 번째 요소(2)를 출력
console.log(values[values.length - 1]); // 배열의 마지막 요소(10)을 출력

// 객체의 속성에 접근할 때와 마찬가지로 인덱스를 변수로 전달할 수도 있습니다.
var i = 3;
console.log(values[i]); // 네 번째(인덱스는 3) 요소를 출력

// 요소의 값을 변경하기
console.log(values[0]); // 선언할 때 넣어준 2 출력
values[0] = 'Hello Array!'; // 'Hello Array!' 문자열로 값을 바꿔주기
console.log(values[0]); // 바뀐 값으로 출력
```

#### 배열의 마지막에 요소 추가하기
우선 당황스럽지만 배열도 객체입니다. `[]` 연산자로 인덱스를 전달하긴 했지만, 객체에서 속성에 접근하는 두 가지 방법 중 하나로 동일하게 `[]`를 사용하는 방법이 있었죠?  
데이터로써의 객체만 다뤘지만 객체는 다양한 형태로 활용될 수 있습니다. 아직 함수를 배우지 않았지만 간단한 함수를 객체에 추가해 보도록 하겠습니다.
```javascript
var game = {
  start: function() { // start라는 속성에 함수를 할당해 줍니다.
    console.log('게임을 시작합니다.');
  }
};

game.start; // start에는 함수 자체가 담겨져 있으므로 실행이 되지는 않습니다.
game.start(); // 함수를 실행할 때는 여닫는 괄호를 붙여줍니다.
// 함수 안의 내용이 실행됩니다.
```
위와 같이 객체 안에 있는 함수를 메서드(method)라고 합니다. 지금까지 출력을 위해 써왔던 `console`도 객체이고 `.` 연산자를 통해 `console` 객체 안의 `log` 메서드를 사용해 왔습니다.
자바스크립트에는 다양한 내장 객체가 미리 만들어져 있어, 잘 활용한다면 보다 수월하게 프로그래밍을 할 수 있습니다. 배열 객체 역시 유용한 기능을 하는 많은 메서드들이 있고, 그 중에 `push` 메서드를 사용하면 배열에 요소를 추가할 수 있습니다.
```javascript
var techfins = ['카카오페이', '네이버페이', '토스'];
techfins.push('신생 테크핀 기업');

console.log(techfins); // push 메서드로 추가한 항목이 함께 표시됩니다.
```
`push` 메서드를 활용해서 추가할 수도 있고, 배열의 마지막 인덱스 다음의 인덱스를 지정하여 요소를 추가할 수도 있습니다.
```javascript
techfins[4] = '스타트업';
// 또는 techfins[techfins.length] = '스타트업'
```
