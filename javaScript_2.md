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
`클로저는 자신이 선언될 당시의 환경을 기억하는 함수입니다.`  
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
**클로저는 상태(state)를 안전하게 변경하고 유지하기 위해 사용합니다.**   
다시 말해, 상태가 의도치 않게 변경되지 않도록 상태를 안전하게 은닉(information hiding)하고 특정 함수에게만 상태변경을 허용하기 위해 사용합니다.  

## 클로저를 어떻게 생성하나요?
클로저를 생성하는 가장 일반적인 방법은 함수 내부에서 새로운 함수를 정의하고, 그 함수를 반환하는 것입니다. 반환된 함수는 자신이 생성된 렉시컬 스코프에서 선언된 변수를 계속해서 참조할 수 있습니다.
```js
function makeAdder(x){
    return function(y){
        return x + y;
    };
}
// makeAdder 함수가 실행되어 반환된 함수를 add5 변수에 할당합니다.
const add5 = makeAdder(5); 
console.log(add5(3)); // 8
consoel.log(add5(7)); // 12
```


# 클래스

## 자바스크립트에서 클래스가 생기기 전에는 어떤 방식으로 객체지향 패턴을 구현했나요?

## 그럼 생성자 함수와 클래스는 어떤 차이가 있나요?

## 클래스의 정의

## 클래스의 상속

# 스프레드 문법

## Spread 문법이 뭔가요?

## 어떤 상황에서 사용할 수 있죠?

# 구조 분해 할당

## 구조 분해 할당이 뭔가요?

## 구조 분해 할당은 크게 어떤 종류가 있나요?

# 브라우저 랜더링 과정

## 브라우저의 렌더링 과정에 대해 설명해보세요

## 브라우저의 렌더링 과정에 자바스크립트는 어떻게 동작하나요?

## script 태그를 body 태그 밑에 둬야하는 이유가 있을까요?
