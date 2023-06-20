# 목차

2번째 자바스크립트 정리 파일로, 클로저부터 정리합니다.

<details>
<summary>접기 / 펼치기</summary>

- [클로저](#클로저)
    - <span style="color: red">⭐️ 클로저가 뭔가요?</span>
    - <span style="color: red">클로저를 사용하면 뭐가 좋죠?</span>
    - <span style="color: red">클로저를 어떻게 생성하나요?</span>
- [ES6(ES2015)특징](#es6특징)
- [클래스](#클래스)
    - 자바스크립트에서 클래스가 생기기 전에는 어떤 방식으로 객체지향 패턴을 구현했나요?
    - 그럼 생성자 함수와 클래스는 어떤 차이가 있나요?
    - 클래스 정의
    - 클래스의 상속
- [스프레드 문법](#스프레드-문법)
    - Rest 연산자와 Spread 연산자에 대해 설명해주세요.
    - 어떤 상황에서 사용할 수 있죠?
- [구조 분해 할당](#구조-분해-할당)
    - 구조 분해 할당이 뭔가요?
    - 구조 분해 할당은 크게 어떤 종류가 있나요?
- [브라우저 렌더링 과정](#브라우저-랜더링-과정)
    - <span style="color: red">브라우저의 렌더링 과정에 대해 설명해보세요</span>
    - <span style="color: red">브라우저의 렌더링 과정에 자바스크립트는 어떻게 동작하나요?</span>
    - `script`태그를 `body`태그 및에 둬야하는 이유가 있을까요?
- [DOM](#dom)
    - DOM이 뭔가요?
    - DOM을 구성하는 건 뭐가 있을까요?
- [이벤트](#이벤트)
    - ⭐ 이벤트 버블링과 캡처링에 대해 설명해주세요.
    - ⭐ 이벤트 전파(propagation)에 대해서 알고 있나요?
    - ⭐ 이벤트 위임(delegation)에 대해서 알고있나요?
    - 마우스 이벤트 타입에는 뭐가 있나요? click 말고 클릭을 대체할 수 있는 이벤트가 있나요?
    - 그 외에 알고있는 대표적인 이벤트가 있나요?
    - 이벤트 핸들러를 등록하는 방식에는 어떤 것들이 있나요?
    - e.preventDefault 에 대해 알고 있나요?
    - e.stopPropagation
- [타이머](#타이머)
    - 호출 스케쥴링이 무엇인가요?
    - 타이머 함수에는 어떤 것들이 있나요?
    - 이벤트가 과도하게 호출되어 성능에 문제를 일으킬 경우에 할 수 있는 어떤 일을 통해 해결 할 수 있나요?
    - 디바운스에 대해서 알고 있나요?
    - 쓰로틀에 대해서 알고 있나요?
- [비동기 프로그래밍](#비동기-프로그래밍)
    - Blocking과 Non-Blocking에 대해 설명해주세요.
    - <span style="color: red">⭐ 동기와 비동기는 뭐고 차이점에 대해서 설명해줄 수 있나요?</span>
    - 비동기적으로 실행되는 것을 동기적으로 코딩하는 방법이 있나요?
    - <span style="color: red">이벤트 루프와 태스크 큐에 대해서 알고 있나요?</span>
    - <span style="color: red">마이크로태스크 큐에 대해서 알고 있나요?</span>
    - <span style="color: red">태스크 큐와 마이크로태스크 큐 중 어떤 것이 먼저 실행되나요?</span>
- [Ajax](#ajax)
    - Ajax가 뭔가요 어떤 것을 담당하고 있죠?
    - Ajax를 사용하면 기존 방식과 어떤 차이가 있을까요?
    - JSON이 뭔가요?
    - JSON이 제공하는 정적 프로토타입 메서드에 대해 몇가지 말해볼 수 있나요?
    - Ajax로 HTTP 요청을 보내기 위해서는 어떤 방법을 사용할 수 있나요?
    - <span style="color: red">XMLHttpRequest와 fetch 메서드의 차이는 무엇이라고 생각하시나요?</span>
- [REST API](#rest-api)
    - REST API가 뭔가요?
    - REST API의 구성은 어떤 것이 있나요?
    - REST API를 설계하는데 중요한 것이 있을까요?
    - HTTP 요청 메서드에 대해서 아는대로 얘기해보세요
    - <span style="color: red">HTTP 상태 코드를 아는대로 말해주세요</span>
- [Promise](#promise)
    - <span style="color: red">콜백이란 뭐라고 생각하나요?</span>
    - <span style="color: red">프로미스가 뭔가요?</span>
    - 프로미스 생성 방법
    - <span style="color: red">프로미스의 상태를 나타내는 것은 어떤 것들이 있나요?</span>
    - <span style="color: red">프로미스 빌트인 객체가 제공하는 정적 메서드에 대해 알고 있나요?</span>
- [제너레이터와 async await](#제너레이터와-async-await)
    - 이터러블과 이터레이터 프로토콜에 대해 설명해주세요.
    - 제너레이터란 뭔가요? 일반 함수와는 어떤 차이가 있죠?
    - 제너레이터의 구조
    - <span style="color: red">async/await 가 뭔가요? 기존의 Promise와는 어떤 차이가 있죠?</span>
    - <span style="color: red">Promise와 async/await의 차이점 한 줄 요약</span>
- [에러](#에러)
    - 에러처리를 왜 해야 하나요?
    - 자바스크립트에서 에러를 처리하는 방법에는 뭐가 있을까요?
- [모듈](#모듈)
    - 모듈이 뭔가요?

</details>


# 클로저

## ⭐️ 클로저가 뭔가요?
> 클로저란 함수가 속한 렉시컬 스코프를 기억하여 함수가 렉시컬 스코프 밖에서 실행될 때도 그 스코프에 접근할 수 있게 하는 기능을 말합니다.

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
## 클로저를 사용하면 뭐가 좋죠?

- 데이터 은닉화
- 지속적인 상태 유지
- 함수 팩토리
## 클로저를 어떻게 생성하나요?
> 함수 내부에서 새로운 함수를 정의하고, 그 함수를 반환하는 것입니다. 반환된 함수는 자신이 생성된 렉시컬 스코프에서 선언된 변수를 계속해서 참조할 수 있습니다.
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

# ES6특징

- 화살표 함수(Arrow Function)
  - `=>`로 사용할 수 있으며 일반 함수와 달리 `this`가 함수 스코프에 바인딩 되지 않고 렉시컬 스코프를 가집니다.
  - 즉, 자신을 감싸는 코드와 동일한 `this`를 공유합니다.
- 클래스(Class)
  - 프로토타입 기반의 객체지향 패턴을 쉽게 만든 장치로, 상속과 생성자 및 인스턴스와 정적 메서드 등을 지원합니다.
- 탬플릿 문자열
  - `' `` '` 복잡한 문자열을 쉽게 만들어줍니다.
- 비구조화
  - 배열과 객체의 패턴 매칭을 통해서 바인딩을 하는 기법입니다.
- let, const
  - 블록 스코프를 가지며 재선언이 불가능하며 선언 이전에는 사용할 수 없습니다.
- 모듈(Module)
  - import로 모듈 불러오기
- Map, Set 자료구조
- 심볼(Symbol)
- 프라미스(Promise)
  - 비동기 작업이 맞이할 미래의 완료/실패와 결과 값을 나타내는 객체입니다.


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

## Rest 연산자와 Spread 연산자에 대해 설명해주세요.
[spread, rest](https://jsdmas.github.io/js/JS_Rest_Spread/)   
> rest는 모든 값을 하나의 변수로 축소 (contract) 시켜주는것이다.
> spread는 변수를 가져와서 풀어 해치고 전개하는 것이다

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
1. 클라이언트에서 불러오고 싶은 파일을 서버에 요청합니다.
   - 주소창에 직접 입력하거나, 클릭을 통해 해당 웹 페이지에 접근한다.
   - 클라이언트에서 요청한 URL을 DNS를 통해 IP주소로 변환하고, 해당 IP를 가진 서버에 GET요청을 보내게 됩니다
2. 서버에서 응답으로 받은 HTML 데이터를 파싱한다. (바이트 > 문자 > 토큰 > 노드 > DOM)
   - 서버에서 존재하던 HTML 파일이 브라우저의 요청에 의해 응답된다.
   - 이때 서버는 브라우저가 요청한 HTML 문서를 바이트(2진수) 형태로 응답받는다.
   - 브라우저는 서버가 응답한 HTML 문서를 바이트(2진수) 형태로 응답받는다.
   - 따라서 응답된 바이트 형태의 HTML 문서를 meta 태그의 charset 어트리뷰트에 의해 지정된 인코딩 방식을 기준으로 문자열로 변환한다.
   - 문자열로 변환된 HTML 문서를 읽어 들여 문법적 의미를 갖는 코드의 최소 단위인 토큰(token)들로 분해한다.
   - 각 토큰들을 객체로 변환하여 노드들을 생성한다. 토큰의 내용에 따라 (1)문서 노드 (2)요소 노드 (3)어트리뷰트 노드 (4)텍스트 노드가 생성된다.
3. HTML 마크업을 바탕으로 DOM 트리를 생성한다.
   - HTML 문서는 HTML 요소들의 집합으로 이루어지며 HTML 요소는 중첩 관계를 갖는다
   - 이때 HTML 요소 간에는 중첩 관계에 의해 부모자식 관계가 형성된다.
   - 이러한 HTML 요소 간의 부모자식 관계를 반영하여 모든 노드들을 트리 자료구조로 구성한다.
   - 이 노드들로 구성된 트리 자료구조를 DOM이라 부른다.
4. CSS 마크업을 바탕으로 CSSOM 트리를 생성한다. (바이트 > 문자 > 토큰 > 노드 > CSSOM)
   - HTML 데이터와 마찬가지로 파싱하여 CSSOM 트리 구조로 나타낸다.
5. DOM 트리와 CSSOM트리를 결합하여 렌더 트리를 형성한다.
   - 렌더링 엔진에 의해 문서의 처음부터 끝까지 해석이 완료되어 DOM트리와 CSSOM 트리가 완성된다면, 이 둘을 바탕으로 랜더 트리를 생성한다.
6. 렌더 트리에서 레이아웃을 실행한다.
   - 랜더 트리를 기반으로 HTML 요소의 레이아웃(위치와 크기)를 계산합니다.
7. 개별 노드를 화면에 페인트한다.
   - 이후 레이아웃을 바탕으로 브라우저 화면에 픽셀을 렌더링하는 페인팅(painting)처리에 입력되면 렌더링이 완료되게 됩니다.

## 브라우저의 렌더링 과정에 자바스크립트는 어떻게 동작하나요?
1. HTML/CSS 파싱 과정과 마찬가지로 `렌더링 엔진`은 HTML을 한 줄씩 순차적으로 파싱하며 DOM을 생성해 나가다가 자바스크립트 파일을 로드하는 `<script>`태그나 자바스크립트 코드를 콘텐츠로 담은 `<script>`태그를 만나면 DOM 생성을 일시 중단한다.
2. 그리고 `<script>`태그의 src 어트리뷰트에 정의된 자바스크립트 파일을 서버에 요청하여 로드한 자바스크립트 파일이나 `<script>`태그 내의 자바스크립트 코드를 파싱하기 위해 `자바스크립트 엔진`에 제어권을 넘긴다. 이후 자바스크립트 파싱과 실행이 종료되면 `렌더링 엔진`으로 다시 제어권을 넘겨 HTML 파싱이 중단된 지점부터 다시 HTML 파싱을 시작하여 DOM 생성을 재개한다.
3. 자바스크립트 파싱과 실행은 `브라우저 렌더링 엔진`이 아닌 `자바스크립트 엔진`이 처리한다. `자바스크립트 엔진`은 자바스크립트 코드를 파싱하여 CPU가 이해할 수 있는 저수준 언어(low-level language)로 변환하고 실행하는 역할을 한다.
4. `자바스크립트 엔진`은 자바스크립트를 해석하여 `AST(Abstract Syntax Tree : 추상적 구문 트리)`를 생성한다. 그리고 AST를 기반으로 인터프리터가 실행할 수 있는 중간 코드 (intermediate code)인 바이트코드를 생성하여 실행한다.
5. `리플로우와 리페인트`
   - 만약 자바스크립트 코드에 DOM이나 CSSOM을 변경하는 DOM API가 사용된 경우 DOM이나 CSSOM이 변경된다.
   - 이때 변경된 DOM과 CSSOM은 다시 렌더 트리로 결합되고 변경된 렌더 트리를 기반으로 레이아웃과 페인트 과정을 거쳐 브라우저의 화면에 다시 렌더링한다. 이를 리플로우(reflow), 리페인트(repaint)라 한다.

<details>
<summary>용어 정리</summary>

- 파싱
  - 파싱(구문 분석)은 프로그래밍 언어의 문법에 맞게 작성된 텍스트 문서를 읽어 들여 실행하기 위해 텍스트 문서의 문자열을 토큰 단위로 분해하고, 토큰의 문법적 의미와 구조를 반영하여 트리 구조의 자료구조인 파스 트리를 생성하는 일련의 과정을 말한다.
- 렌더링
  - 렌더링은 HTML,CSS,JS 로 작성된 문서를 파싱하여 브라우저에 시각적으로 출력하는 것을 말한다.
- 리소스
  - HTTP 요청 대상을 "리소스"라고 부르는데, 그에 대한 본질을 이 이상으로 정의할 수 없습니다.
  - 그것은 문서, 사진 또는 다른 어떤 것이든 될 수 있습니다.
  - 각 리소스는 리소스 식별을 위해 HTTP 전체에서 사용되는  Uniform Resource Identifier (URI)에 의해 식별됩니다.
- DNS
  - DNS(Domain Name System)는 인터넷에 연결된 리소스를 위한 계층적이고 분산된 명명 시스템입니다.
  - DNS는 도메인 이름 목록과 연결된 리소스(예 : IP주소)를 유지 관리 합니다.

</details>

## script 태그를 body 태그 밑에 둬야하는 이유가 있을까요?

- HTML 파서는 script 태그를 만나면 파싱을 멈추고 스크립트 파일을 읽기 떄문에 DOM 생성이 지연되어 스크립트 파일이 많거나 파일이 크면 읽는 시간이 오래 걸려 Display에 표시되는 것이 지연됩니다.
- DOM tree가 완성되지 않은 상태에서 JavaScript가 DOM을 조작한다면 에러가 발생할 수 있습니다.

이렇게 동기적으로 코드를 실행하는 자바스크립트에서 근본적인 문제를 해결하기 위해 `<script>`태그에 `async, defer`어트리뷰트가 추가되었습니다.  
`async, defer`어트리뷰트는 다음과 같이 src 어트리뷰트를 통해 외부 자바스크립트 파일을 로드하는 경우에만 사용할 수 있습니다. `<script>`태그 내부에 코드를 작성하는 경우에는 사용할 수 없습니다.  

- `async 어트리뷰트`
  - HTML 파싱과 외부 자바스크립트 파일의 로드가 비동기적으로 동시에 진행됩니다.
  - 단, 자바스크립트의 파싱과 실행은 자바스크립트의 파일의 로드가 완료된 직후 진행되며, 이때 HTML 파싱은 중단됩니다.
    ![image](https://user-images.githubusercontent.com/105098581/223293411-6f22f91d-965e-41a7-a70d-e6b4179f94ea.png)
  - 여러 개의 script 태그에 async 어트리뷰트를 지정하면 script 태그의 순서와는 상관없이 로드가 완료된 자바스크립트부터 먼저 실행되므로 순서가 보장되지 않습니다.

- `defer 어트리뷰트`
  - async 어트리뷰트와 마찬가지로 HTML 파싱과 외부 자바스크립트 파일의 로드가 비동기적으로 동시에 진행됩니다.
  - 단, 자바스크립트의 파싱과 실행은 HTML 파싱이 완료된 직후, 즉 DOM 생성이 완료된 직후 진행됩니다.
  - 따라서 DOM 생성이 완료된 이후 실행되어야 할 자바스크립트에 유용합니다.
    ![image](https://user-images.githubusercontent.com/105098581/223293826-d3f334f1-8287-44fd-ac81-7b0aee783ed4.png)



# DOM

## DOM이 뭔가요?
DOM은 HTML 문서의 계층적 구조와 정보를 표현하며 이를 제어할 수 있는 API, 즉 프로퍼티와 메서드를 제공하는 트리 자료구조입니다.

## DOM을 구성하는 건 뭐가 있나요?
HTML 요소는 렌더링 엔진에 의해 파싱되어 DOM을 구성하는 요소 노드 객체로 변환됩니다.  
이떄 HTML 요소 어트리뷰트는 어트리뷰트 노드로, HTML 요소의 텍스트 콘텐츠는 텍스트 노드로 변환됩니다.  
DOM은 노드 객체의 계층적인 구조로 구성됩니다. 노드 객체는 종류가 있고 상속 구조를 갖습니다.  
노드 객체는 총 12개의 종류(노드 타입)가 있습니다. 이 중에서 중요한 노드 타입은 다음과 같이 4가지입니다.  
1. 문서노드
   ```html
   <!DOCTYPE>
   ```
   - 문서 노드는 DOM 트리의 최상위에 존재하는 루트 노드로서 document 객체를 가리킵니다.
   - document 객체는 브라우저가 렌더링한 HTML 문서 전체를 가리키는 객체로서 전역 객체 window의 document 프로퍼티에 바인딩되어 있습니다.
   - 따라서 문서 노드는 window.document 또는 document로 참조할 수 있습니다.
   - 브라우저 환경의 모든 자바스크립트 코드는 script 태그에 의해 분리되어 있어도 하나의 전역 객체 window를 공유합니다.
   - 따라서, window의 docuemnt 프로퍼티에 바인딩되어 있는 하나의 document 객체를 바라봅니다. 즉, HTML 문서당 document 객체는 유일합니다.
    
2. 요소 노드
   ```html
   <html> <head> <meta> <link> <body> <ul> <li> <script>
   ``` 
   - 요소 노드는 HTML 요소를 가리키는 객체입니다. 요소 노드는 HTML 요소 간의 중첩에 의해 부자 관계를 가지며, 이 부자 관계를 통해 정보를 구조화합니다.
   - 따라서 요소 노드는 문서의 구조를 표현한다고 할 수 있습니다.


3. 어트리뷰트 노드
   ```
   charset="UTF"
   rel="stylesheet"
   ...
   id="hello"
   ``` 
   - 어트리뷰트 노드는 HTML 요소의 어트리뷰트를 가리키는 객체입니다.
   - 어트리뷰트 노드는 어트리뷰트가 지정된 HTML 요소의 요소 노드와 연결되어 있습니다.


4. 텍스트 노드
   ```
   APPLE
   BANANA
   ORANGE
   ``` 
   - 텍스트 노드는 HTML 요소와 텍스트를 가리키는 객체입니다.
   - 요소 노드가 문서의 구조를 표현한다면 텍스트 노드는 문서의 정보를 표현한다고 할 수 있습니다.

# 이벤트

## ⭐ 이벤트 전파(propagation)에 대해서 알고 있나요?

> DOM(Documnet Object Model)요소에서 발생한 이벤트가 상위 요소로 전달되는 방식을 말합니다.
HTML 문서의 각 엘리먼트들은 아래와 같이 태그안의 태그가 위치하는 식으로 **계층적**으로 이루어짐을 볼 수 있습니다.  
이러한 계층적 구조 특징 떄문에 만일 HTML 요소에 이벤트가 발생할 경우 **연쇄적 이벤트 흐름**이 일어나게 됩니다.  
```html
<form onclick="alert('form')">FORM
    <div onclick="alert('div')">DIV
    	<p onclick="alert('p')">P</p>
    </div>
</form>
<!-- p 클릭시 p, div, form alert가 순차적으로 나타남-->
```
이러한 현상을 이벤트 전파(Event Propagation)라 부르며, 전파 방향에 따라 버블링과 캡처링으로 구분합니다.  

### 이벤트 전파 흐름

1. 캡처링 단계 : 이벤트가 하위 요소로 전파되는 단계
2. 타깃 단계 : 이벤트가 실제 타깃 요소에 전달되는 단계
3. 버블링 단계 : 이벤트가 상위 요소로 전파되는 단계

![](https://github.com/jsdmas/dev-matching-fe-practice/assets/105098581/15bc02b3-1ee5-4293-a45c-84fe49c097ba)
1. `td`를 클릭하면 이벤트가 최상위 조상에서 시작해 아래로 전파됩니다. (캡처링)
2. 이벤트가 타겟 요소에 도착해 리스너를 실행합니다.(타깃)
3. 그리고 다시 상위로 이벤트를 전파합니다. (버블링)

## ⭐ 이벤트 위임(delegation)에 대해서 알고있나요?

> 하위 엘리먼트들이 여러개 있을 떄, 하위 엘리먼트들에 각각 이벤트 핸들러를 달지 않고 상위 엘리먼트에 이벤트 핸들러를 달아 하위 엘리먼트들을 제어하는 방식입니다.
 
- 동적으로 엘리먼트를 추가할 떄마다 핸들러를 고려할 필요가 없습니다.
- 상위 엘리먼트에 하나의 이벤트 핸들러만 추가하면 되기 때문에 코드가 훨씬 깔끔해집니다.
- 메모리에 있게되는 이벤트 핸들러가 적어지기 때문에 퍼포먼스 측면에서 이점이 있습니다.

## ⭐ 이벤트 버블링과 캡처링에 대해 설명해주세요.

![](https://github.com/jsdmas/dev-matching-fe-practice/assets/105098581/7498656e-5528-4666-8eee-cbb1f3fcb90d)

### 이벤트 버블링(Bubbling)
> 하위 엘리먼트 이벤트가 발생시 그 엘리먼트부터 시작해서 상위요소까지 전달되는 방식을 말합니다.

### 이벤트 캡처링
> 하위 엘리먼트에 이벤트가 있을 떄 상위 엘리먼트부터 이벤트가 발생하기 시작해서 하위 엘리먼트까지 이벤트가 전달되는 방식을 말합니다.

## 마우스 이벤트 타입에는 뭐가 있나요? click 말고 클릭을 대체할 수 있는 이벤트가 있나요?
> mouseup
| 이벤트 타입 | 이벤트 발생 시점                                      |
| ----------- | ----------------------------------------------------- |
| click       | 마우스 버튼을 클릭했을 때                             |
| dbclick     | 마우스 버튼을 더블 클릭했을 떄                        |
| mousedown   | 마우스 버튼을 누르고 있을 떄                          |
| mouseup     | 누르고 있던 마우스 버튼을 뗄 떄                       |
| mousemove   | 마우스 커서를 움직일 때                               |
| mouseenter  | 마우스 커서를 HTML 요소 안으로 이동했을 떄 (버블링 x) |
| mouseover   | 마우스 커서를 HTML 요소 안으로 이동했을 떄 (버블링 o) |
| mouseleave  | 마우스 커서를 HTML 요소 밖으로 이동했을 떄 (버블링 x) |
| mouseout    | 마우스 커서를 HTML 요소 밖으로 이동했을 떄 (버블링 o) |

## 그 외에 알고 있는 대표적인 이벤트가 있나요?
**키보드 이벤트**
| 이벤트 타입 | 이벤트 발생 시점       |
| ----------- | ---------------------- |
| keydown     | 키를 누르고 있을 때    |
| keyup       | 누르고 있던 키를 뗄 때 |

**포커스 이벤트**
| 이벤트 타입 | 이벤트 발생 시점                     |
| ----------- | ------------------------------------ |
| focus       | 요소가 포커스를 얻었을 떄 (버블링 x) |
| blur        | 요소가 포커스를 잃었을 떄 (버블링 x) |
| focusin     | 요소가 포커스를 얻었을 떄 (버블링 o) |
| focusout    | 요소가 포커스를 잃었을 떄 (버블링 o) |

**폼 이벤트**
| 이벤트 타입 | 이벤트 발생 시점       |
| ----------- | ---------------------- |
| submit      | form을 submit할 떄     |
| reset       | reset 버튼을 클릭할 떄 |

**값 변경 이벤트**
| 이벤트 타입 | 이벤트 발생 시점                                          |
| ----------- | --------------------------------------------------------- |
| input       | input 또는 textarea 요소의 값이 변경되었을 때             |
| change      | select box, checkbox, radio button의 상태가 변경되었을 때 |

**DOM 뮤테이션 이벤트**
| 이벤트 타입      | 이벤트 발생 시점                                            |
| ---------------- | ----------------------------------------------------------- |
| DOMContentLoaded | HTML 문서의 로드와 파싱이 완료되어 DOM 생성이 완료되었을 떄 |

**뷰 이벤트**
| 이벤트 타입 | 이벤트 발생 시점                                                |
| ----------- | --------------------------------------------------------------- |
| resize      | 브라우저 윈도우의 크기를 리사이즈할 때 연속적으로 발생          |
| scroll      | 웹페이지(document) 또는 HTML 요소를 스크롤할 때 연속적으로 발생 |

**리소스 이벤트**
| 이벤트 타입 | 이벤트 발생 시점                                            |
| ----------- | ----------------------------------------------------------- |
| load        | DOMContentLoaded 이후, 모든 리소스의 로딩이 완료되었을 때   |
| unload      | 리소스가 언로드 될 떄 (주로 새로운 웹 페이지를 요청한 경우) |
| abort       | 리소스 로딩이 중단되었을 떄                                 |
| error       | 리소스 로딩이 실패했을 떄                                   |

## 이벤트 핸들러를 등록하는 방식에는 어떤 것들이 있나요?
1. 이벤트 핸들러 어트리뷰트 방식

```html
<!DOCTYPE html>
<html>
    <body>
        <button onclick="sayHi('jinHo')">Click</button>
        <script>
            function sayHi(name){
                console.log(`hello ${name}`);
            }
        </script>
    </body>
</html>
```

2. 이벤트 핸들러 프로퍼티 방식

```html
<!DOCTYPE html>
<html>
    <body>
        <button>Click</button>
        <script>
            const btn = document.querySelectorAll("button");
            btn.onclick = function(){
                console.log("click!");
            }
        </script>
    </body>
</html>
```

3. addEventListener 메서드 방식

```html
<!DOCTYPE html>
<html>
    <body>
        <button>Click</button>
        <script>
            const btn = document.querySelectorAll("button");
            btn.addEventListener("click", ()=>{
                console.log('hello');
            });
        </script>
    </body>
</html>
```


## e.preventDefault 에 대해 알고 있나요?
e.preventDefault 메서드는 요소 태그의 기본 동작을 중단합니다.
## e.stopPropagation
e.stopPropagation 메서드는 이벤트 전파를 중지시키는 메서드입니다.  
# 타이머

## 호출 스케쥴링이 무엇인가요?
호출 스케쥴링(Calling Scheduling)은 JavaScript에서 함수를 실행할 때, 언제 실행할지를 결정하는 프로세스입니다.  
JavaScript에서는 함수 실행을 즉시 처리하지 않고, 호출 스택(Call Stack)과 이벤트 루프(Event Loop)를 사용하여 비동기적으로 처리합니다. 이 때, 호출 스케쥴링은 함수를 언제 호출할지를 결정하는 중요한 역할을 합니다.  

함수를 명시적으로 호출하면 함수가 즉시 실행됩니다.
```js
function add(a,b){
    return a+ b;
}
console.log(add(2,5)); // 7
```
만약 함수를 명시적으로 호출하지 않고 시간이 경과된 이후에 호출되도록 함수 호출을 예약하려면, 타이머 함수를 사용해야 합니다.  
이렇게 타이머 함수를 사용하여 명시적으로 호출하지 않고 일정 시간이 경기된 이후에 호출되도록 함수 호출을 예약하는 것을 호출 스케쥴링이라고 합니다.  
## 타이머 함수에는 어떤 것들이 있나요?
[JS_setTimeout , setInterval](https://jsdmas.github.io/js/JS_setTime_Interval/)  
1. setTimeout / clearTimeout
2. setInterval / clearInterval


## 이벤트가 과도하게 호출되어 성능에 문제를 일으킬 경우에 할 수 있는 어떤 일을 통해 해결 가능한가요?
scroll, resize, mousemove 같은 이벤트는 짧은 시간 간격으로 연속해서 발생합니다.  
이러한 이벤트에 바인딩한 이벤트 핸들러는 과도하게 호출되어 성능에 문제를 일으킬 수 있습니다.  
디바운스와 쓰로틀은 짧은 시간 간격으로 연속해서 발생하는 이벤트를 그룹화해서 과도한 이벤트 핸들러의 호출을 방지하는 프로그래밍 기법입니다.  
이렇게 디바운스와 쓰로틀을 사용하여 이벤트가 과도하게 호출되는 것을 막거나, 조절할 수 있습니다.  

## 디바운스에 대해서 알고 있나요?
디바운스(debounce)는 연이어 발생한 이벤트를 하나의 그룹으로 묶어서 처리하는 방식으로, 주로 그룹에서 처음이나 마지막으로 실행된 함수를 처리하는 방식으로 사용됩니다.   
사용예시로는 다음과 같습니다.
- 사용자가 창 크기 조정을 멈출 때까지 기다렸다가 resizing event를 반영하고 싶다면 사용합니다.
- 사용자가 키보드 입력을 중지할 떄까지 AJAX 이벤트를 발생시키지 않고 싶다면 사용합니다.

```js
const input = document.querySelector("#input");
const app = document.querySelector("#app");

const callAjaxRequest = e => {
   app.innerContext = `ajax 요청 ${e.target.value}`;
};

const debounce = (func) => {
  let timer;
  return (event)=>{
     if(timer){
       clearTimeout(timer);
     }
    timer = setTimeout(func(event), 500);
  };
};

input.addEventListener("input", debounce(callAjaxRequest));
```


## 쓰로틀에 대해서 알고 있나요?
쓰로틀링은 출력을 조절한다는 의미를 가지고 있습니다.  
프로그래밍에서 쓰로틀링은 이벤트를 일정주기마다 발생하도록 하는 기술입니다.  
Throttle의 설정 시간으로 100ms를 주게 된다면, 해당 이벤트는 100ms 동안 최대 한 번만 발생하게 됩니다. 즉, 마지막 함수가 호출된 후 일정 시간이 지나기 전에 다시 호출되지 않도록 합니다.  
- 쓰로틀은 scroll 이벤트 처리나 무한 스크롤 UI 구현 등에 유용하게 사용됩니다.

```js
const input = document.querySelector("#input");
const countNumber = document.querySelector("#count-number");
let count = 0;
const increaseCountNumber = () => {
    countNumber.innerText = count++;
};

const throttle = (func) => {
  let timer;
  return ()=>{
     if(!timer){
        // timer가 없을시에만 실행
        timer = setTimeout(()=>{
            // 1000ms 가 지난후에 timer를 초기화와 동시에 지정해놓은 함수 실행
            timer = null;
            func();
        }, 1000);
     }
  };
};

input.addEventListener("scroll", throttle(increaseCountNumber));
```


# 비동기 프로그래밍

## Blocking과 Non-Blocking에 대해 설명해주세요.

> 블로킹/논블로킹은 단어 그대로 현재 작업이 block(차단, 대기)되느냐 아니냐에 따라 다른 작업을 수행할 수 있는가에 대한 프로세스 실행 방식입니다.
- Blocking(차단)
  - 코드 실행 흐름이 일시 중단되거나 블록되는 상태를 말합니다.
  - 동기적인 작업이 실행될 때 발생하며, 작업이 완료될 떄까지 코드 실행이 중단됩니다.
- Non-Blocking(비차단)
  - 코드 실행 흐름이 일시 중단되지 않고 계속 진행되는 상태를 말합니다.
  - 비동기적인 작업이 실행될 떄 발생하며, 작업이 완료되기를 기다리지 않고 다음 코드가 실행됩니다.

## ⭐ 동기와 비동기는 뭐고 차이점에 대해서 설명해줄 수 있나요?

> 동기 처리 방식은 현재 실행중인 태스크가 종료될 떄까지 다음에 실행될 태스크가 대기하는 방식을 말합니다.
> 비동기 처리 방식은 현재 실행중인 태스크가 종료되지 않은 상태라 해도 다음 태스크를 곧 바로 실행하는 방식을 말합니다.

javaScript는 기본적으로 함수를 호출하면 함수 코드가 평가되어 함수 실행 컨텍스트가 생성됩니다.  
이때 생성된 함수 실행 컨택스트는 실행 컨텍스트 스택(call stack)에 푸쉬되고 함수 코드가 실행됩니다.  
함수 코드의 실행이 종료되면 함수 실행 컨텍스트는 실행 컨텍스트 스택에서 팝되어 제거됩니다.  

## 비동기적으로 실행되는 것을 동기적으로 코딩하는 방법이 있나요?

- CallBack 방식
  - 함수를 다른함수의 인자로 전달하는 방식
- Promise방식
  - 비동기 작업 상태를 나타내는 객체입니다. 성공이나 실패를 then(),catch()메서드로 수행할 수 있습니다.
- async/await 방식
  - Promise를 더 간결하게 표현할 수 있습니다.

## 이벤트 루프와 태스크 큐에 대해서 알고 있나요?

![image](https://user-images.githubusercontent.com/105098581/223355458-12ce0d96-1e6c-4314-a4cb-1766c5e86d3a.png)  

- 이벤트 루프(Event Loop)
  - 자바스크립트의 실행 환경에서 비동기 처리를 담당하는 메커니즘입니다.
  - 호출 스택(call stack), 태스크 큐(Task Queue), 백그라운드(Background) 세 가지 요소로 구성됩니다.
  - 호출 스택은 현재 실행 중인 함수가 저장되는 스택이며, 태스크 큐는 비동기 함수의 콜백 함수들이 대기하는 큐입니다.
  - 백그라운드는 Web API나 브라우저 API와 같은 비동기 API가 실행되는 곳입니다.
  - 이벤트 루프는 호출 스택이 비어있을 때, 태스크 큐에서 대기하고 있는 콜백 함수를 호출 스택으로 이동시킵니다.
- 태스크 큐(Task Queue)
  - 비동기 함수의 콜백 함수들이 대기하는 큐입니다.
  - 콜백 함수는 이벤트 핸들러 함수, 타이머 함수, Promise 객체의 then() 함수와 같은 비동기 함수에서 반환되는 콜백 함수를 의미합니다.
  - 비동기 함수가 호출되면 해당 함수는 호출 스택에서 실행되지 않고, 백그라운드에서 비동기적으로 실행됩니다.
  - 비동기 함수의 실행이 완료되면 해당 콜백 함수는 태스크 큐에 추가됩니다.

## 다음과 같은 코드에서 이벤트 루프와 태스크 큐가 어떻게 동작하는지 설명해볼 수 있나요?
```js
function foo(){
    console.log("foo");
}
function bar(){
    console.log("bar");
}
setTimeout(foo,0); // 0초 (실제는 4ms) 후에 foo 함수가 호출됩니다.
bar();
```
1. 실행 컨텍스트에 의해 전역 스코프에 존재하는 함수(foo, bar)가 평가되어 전역 실행 컨텍스트를 생성합니다.
2. 전역 코드 실행 단계에서 상대적으로 위에 존재하는 setTimeout 함수를 호출합니다.
   - 이떄 setTimeout 함수의 실행 컨텍스트가 생성되고 콜스택에 푸시되어 실행 중인 실행 컨텍스트가 됩니다.
3. setTimeout 함수가 실행되면서 콜백 함수를 호출 스케줄링(주어진 시간 0ms)하고 종료되어 콜 스택에서 팝 됩니다.
   - 이떄 타이머의 설정과 타이머가 만료되면 콜백 함수(foo)를 태스크 큐에 푸시하는 것은 브라우저의 역할입니다.
4. 브라우저가 수행하는 4.1 과 자바스크립트 엔진이 수행하는 4.2 는 병렬 처리 됩니다.
    `4.1` : 브라우저는 타이머를 설정하고 타이머의 만료를 기다린다. 이후 타이머가 만료되면 콜백 함수 foo가 태스크 큐에 푸시됩니다.  
    `4.2` : bar 함수가 호출되어 bar 함수의 함수 실행 컨텍스트가 생성되고 콜 스택에 푸시되어 현재 실행 중인 컨텍스트가 된다. 이후 bar 함수가 종료되어 콜 스택에서 팝된다.
5. 비동기로 진행되는 함수, HTTP요청, 이벤트 핸들러 는 브라우저에 의해 태스크 큐로 이동하게 되는데, 동기적으로 실행되는 함수가 모두 실행되고 콜 스택에서 팝된 이후에 태스크 큐에 먼저 들어온 함수부터 차례대로 콜스택에 푸시합니다.

```js
>>>
bar
foo
```

## 마이크로태스크 큐에 대해서 알고 있나요?
마이크로태스크 큐(microtask queue)는 자바스크립트에서 비동기 처리 중에 즉시 실행되어야 하는 작업들을 저장하는 큐입니다. Promise와 관련된 콜백 함수, MutationObserver 콜백 함수, Object.observe 콜백 함수와 같이, 이벤트 루프가 호출 스택을 처리하기 전에 즉시 실행되어야 하는 작업들이 이 큐에 추가됩니다.   
그 외의 비동기 함수의 콜백 함수나 이벤트 핸들러는 태스크 큐에 일시 저장됩니다.   
콜백 함수나 이벤트 핸들러를 일시 저장한다는 점에서 태스크 큐와 동일하지만 마이크로태스크 큐는 태스크 큐보다 우선순위가 높습니다.
```js
setTimeout(() => console.log(1), 0);

Promise.resolve()
  .then(() => console.log(2))
  .then(() => console.log(3));
// 프로미스의 후속 처리 메서드의 콜백 함수는 테스크 큐 가 아니라 마이크로태스크 큐 에 저장된다.
//  2 > 3 > 1
```

## 태스크 큐와 마이크로태스크 큐 중 어떤 것이 먼저 실행되나요?
마이크로태스크 큐는 태스크 큐보다 우선순위가 높습니다.  
따라서 이벤트 루프에서 마이크로태스크 큐에 쌓인 태스크를 먼저 콜 스택에 올려준 뒤, 태스크 큐에 잔여 태스크를 콜 스택에 올립니다.  
# Ajax

## Ajax가 뭔가요 어떤 것을 담당하고 있죠?
Asynchronous JavaScript and XML 의 약자로, 비동기식 JavaScrip와 XML을 사용하여 웹 페이지를 업데이트하는 웹 개발 기술입니다.  

- 브라우저가 서버에게 비동기 방식으로 데이터를 요청하고, 서버가 응답한 데이터를 수신하여 웹페이지를 동적으로 갱신하는 프로그래밍 방식을 말합니다.  
- Ajax는 브라우저에서 제공하는 호스트 객체 Web API인 XMLHttpRequest 객체를 기반으로 동작합니다.
- XMLHttpRequest는 HTTP 비동기 통신을 위하 메서드와 프로퍼티를 제공합니다.
  - XMLHttpRequest는 Ajax에서 가장 핵심적인 객체 중 하나로, 비동기적으로 서버와 데이터를 주고 받을 수 있도록 지원하는 JavaScript 객체입니다.
  - 웹 페이지의 JavaScript 코드에서 HTTP 요청을 생성하고, 서버에서 HTTP 응답을 비동기적으로 받아올 수 있습니다.
- 이전의 웹 페이지는 html태그로 시작해서 html 태그로 끝나는 완전한 HTML을 서버로부터 전송받아 웹 페이지 전체를 처음부터 다시 렌더링 하는 방식으로 동작했습니다.
- Ajax의 등장으로 서버로부터 웹페이지의 변경에 필요한 데이터만 비동기 방식으로 전송받아 웹페이지를 변경할 필요가 없는 부분까지 다시 렌더링하지 않고, 변경할 필요가 있는 부분만 한정적으로 렌더링하는 방식이 가능해졌습니다.

## Ajax를 사용하면 기존 방식과 어떤 차이가 있을까요?
1. 변경할 부분을 갱신하는데 필요한 데이터만 서버로부터 전송받기 때문에 불필요한 데이터 통신이 발생하지 않는다.
2. 변경할 필요가 없는 부분은 다시 렌더링하지 않습니다. 따라서 화면이 순간적으로 깜박이는 현상이 발생하지 않습니다.
3. 클라이언트와 서버와의 통신이 비동기 방식으로 동작하기 때문에 서버에게 요청을 보낸 이후 블로킹이 발생하지 않습니다.

## JSON이 뭔가요?
JSON은 JavaScript Object Notation의 약자입니다.  
JSON은 클라이언트와 서버 간의 HTTP 통신을 위한 텍스트 데이터 포맷입니다.  
자바스크립트에 종속되지 않는 언어 독립형 데이터 포맷으로, 대부분의 프로그래밍 언어에서 사용할 수 있습니다.  
객체 리터럴과 유사하게 키와 값으로 구성된 순수한 텍스트입니다.
```json
{
    "name":"jinHo",
    "age": 25,
    "happy": true
}
```
## JSON이 제공하는 정적 프로토타입 메서드에 대해 몇가지 말해볼 수 있나요?
1. JSON.stringify()
   - 객체를 JSON 포맷의 문자열로 변환합니다.
   - 클라이언트가 서버로 객체를 전송하려면 객체를 문자열화 해야하는데 이를 직렬화(serializing)라 합니다.
2. JSON.parse()
   - JSON 포맷의 문자열을 객체로 변환합니다.
   - 서버로부터 클라이언트에게 전송된 JSON 데이터는 문자열입니다.
   - 이 문자열을 객체로 사용하려면 JSON 포맷의 문자열을 객체화 해야하는데 이를 역직렬화(deserializing)라 합니다. 

## Ajax로 HTTP 요청을 보내기 위해서는 어떤 방법을 사용할 수 있나요?
1. XMLHttpRequest
브라우저는 주소창이나 HTML의 form 태그 또는 a 태그를 통해 HTTP 요청 전송 기능을 기본 제공합니다.   
자바스크립트를 사용하여 HTTP 요청을 전송하려면 XMLHttpRequest 객체를 사용합니다.   
Wep API인 XMLHttpRequest 객체는 HTTP 요청 전송과 HTTP 응답 수신을 위한 다양한 메서드와 프로퍼티를 제공합니다.  
**HTTP GET 요청**
```js
// XMLHttpRequest 객체 생성
const xhr = new XMLHttpRequest();

// HTTP 요청 초기화
xhr.open("GET", "/users");

// HTTP 요청 해더 설정
// 클라이언트가 서버로 전송할 데이터의 MIME 타입 지정 : json
xhr.setRequestHeader("content-type", "application/json");

// HTTP 요청 전송
xhr.send();
```
**HTTP POST 요청**
```js
const xhr = new XMLHttpRequest();
xhr.open("POST", "/users");
xhr.setRequestHeader("content-type", "application/json");
xhr.send(JSON.stringify({id:1, content:"HTML", completed:false}));
```
**HTTP 응답 처리**
```js
const xhr = new XMLHttpRequest();
xhr.open("POST", "http://naver.com");
xhr.send();
// load 이벤트는 HTTP 요청이 성공적으로 완료된 경우 발생합니다.
xhr.onload = () => {
    if(xhr.status === 200){
        console.log(JSON.parse(xhr.response));
    }else{
        console.error(xhr.status, xhr.statusText);
    }
};
```

2. Fetch
fetch 함수는 XMLHttpRequest 객체와 마찬가지로 HTTP 요청 전송 기능을 제공하는 클라이언트 사이드 Web API입니다.  
프로미스를 지원하기 떄문에 비동기 처리를 위한 콜백 패턴의 단점에서 자유롭습니다.  

```js
// 옵션도 추가 가능합니다. 기본값 GET
fetch("http://naver.com")
    .then((response)=>response.json())
    .catch((error)=>console.log(error));
```

## XMLHttpRequest와 fetch 메서드의 차이는 무엇이라고 생각하시나요?
둘다 Ajax 통신을 위해 사용됩니다.  
하지만 `fetch`메서드는 Promise를 기반으로 구성되어 있어서 더 간편하게 사용할 수 있다는 차이점이 있습니다.  
Promised의 후속 처리 메서드 `then, catch, finally`등을 사용하여 코드를 작성할 수 있습니다.  
# REST API

## REST API가 뭔가요?
REST는 Representational State Transfer의 약자로, 웹 서비스 아키텍처를 설계하는 데 사용되는 아키텍처 스타일입니다.  
- REST는 HTTP를 기반으로 클라이언트가 서버의 리소스에 접근하는 방식을 규정한 아키텍처입니다.
- REST API는 REST를 기반으로 서비스 API를 구현한 것을 의미합니다.
- REST의 기본 원칙을 성실히 지킨 서비스 디자인을 **RESTful** 이라고 표현합니다.


## REST API의 구성은 어떤 것이 있나요?
REST API는 자원(resource), 행위(verb), 표현(representations) 의 3가지 요소로 구성됩니다.  
| 구성 요소             | 내용                           | 표현 방법        |
| --------------------- | ------------------------------ | ---------------- |
| 자원(resource)        | 자원                           | URI(엔드 포인트) |
| 행위(verb)            | 자원에 대한 행위               | HTTP 요청 메서드 |
| 표현(representations) | 자원에 대한 행위의 구체적 내용 | 페이로드         |

## REST API를 설계하는데 중요한 것이 있을까요?
REST에서 가장 중요한 기본적인 원칙은 두 가지입니다.  
1. URI는 리소스를 표현하는데 집중해야 한다.
2. 행위에 대한 정의는 HTTP 요청 메서드를 통해 해야 한다.

위 두 규칙이 RESTful API를 설계하는 중심 규칙입니다.   
URI는 리소스를 표현해야 하고, URI는 리소스를 표현하는 데 중점을 두어야 합니다.  
리소스를 식별할 수 있는 이름은 동사보다는 명사를 사용합니다.  
따라서 리소스 이름에 get 같은 행위에 대한 표현이 들어가서는 안 됩니다.  
```
# bad
GET /getTodos/1
GET /todos/show/1

# good
GET /todos/1
```
그 외에도 소문자를 사용해야 하고, 언더바대신 하이픈을 사용하고, uri의 마지막에는 슬래시를 포함하지 않아야하며 계층관계를 나타낼 때는 슬래시 구분자를 사용해야 합니다.  

## HTTP 요청 메서드에 대해서 아는대로 얘기해보세요
| HTTP 요청 메서드 | 종류           | 목적                  | 페이로드 |
| ---------------- | -------------- | --------------------- | -------- |
| GET              | index/retrieve | 모든/특정 리소스 취득 | X        |
| POST             | create         | 리소스 생성           | O        |
| PUT              | replace        | 리소스의 전체 교체    | O        |
| PATCH            | modify         | 리소스 일부 수정      | O        |
| DELETE           | delete         | 모든/특정 리소스 삭제 | X        |

## HTTP 상태 코드를 아는대로 말해주세요
`2XX`
| 상태 코드 | 코드 명 | 의미                                                    |
| --------- | ------- | ------------------------------------------------------- |
| 200       | OK      | 요청이 성공적으로 보내졌음을 의미                       |
| 201       | Created | 요청이 성공적이였으며 새로운 리소스가 생성되었음을 의미 |

`4XX`
| 상태 코드 | 코드 명     | 의미                                                       |
| --------- | ----------- | ---------------------------------------------------------- |
| 400       | Bad Request | 잘못된 문법으로 인하여 서버가 요청을 이해할 수 없음을 의미 |
| 401       | Unathorized | 비인증(Unathorize)된 요청임을 의미                         |
| 403       | Forbidden   | 콘텐츠에 접근할 권리를 가지고 있지 않음을 의미             |
| 404       | Not Found   | 요청받은 리소스를 찾을 수 없음을 의미                      |

`5XX`
| 상태 코드 | 코드 명               | 의미                                  |
| --------- | --------------------- | ------------------------------------- |
| 500       | Internal Server Error | 서버가 처리 방법을 모르는 상황을 의미 |


# Promise

## 콜백이란 뭐라고 생각하나요?
자바스크립트에서 콜백 함수는 다른 함수의 매개변수로 함수를 전달하고, 어떠한 이벤트가 발생한 후 매개변수로 전달한 함수가 다시 호출되는 것을 의미합니다.   
어떤 일을 다른 객체에게 시키고, 그 일이 끝나는 것을 기다리지 않고 끝나고 부를 때까지 다른 일을 하는 것을 말합니다.  
이 떄문에 `동기`가 아닌 `비동기`적으로 처리되는 비동기 방식의 함수라고 할 수 있습니다.  

## 프로미스가 뭔가요?
자바스크립트에서는 비동기 처리를 위한 패턴중 하나로 콜백 함수를 사용합니다.  
전통적인 콜백 패턴은 일명 `콜백 헬`로 인해 가독성이 나쁘고 비동기 처리 중 발생한 에러의 처리가 곤란하며 여러 개의 비동기 처리를 한 번에 처리하는데 한계를 느꼈다.  
프로미스는 ES6에서 도입된, 콜백 함수의 문제점인 비동기 처리를 해결하기 위한 또 하나의 패턴입니다.  
```js
get("/step1", (a)=>{
    get(`/step2/${a}`, (b)=>{
        get(`/step3/${b}`, (c)=>{
            console.log(c);
        })
    })
})
```

## 프로미스 생성 방법
[Promise](https://jsdmas.github.io/js/JS_promises/)  
Promise 생성자 함수를 new 연사자와 함께 호출하면 프로미스(Promise 객체)를 생성합니다.  
ES6에서 도입된 Promise는 호스트 객체가 아닌 ECMAScript 사양에 정의된 표준 빌트인 객체입니다.  
Promise 생성자 함수는  비동기 처리를 수행할 콜백 함수를 인수로 전달받는데 이 콜백 함수는 resolve와 reject 함수를 인수로 전달받습니다.  
```js
const promise = new Promise((resolve, reject)=>{
    if(/* 비동기 처리 성공 */){
        resolve(`result`);
    }else{
        /* 비동기 처리 실패 */
        reject(`failure reason`);
    }
});
```
Promise 생성자 함수가 인수로 전달받은 콜백 함수 내부에서 비동기 처리를 수행합니다.   
이떄 비동기 처리가 성공하면 resolve를, 실패하면 reject를 호출합니다.  
## 프로미스의 상태를 나타내는 것은 어떤 것들이 있나요?
| 프로미스의 상태 정보 | 의미                                  | 상태 변경 조건                  |
| -------------------- | ------------------------------------- | ------------------------------- |
| pending              | 비동기 처리가 아직 수행되지 않은 상태 | 프로미스가 생성된 직후 기본상태 |
| fulfilled            | 비동기 처리가 수행된 상태(성공)       | resolve 함수 호출               |
| reject               | 비동기 처리가 수행된 상태(실패)       | reject 함수 호출                |

생성된 직후 프로미스는 기본적으로 pending 상태입니다.  
이후 비동기 처리가 수행되면 비동기 처리 결과에 따라 다음과 같이 프로미스의 상태가 변경됩니다.  
fulfilled 또는 rejected인 상태를 settled 상태라고 합니다.  
settled 상태는 fulfilled 또는 rejected 상태와 상관없이 pending이 아닌 상태로 비동기 처리가 수행된 상태를 말합니다.  
settled 상태가 되면 더는 다른 상태로 변화할 수 없습니다.  
## 프로미스 빌트인 객체가 제공하는 정적 메서드에 대해 알고 있나요?
- Promise.resolve/ Promise.reject
- Promise.all
- Promise.race
- Promise.allSettled
- Promise.any

# 제너레이터와 async await

## 이터러블과 이터레이터 프로토콜에 대해 설명해주세요.
- [ref](https://inpa.tistory.com/entry/JS-%F0%9F%93%9A-%EC%9D%B4%ED%84%B0%EB%9F%AC%EB%B8%94-%EC%9D%B4%ED%84%B0%EB%A0%88%EC%9D%B4%ED%84%B0-%F0%9F%92%AF%EC%99%84%EB%B2%BD-%EC%9D%B4%ED%95%B4)


### 이터러블
> 이터러블(iterable)이란 자료를 반복할 수 있는 객체를 말하는 것입니다.
우리가 흔히 쓰는 배열 역시 **이터러블 객체**입니다.  

### 이터러블과 이터레이터
> iterable Protocol / iterator Protocol

정의 : 이터러블을 \[for...of], [전개 연산자], \[비구조화].. 등, 이터러블이나 이터레이터 프로토콜을 따르는 연산자들과 함께 동작하도록 하는 약속된 규약을 의미합니다.  
그래서 이터러블이란 이터러블 규약을 따르는 객체인 셈입니다.  

### iterable
정의 : 이터레이터를 리턴하는 \[Symbol.iterator]() 메서드를 가진 객체  
배열의 경우 Array.prototype의 Symbol.iterator 를 상속받기 때문에 이터러블입니다. 문자열도 마찬가지 입니다.  
![](https://github.com/jsdmas/frontend-interview/assets/105098581/9247d80f-e401-4172-ba81-7459780efa43)  

### iterator
정의 : {value : 값, done : true/false} 형태의 이터레이터 객체를 리턴하는 next() 메서드를 가진 객체입니다.  
next 메서드로 순환 할 수 있는 객체입니다.  
\[Symbol.iterator]() 안에 정의되어 있습니다.  
```js
const arr = [1,2,3];
const iter = arr[Symbol.iterator]();
/*
key값을 문자열이 아닌 변수로 주기위해 arr[변수] 형태를 가집니다.
위 사진에서 보듯이, Symbol.iterator 라는 key값을 가지고 value는 함수입니다.
이를 접근해서 함수실행() 시키면 이터레이터 객체가 반환되어 iter에 담기게 됩니다.
*/
iter.next()
// {value:1, done:false}
iter.next()
// {value:2, done:false}
iter.next()
// {value:3, done:false}
iter.next()
// {value:undefined, done:true}
```

![](https://github.com/jsdmas/frontend-interview/assets/105098581/ccfd27f4-823e-4dd5-b93b-2448e1b1fa95)

### \[Symbol.iterator]

이터러블 객체 만들기
```js
let range = {
  from : 1,
  to : 5
}

range[Symbol.iterator] = function(){
  return {
    current : this.from,
    last : this.to,
    next(){
      if(this.current < this.last){
        return { done : false, value : this.current++ };
      }else{
        return { done : true };
      }
    }
  }
}

alert([...range]); // 1, 2, 3, 4, 5
```
#### 무엇이 이터러블 객체이고 무엇이 이터레이터 인가?
- 이터러블 객체는 `range`입니다.
  - 이유는 Symbol.iterator메서드를 가지고 있기 때문입니다.
- 이터레이터 객체는 Symbol.iterator() 메서드에서 리턴한 객체가 바로 `이터레이터` 입니다.
  - 이 객체 안에는 `{value:값, done:true/false}`를 리턴하는 next()메서드가 있기 때문입니다.

![](https://github.com/jsdmas/frontend-interview/assets/105098581/0949f14e-532c-4150-bee8-9ad8d3a4b77d)

#### 위의 예시에서의 for..of 순회
1. for..of가 시작되자마자 for..of는 Symbol.iterator를 호출합니다.
2. 이후 for..of는 반환된 객체(이터레이터)만을 대상으로 동작합니다.
3. for..of에 다음 값이 필요하면, for..of는 이터레이터의 next()메서드를 호출합니다.
4. next()의 반환값은 `{doen: Boolean, value: any}`와 같은 형태여야 합니다.
   - 그래야 순회가 되며 `done=true`는 순회가 종료되었음을 의미합니다.
   - `done=false`는 value에 다음 값이 저장됩니다.

### 한방에 이터러블 + 이터레이터 구현하기
한 객체에 아예 이터레이터 형식을 정의하면, range객체는 이터러블 객체이자 이터레이터 객체 역할을 모두 수행할 수 있습니다.  
표현만 다를뿐 실행자체는 위의 예제와 다를바 없습니다.
```js
let range = {
  from : 1,
  to : 5,
  [Symbol.iterator](){
    this.current = this.from,
    this.last = this.to;
    return this;
  },
  next(){
    if(this.current < this.last){
      return { done:false, value:this.current++ }
    }else{
      return { done:true };
    }
  },
};

for(let num of range){
  alert(num) // 1, 2, 3, 4, 5
}
```

## 제너레이터란 뭔가요? 일반 함수와는 어떤 차이가 있죠?
- [ref](https://inpa.tistory.com/entry/JS-%F0%9F%93%9A-%EC%A0%9C%EB%84%88%EB%A0%88%EC%9D%B4%ED%84%B0-%EC%9D%B4%ED%84%B0%EB%A0%88%EC%9D%B4%ED%84%B0-%EA%B0%95%ED%99%94%ED%8C%90)

> 이터레이터를 리턴하는 함수입니다.
(async가 Promise를 리턴하듯, 제네레이터는 이터레이터를 리턴하는 함수입니다.)  
제네레이터 함수를 사용하면 이터레이션 프로토콜을 준수해 이터러블을 생성하는 방식보다 간편하게 구현할 수 있습니다.  

### 일반 함수와의 차이점
제네레이터 함수는 일반 함수처럼 코드 블록을 한 번에 실행하지 않고 함수 코드 블록의 실행을 일시중지했다가 필요한 시점에 재시작할 수 있는 특수한 함수입니다.  

## 제너레이터의 구조

```js
const range = function* (){
  let i = 0;
  while(true){
    if (i < 5){
      // yield : 생산하다
      // yield를 만나면 일시정지되고, 값을 건내줍니다. 그리고 for..of에 의해 next()가 호출되면 함수 실행을 이어나갑니다.
      yield ++i;
    }else return;
  }
};
for(let i of range()){
  console.log(i); // 1, 2, 3, 4, 5
}
```

```js
let range = {
  from : 1,
  to : 5,
  *[Symbol.iterator]() {
    for(let value = this.from; value <= this.to; value++){
      yield value;
    }
  }
};
alert([...range]); // 1, 2, 3, 4, 5
```


## async/await 가 뭔가요? 기존의 Promise와는 어떤 차이가 있죠?
async / await 는 비동기 작업을 처리하기 위한 문법 중 하나로, Promise를 더 쉽게 사용하기 위한 문법입니다.  
비동기 작업을 처리하는 코드를 보다 간결하게 작성할 수 있습니다.  
`async/await`을 사용하면 `Promise`를 사용하는 것보다 코드가 더 직관적이며, 예외 처리가 더 간편해집니다.   
기존 Promise는 `then, catch`메서드를 사용하였는데 async/await를 사용하면 `try/catch`문을 사용하여 비동기 작업에서 발생할 수 있는 예외를 처리할 수 있습니다.  
```js
async function hello(){
    try{
        const response = await fetch("https://naver.com");
        const data = await response.json();
    }catch(error){
        console.log(error);
    }
}
```
- `async 함수`
  - async 함수는 async 키워드를 사용해 정의하며 언제나 프로미스를 반환합니다.
  - async 함수가 명시적으로 프로미스를 반환하지 않더라도 async 함수는 암묵적으로 반환 값을 resolve 하는 프로미스를 반환합니다.
- `await`
  - 프로미스가 settled 상태(비동기 처리가 수행된 상태)가 될 때까지 대기하다가 settled 상태가 되면 프로미스가 resolve한 처리 결과를 반환합니다.
  - await 키워드는 반드시 프로미스 앞에서 사용해야 합니다.

## Promise와 async/await의 차이점 한 줄 요약
1. 에러 핸들링
   - Promise 를 활용할 시에는 .catch() 문을 통해 에러 핸들링을 해야 하지만,
   - async/await 는 try/catch 를 통해 에러를 처리할 수 있습니다.
2. 코드 가독성
   - Promise의 후속 처리 메서드인 .then() 의 hell의 가능성
   - async/await 는 프로미스의 후속 처리 메서드 없이 마치 동기 처리처럼 프로미스가 처리 결과를 반환하도록 구현할 수 있기 때문에 코드 흐름을 이해 하기 쉽다.


# 에러

## 에러처리를 왜 해야 하나요?
1. 애플리케이션의 안정성과 신뢰성을 향상 시키기위해서
2. 예측할 수 없는 오류 방지
3. 디버깅 및 유지보수 용이성

## 자바스크립트에서 에러를 처리하는 방법에는 뭐가 있을까요?
1. try catch finally
2. Error 객체
3. throw 문

**Error 객체**  
Error 생성자 함수는 에러 객체를 생성합니다.  
Error 생성자 함수에는 에러를 상세히 설명하는 에러 메시지를 인수로 전달할 수 있습니다.  
```js
const error = new Error("invalid");
```
자바스크립트는 Error 생성자 함수를 포함해 7가지의 에러 객체를 생성할 수 있는 Error 생성자 함수를 제공합니다.  
해당 함수가 생성한 에러 객체의 프로토타입은 모두 Error.prototype을 상속받습니다.  
| 생성자 함수    | 인스턴스                                                                      |
| -------------- | ----------------------------------------------------------------------------- |
| Error          | 일반적인 에러 객체                                                            |
| SyntaxError    | 자바스크립트 문법에 맞지 않는 문을 해석할 때 발생하는 에러 객체               |
| ReferenceError | 참조할 수 없는 식별자를 참조했을 때 발생하는 에러 객체                        |
| TypeError      | 피연산자 또는 인수의 데이터 타입이 유효하지 않을 때 발생하는 에러 객체        |
| RangeError     | 숫자값의 허용 범위를 벗어낫을 때 발생하는 에러 객체                           |
| URIError       | encoeURI 또는 decodeURI 함수에 부적절한 인수를 전달했을 때 발생하는 에러 객체 |
| EvalError      | eval 함수에서 발생하는 에러 객체                                              |

**throw 문**  
Error 생성자 함수로 에러 객체를 생성한다고 에러가 발생하는 것은 아닙니다.  
즉, 에러 객체 생성과 에러 발생은 의미가 다릅니다.  
```js
function sum (x, y) {
  if (typeof x !== 'number' || typeof y !== 'number') {
    // Error 객체를 사용하게 되면 해당 콜 스택 정보가 같이 출력되기 떄문에 어디에서 에러가 발생했는지에 대한 정보를 얻을 수 있습니다.
    throw new Error "숫자를 입력하세요"
  }
  return x + y; 
}

console.log(sum("abc", 1))
```
# 모듈

## 모듈이 뭔가요?
모듈(module)이란 애플리케이션을 구성하는 개별적 요소로서 재사용 가능한 코드 조각을 말합니다.  
일반적으로 모듈은 기능을 기준으로 파일 단위로 분리합니다. 이때 모듈이 성립하려면 모듈은 자신만의 파일 스코프(모듈 스코프)를 가질 수 있어야 합니다.  
자신만의 파일 스코프를 갖는 모듈의 자산(모듈에 포함되어 있는 변수, 함수, 객체 등)은 기본적으로 비공개 상태입니다.  
즉, 모듈은 개별적 존재로서 애플리케이션과 분리되어 존재합니다.  
모듈은 공개가 필요한 자산에 한정하여 명시적으로 선택적 공개가 가능한데 이를 `export`
라 합니다.  
공개(export)자산은 다른 모듈에서 재사용 할 수 있습니다. (의존성을 갖게 된다.)   
이때 공개된 모듈의 자산을 사용하는 모듈을 모듈 사용자(module consumer) 라 한다.    모듈 사용자는 모듈이 공개(export)한 자산 중 일부 또는 전체를 선택해 자신의 스코프 내로 불러들여 재사용할 수 있다. 이를 import 라 한다.  
```js
// myModule.js
export function add(a,b){
    return a + b;
};
export const name = "JinHo";

// main.js
import {add, name} from "./myModule.js";
console.log(add(2,1)); // 3
console.log(name); // JinHo
```