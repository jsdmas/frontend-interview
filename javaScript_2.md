# 목차

2번째 자바스크립트 정리 파일로, 클로저부터 정리합니다.

<details>
<summary>접기 / 펼치기</summary>

- [클로저](#클로저)
    - <span style="color: red">클로저에 대해 아시나요?</span>
    - <span style="color: red">클로저를 사용하면 뭐가 좋죠?</span>
    - <span style="color: red">클로저를 어떻게 생성하나요?</span>
- [클래스](#클래스)
    - 자바스크립트에서 클래스가 생기기 전에는 어떤 방식으로 객체지향 패턴을 구현했나요?
    - 그럼 생성자 함수와 클래스는 어떤 차이가 있나요?
    - 클래스 정의
    - 클래스의 상속
- [스프레드 문법](#스프레드-문법)
    - spread 문법이 뭔가요?
    - 어떤 상황에서 사용할 수 있죠?
- [구조 분해 할당](#구조-분해-할당)
    - 구조 분해 할당이 뭔가요?
    - 구조 분해 할당은 크게 어떤 종류가 있나요?
- [브라우저 렌더링 과정](#브라우저-랜더링-과정)
    - <span style="color: red">브라우저의 렌더링 과정에 대해 설명해보세요</span>
    - <span style="color: red">브라우저의 렌더링 과정에 자바스크립트는 어떻게 동작하나요?</span>
    - `script`태그를 `body`태그 및에 둬야하는 이유가 있을까요?
- DOM
    - DOM이 뭔가요?
    - DOM을 구성하는 건 뭐가 있을까요?
- 이벤트
    - 마우스 이벤트 타입에는 뭐가 있나요? click 말고 클릭을 대체할 수 있는 이벤트가 있나요?
    - 그 외에 알고있는 대표적인 이벤트가 있나요?
    - 이벤트 핸들러를 등록하는 방식에는 어떤 것들이 있나요?
    - 이벤트 전파(propagation)에 대해서 알고 있나요?
    - <span style="color: red">이벤트 위임(delegation)에 대해서 알고있나요?</span>
    - e.preventDefault 에 대해 알고 있나요?
    - e.stopPropagation
- 타이머
    - 호출 스케쥴링이 무엇인가요?
    - 타이머 함수에는 어떤 것들이 있나요?
    - 이벤트가 과도하게 호출되어 성능에 문제를 일으킬 경우에 할 수 있는 어떤 일을 통해 해결 할 수 있나요?
    - 디바운스에 대해서 알고 있나요?
    - 쓰로틀에 대해서 알고 있나요?
- 비동기 프로그래밍
    - <span style="color: red">동기와 비동기의 차이점에 대해서 설명해줄 수 있나요?</span>
    - <span style="color: red">이벤트 루프와 태스크 큐에 대해서 알고 있나요?</span>
    - <span style="color: red">마이크로태스크 큐에 대해서 알고 있나요?</span>
    - <span style="color: red">태스크 큐와 마이크로태스크 큐 중 어떤 것이 먼저 실행되나요?</span>
- Ajax
    - Ajax가 뭔가요 어떤 것을 담당하고 있죠?
    - Ajax를 사용하면 기존 방식과 어떤 차이가 있을까요?
    - JSON이 뭔가요?
    - JSON이 제공하는 정적 프로토타입 메서드에 대해 몇가지 말해볼 수 있나요?
    - Ajax로 HTTP 요청을 보내기 위해서는 어떤 방법을 사용할 수 있나요?
    - <span style="color: red">XMLHttpRequest와 fetch 메서드의 차이는 무엇이라고 생각하시나요?</span>
- REST API
    - REST API가 뭔가요?
    - REST API의 구성은 어떤 것이 있나요?
    - REST API를 설계하는데 중요한 것이 있을까요?
    - HTTP 요청 메서드에 대해서 아는대로 얘기해보세요
    - <span style="color: red">HTTP 상태 코드를 아는대로 말해주세요</span>
- Promise
    - <span style="color: red">콜백이란 뭐라고 생각하나요?</span>
    - <span style="color: red">프로미스가 뭔가요?</span>
    - 프로미스 생성 방법
    - <span style="color: red">프로미스의 상태를 나타내는 것은 어떤 것들이 있나요?</span>
    - <span style="color: red">프로미스 빌트인 객체가 제공하는 정적 메서드에 대해 알고 있나요?</span>
- 제네레이터와 async await
    - 제네레이터란 뭔가요? 일반 함수와는 어떤 차이가 있죠?
    - 제네레이터의 구조
    - <span style="color: red">async/await 가 뭔가요? 기존의 Promise와는 어떤 차이가 있죠?</span>
    - <span style="color: red">Promise와 async/await의 차이점 한 줄 요약</span>
- 에러
    - 에러처리를 왜 해야 하나요?
    - 자바스크립트에서 에러를 처리하는 방법에는 뭐가 있을까요?
- 모듈
    - 모듈이 뭔가요?

</details>


# 클로저

## 클로저에 대해서 아시나요?
내부함수가 이미 생명주기를 마감한 외부함수(outer)의 변수를 참조할 수 있다면 그 함수를 클로저라고 합니다.  
클로저는 함수와 그 함수가 선언된 렉시컬 환경과의 조합입니다.  
간단히 말해, 클로저는 함수 내부에서 선언된 변수를 외부에서 접근할 수 없게 되는데, 이때 해당 함수와 변수들의 조합을 클로저라고 부릅니다.   
즉, 클로저를 통해 함수 내부에서 선언한 변수를 계속해서 참조할 수 있게 됩니다.  
```js
function makeCounter(){
    let count = 0;
    function counter(){
        count++;
        console.log(count);
    }
    return counter;
}
const counter1 = makeCounter();
counter1(); // 1
counter1(); // 2
const counter2 = makeCounter();
counter2(); // 1
counter2(); // 2
//  outer함수의 실행 컨텍스트는 사라지지만 렉시컬 환경까지는 사라지지 않는다.
```
  
- 상위 스코프의 식별자를 참조하지 않는 경우
```js
function foo(){
    const x = 1;
    const y = 2;
    function bar(){
        const z = 3;
        console.log(z);
    }
    return bar;
}
const bar = foo();
bar();
```
위 예제의 중첩 함수 bar는 외부 함수 foo보다 더 오래 유지되지만 상위 스코프의 어떤 식별자(x,y)도 참조하지 않습니다.  
이처럼 상위 스코프의 어떤 식별자도 참조하지 않는 경우 대부분의 모던 브라우저는 최적화를 통해 상위 스코프를 기억하지 않습니다.  
참조하지도 않는 식별자를 기억하는 것은 메모리 낭비이기 때문입니다.   
`따라서 bar 함수는 클로저라고 할 수 없습니다.`  
> 참조하는 식별자를 실행 컨텍스트가 종료되어도 렉시컬 환경을 통해 참조하고, 값을 변경할 수 있는 것이 클로저 입니다.


## 클로저를 사용하면 뭐가 좋죠?
- **클로저는 상태(state)를 안전하게 변경하고 유지하기 위해 사용합니다.**   
  - 다시 말해, 상태가 의도치 않게 변경되지 않도록 상태를 안전하게 은닉(information hiding)하고 특정 함수에게만 상태변경을 허용하기 위해 사용합니다.  


## 클로저를 어떻게 생성하나요?
클로저를 생성하는 가장 일반적인 방법은 함수 내부에서 새로운 함수를 정의하고, 그 함수를 반환하는 것입니다. 반환된 함수는 자신이 생성된 렉시컬 스코프에서 선언된 변수를 계속해서 참조할 수 있습니다.
```js
function makeAdder(x){
    return function(y){
        // y를 가지고있고 상위함수인 makeAdder 의 x 에 접근가능

        return x + y;
    };
}
// makeAdder 함수가 실행되어 반환된 함수를 add5 변수에 할당합니다.
const add5 = makeAdder(5);
// add5 함수가 생성된 이후에도 상위함수인 makeAdder 의 x 에 접근가능 
console.log(add5(3)); // 8
consoel.log(add5(7)); // 12
```
## 함수형 프로그래밍에서의 클로저 사용하기
```js
function closure(){
    let num = 10;

    function plusNum(){
        num +=1;
    }
    function printNum(){
        console.log(num);
    }
    function setNum(val){
        num = val;
    }
    // 함수를 객체 형식으로 리턴하는 이유는 새로 생성한 변수를 (.) 연산자를 통해 접근하기 위해서 입니다.
    return {num, plusNum, printNum, setNum};
}

const newNum = closure();

// closure 함수가 리턴하는 객체 형식의 프로퍼티와 메서드가 들어있다.
console.log(newNum); // {num:10, plusNum : f, printNum : f, setNum : f}

newNum.num = 20
console.log(newNum); // {num:20, plusNum : f, printNum : f, setNum : f}
newNum.printNum(); // 10 객체형식으로 리턴되는 newNum 특성상 newNum의 프로퍼티인 num의 값이 재할당됩니다. 
newNum.setNum(100); // 지역 변수 num을 변경하기 위해서는 새로운 메서드를 정의하여 값을 전달함으로서 부수효과를 줄여야합니다.
newNum.printNum(); // 100
```

# 클래스

## 자바스크립트에서 클래스가 생기기 전에는 어떤 방식으로 객체지향 패턴을 구현했나요?
자바스크립트는 프로토타입 기반 객체지향 언어로서, 클래스가 필요 없는 객체지향 프로그래밍 언어입니다.   
생성자 함수와 프로토타입을 통해 객체지향 언어의 상속을 구현할 수 있었습니다.
```js
// ES5 생성자 함수
function Person(name){
    this.name = name;
}
// 프로토타입 메서드
Person.prototype.sayHi = function() {
    console.log(`Hello! My name is ${this.name}`)
};

// 인스턴스 생성
var user = new Person("JinHo");
user.sayHi(); // Hello! My name is JinHo
```
ES6에서 도입된 `클래스`는 기존 프로토타입 기반 객체지향 프로그래밍보다 자바나 C#과 같은 클래스 기반 객체지향 프로그래밍에 익숙한 프로그래머가 더욱 빠르게 학습할 수 있도록 클래스 기반 객체지향 프로그래밍 언어와 매우 흡사한 새로운 객체 생성 메커니즘을 제시합니다.


## 그럼 생성자 함수와 클래스는 어떤 차이가 있나요?
1. 클래스를 new 연산자 없이 호출하면 에러가 발생합니다. 하지만, 생성자 함수는 일반 함수로 호출됩니다.
2. 클래스는 상속을 지원하는 extends와 super 키워드를 제공합니다. 생성자 함수는 해당 키워드를 제공하지 않습니다.
3. 클래스는 호이스팅이 발생하지 않는 것처럼 동작합니다. 하지만 함수 선언문으로 작성된 클래스는 함수 호이스팅이, 함수 표현식으로 정의한 생성자 함수는 변수 호이스팅이 발생합니다.
4. 클래스 내의 모든 코드에는 암묵적으로 strict mode가 저장되어 실행되며 strict mode를 해제할 수 없습니다. 하지만 생성자 함수는 암묵적으로 strict mode가 지정되지 않습니다.

## 클래스의 정의
**정의**
```js
class User{}
// 함수 선언문으로 작성시, 함수 호이스팅이
// 함수 표현식으로 작성시, 변수 호이스팅이 발생
```
**익명 함수와 기명 함수로 클래스 정의**
```js
// 익명 클래스 표현식
const Person = class {};
// 기명 클래스 표현식
const Person = class MyClass {};
```
**클래스 몸체에 정의할 수 있는 메서드**
1. constructor (생성자)
2. 프로토타입 메서드
3. 정적 메서드
```js
class User {
    // 생성자
    constructor(name){
        // 인스턴스 생성 및 초기화
        this.name = name; // name 프로퍼티는 public
    }
    // 프로토타입 메서드
    sayHi(){
        console.log(`Hello ${this.name}`);
    }

    // 정적 메서드
    static sayHello(){
        console.log("hello~");
    }
}
// 인스턴스 생성
const user1 = new User("jinHo");

console.log(user1.name); // jinHo
user1.sayHi(); // Hello jinHo
User.sayHello(); // hello~
```

**정적 메서드와 프로토타입 메서드의 차이**
1. 정적 메서드와 프로토타입 메서드는 자신이 속해 있는 프로토타입 체인이 다릅니다.
2. 정적 메서드는 클래스로 호출하고 프로토타입 메서드는 인스턴스로 호출합니다.
3. 정적 메서드는 인스턴스를 프로퍼티로 참조할 수 없지만 프로토타입 메서드는 인스턴스를 프로퍼티로 참조할 수 있습니다.

## 클래스의 상속
상속에 의한 클래스 확장은 프로토타입 기반 상속과는 다른 개념입니다.  
기존 클래스를 상속받아 새로운 클래스를 확장(extends)하여 정의하는 것입니다.   
[class](https://jsdmas.github.io/js/JS_prototypes_Class/#class)  
# 스프레드 문법

## Spread 문법이 뭔가요?
[spread](https://jsdmas.github.io/js/JS_Rest_Spread/)   
전개문법 `...` 은 하나로 뭉쳐 있는 여러 값들의 집합을 펼쳐서 개별적인 값들의 목록으로 만듭니다.  
## 어떤 상황에서 사용할 수 있죠?
1. Array
2. String
3. Map
4. Set
5. DOM 컬랙션
6. arguments 와 같이 for of 문으로 순회할 수 있는 이터러블
  

**이터러블이 아닌 일반 객체는 스프레드 문법의 대상이 될 수 없습니다.**   
```js
const merged = {x: 1, y: 2, ...{a: 3, b: 4}};
console.log(merged); // { x: 1, y: 2, a: 3, b: 4 }

console.log(...{ a : 1 , b : 2 }); // TypeError
```
# 구조 분해 할당

## 구조 분해 할당이 뭔가요?
구조화된 배열과 같은 이터러블 또는 객체를 비구조화, 구조 파괴하여 1개 이상의 변수에 개별적으로 할당하는 것을 말합니다.  
배열과 같은 이터러블 또는 객체 리터럴에서 필요한 값만 추출하여 변수에 할당할 때 유용합니다.  
## 구조 분해 할당은 크게 어떤 종류가 있나요?
1. 배열 구조분해 할당
2. 객체 구조분해 할당

```js
const arr = [1,2,3];
const [one,two,three] = arr;
console.log(one, two, three); // 1 2 3
```
# 브라우저 랜더링 과정

## 브라우저의 렌더링 과정에 대해 설명해보세요

## 브라우저의 렌더링 과정에 자바스크립트는 어떻게 동작하나요?

## script 태그를 body 태그 밑에 둬야하는 이유가 있을까요?
