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
- [DOM](#dom)
    - DOM이 뭔가요?
    - DOM을 구성하는 건 뭐가 있을까요?
- [이벤트](#이벤트)
    - 마우스 이벤트 타입에는 뭐가 있나요? click 말고 클릭을 대체할 수 있는 이벤트가 있나요?
    - 그 외에 알고있는 대표적인 이벤트가 있나요?
    - 이벤트 핸들러를 등록하는 방식에는 어떤 것들이 있나요?
    - 이벤트 전파(propagation)에 대해서 알고 있나요?
    - <span style="color: red">이벤트 위임(delegation)에 대해서 알고있나요?</span>
    - e.preventDefault 에 대해 알고 있나요?
    - e.stopPropagation
- [타이머](#타이머)
    - 호출 스케쥴링이 무엇인가요?
    - 타이머 함수에는 어떤 것들이 있나요?
    - 이벤트가 과도하게 호출되어 성능에 문제를 일으킬 경우에 할 수 있는 어떤 일을 통해 해결 할 수 있나요?
    - 디바운스에 대해서 알고 있나요?
    - 쓰로틀에 대해서 알고 있나요?
- [비동기 프로그래밍](#비동기-프로그래밍)
    - <span style="color: red">동기와 비동기의 차이점에 대해서 설명해줄 수 있나요?</span>
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

## 이벤트 전파(propagation)에 대해서 알고 있나요?
DOM 트리상에 존재하는 모든 DOM 요소 노드에서 발생한 이벤트는 DOM 트리를 통해 전파됩니다. 이를 이벤트 전파라고 합니다.  
사용자의 다양한 입력을 통해 동적으로 생성되는 이벤트 객체는 이벤트를 발생시킨 타깃(target)을 중심으로 DOM 트리를 통해 전파됩니다.  
전파되는 방향에 따라 3단계로 구분할 수 있습니다.
- 캡처링 단계 : 이벤트가 상위 요소에서 하위 요소 방향으로 전파
- 타깃 단계 : 이벤트가 이벤트 타깃에 도달
- 버블링 단계 : 이벤트가 하위 요소에서 상위 요소 방향으로 전파

![image](https://user-images.githubusercontent.com/105098581/223305964-dba25922-da51-44c0-98a9-6224f37f1d29.png)

브라우저는 기본적으로 이벤트 버블링 단계에서 이벤트를 캐치합니다.  
```html
<html>
    <head>
        <meta charset="UTF-8"/>
        <title>hello</title>
        <body>
            <div>click</div>
        </body>
        <script>
            const html = document.querySelector("html");
            const body = document.querySelector("body");
            const div = document.querySelector("div");

            html.addEventListener("click", ()=> console.log("HTML"));
            html.addEventListener("click", ()=> console.log("BODY"));
            html.addEventListener("click", ()=> console.log("DIV"));
        </script>
    </head>
</html>
```
div 클릭시
```
DIV
BODY
HTML
```
![image](https://user-images.githubusercontent.com/105098581/223307152-a2bd7f4f-0df2-465b-aa68-e40b3f0c408c.png)  
이벤트 캡처링 단계라면 HTML > BODY > DIV 순으로 상위 노드에서 하위 노드로 내려오며 이벤트를 캐치할 것입니다.  
하지만 브라우저는 기본적으로 이벤트 버블링 단계인 우리가 클릭하고자 한 이벤트 객체인 타깃인`<div>`에 도달한 후 다시 해당 하위 노드에서 상위 노드로 돌아가는 과정에서 이벤트를 캐치 합니다.   
addEventListener 메서드의 세번째 인수(argument)로 옵션인[, useCaputure]자리에 boolean 값인 true를 넣어준다면, 캡처링 단계에서도 이벤트 객체를 캐치할 수 있습니다.  
기본값은 false로, 버블링 단계에서 이벤트 객체를 캐치합니다.

```js
html.addEventListener("click", ()=> console.log("HTML"), true);
html.addEventListener("click", ()=> console.log("BODY"), true);
html.addEventListener("click", ()=> console.log("DIV"));

>>>
HTML
BODY
DIV
```

## 이벤트 위임(delegation)에 대해서 알고있나요?
연속되는 태그에 대해서 공통적으로 이벤트를 줘야할 떄 우리가 이벤트 핸들러를 바인딩할 해당 요소의 부모요소에게 이를 위임하여 이벤트를 진행하는 것 을 이벤트 위임(event delegation) 이라 합니다.  
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

## 동기와 비동기의 차이점에 대해서 설명해줄 수 있나요?
- 현재 실행 중인 태스크가 종료될 떄까지 다음에 실행될 태스크가 대기하는 방식을 동기(synchronous) 처리 방식이라고 합니다.
- 현재 실행 중인 태스크가 종료되지 않은 상태라 해도 다음 태스크를 곧바로 실행하는 방식 을 비동기(asynchronous) 처리라고 합니다.
- 대표적으로 타이머 함수인 **setTimeout / setInterval , HTTP 요청, 이벤트 핸들러**는 비동기 처리 방식으로 동작합니다.

- 자바스크립트 엔진은 한 번에 하나의 태스크(작업, 일)만 실행할 수 있는 싱글 스레드 방식으로 동작합니다.   
- 이는 자바스크립트 엔진이 단일 호출 스택(call stack)을 사용하여 코드 실행 순서를 관리하기 떄문입니다.  
- call stack은 현재 실행 중인 함수의 모음으로, 함수가 호출되면 해당 함수의 실행 컨텍스트가 스택에 push 되고, 함수 실행이 완료되면 스택에서 pop 됩니다.
  - 호출 스택은 Last-In-First-Out(LIFO)구조를 가지므로, 가장 마지막에 추가된 함수가 가장 먼저 실행되고, 가장 처음에 추가된 함수가 가장 마지막에 실행됩니다.
- 싱글 스레드 방식은 한 번에 하나의 태스크만 실행할 수 있기 때문에 처리에 시간이 걸리는 태스크를 실행하는 경우 블로킹(작업중단)이 발생합니다.  
- 이러한 문제를 해결하기 위해 비동기 처리 방식과 이벤트 루프(Event Loop)를 사용하여 작업을 분리하고 병렬로 처리하는 기법이 사용됩니다.

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

## XMLHttpRequest와 fetch 메서드의 차이는 무엇이라고 생각하시나요?

# REST API

## REST API가 뭔가요?

## REST API의 구성은 어떤 것이 있나요?

## REST API를 설계하는데 중요한 것이 있을까요?

## HTTP 요청 메서드에 대해서 아는대로 얘기해보세요

## HTTP 상태 코드를 아는대로 말해주세요

# Prommise

## 콜백이란 뭐라고 생각하나요?

## 프로미스가 뭔가요?

## 프로미스 생성 방법

## 프로미스의 상태를 나타내는 것은 어떤 것들이 있나요?

## 프로미스 빌트인 객체가 제공하는 정적 메서드에 대해 알고 있나요?

# 제네레이터와 async await

## 제네레이터란 뭔가요? 일반 함수와는 어떤 차이가 있죠?

## 제네레이터의 구조

## async/await 가 뭔가요? 기존의 Promise와는 어떤 차이가 있죠?


## Promise와 async/await의 차이점 한 줄 요약

# 에러

## 에러처리를 왜 해야 하나요?

## 자바스크립트에서 에러를 처리하는 방법에는 뭐가 있을까요?

# 모듈

## 모듈이 뭔가요?


