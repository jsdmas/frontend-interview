# 목차

<details>
<summary>접기 / 펼치기</summary>

- [React](#react)
  - React의 원리, 특징, 장단점이 무엇인가요?
- [virtual DOM에 대해서 아시나요](#virtual-dom에-대해서-아시나요)
  - Virtual DOM 작동 원리에 대해 설명해주세요.
- [JSX가 뭔가요?](#jsx가-뭔가요)
- 엘리먼트와 컴포넌트의 차이에 대해 설명해주세요.
- 리액트에서 컴포넌트를 어떻게 생성하나요?
- 클래스형 컴포넌트를 사용해보셨나요?
- [React에서 함수 컴포넌트와 클래스 컴포넌트의 차이](#react에서-함수-컴포넌트와-클래스-컴포넌트의-차이)<span style="color:red">★★</span>
- [리액트에서 함수형 컴포넌트라고 부르지 않고 함수 컴포넌트라고 부르는 이유가 무엇인가요?](#리액트에서-함수형-컴포넌트라고-부르지-않고-함수-컴포넌트라고-부르는-이유가-무엇인가요)<span style="color:red">★★</span>
- [props와 state의 차이](#props와-state의-차이)<span style="color:red">★★</span>
- [Props가 컴포넌트간에 전달받는 것이라고 했는데 자식에서 부모로도 전달할 수 있는가](#props가-컴포넌트간에-전달받는-것이라고-했는데-자식에서-부모로도-전달할-수-있는가)<span style="color:red">★★</span>
- [FLUX에 대해서 아시나요?](#flux에-대해서-아시나요)<span style="color:red">★★</span>
- [리덕스에 대해서 아시나요?](#리덕스에-대해서-아나요)<span style="color:red">★★</span>
- [리덕스의 기본 원칙은?](#리덕스의-기본-원칙은-뭔가요)<span style="color:red">★★</span>
- [React에서 state의 불변성을 유지하라는 말이 있는데 이에 대해 설명해주세요](#react에서-state의-불변성을-유지하라는-말이-있는데-이에-대해-설명해주세요)<span style="color:red">★★</span>
- [리듀서 내부에서 불변성을 지키는 이유는?](#리듀서-내부에서-불변성을-지키는-이유는)<span style="color:red">★★</span>
- [리액트 사용시에 부수효과로 인해 생기는 문제점이 있다면?](#리액트-사용시에-부수효과로-인해-생기는-문제점이-있다면)<span style="color:red">★★</span>
  - 부수 효과를 일으키는 함수 (불순 함수)
  - 부수 효과를 일으키지 않는 함수 (순수 함수)
  - 요약
- [⭐ 컴포넌트의 라이프 사이클 메서드](#⭐-컴포넌트의-라이프-사이클-메서드)<span style="color:red">★★</span>
  - ⭐ 이해
  - ⭐ 메서드 종류
- [Hooks의 종류](#hooks의-종류)<span style="color:red">★★</span>
  - useState
  - useEffect
  - useMemo
  - useCallback
    - useMemo, useCallback 의 차이점 <span style="color:red">★★</span>
  - useRef
- [useCallback을 사용할 떄와 사용하지 않고 함수를 선언할 때는 어떤 차이가 있나요?](#usecallback을-사용할-떄와-사용하지-않고-함수를-선언할-때는-어떤-차이가-있나요)
- [리액트에서 setState는 비동기 동작인가요 동기 동작인가요?](#리액트에서-setstate는-비동기-동작인가요-동기-동작인가요)
- [리액트의 성능개선 방법에 대해서 설명해주세요](#리액트의-성능개선-방법에-대해서-설명해주세요)
- [컴포넌트에서 이벤트를 실행시키기 위해서는 어떻게 핸들링해야 하나요?](#컴포넌트에서-이벤트를-실행시키기-위해서는-어떻게-핸들링해야-하나요)
- [SPA가 뭔가요](#spa가-뭔가요)
  - SPA의 단점
- [SSR이 뭔가요](#ssr이-뭔가요)
- [CSR이 뭔가요](#csr이-뭔가요)
- [SEO가 뭔가요](#seo가-뭔가요)
  - TTV, TTI

</details>

# React
React는 페이스북에서 개발한 자바스크립트 `라이브러리로`, 사용자 인터페이스를 구축하는 데 사용됩니다.   
`컴포넌트`라고 불리는 작고 고립된 코드의 파편을 이용하여 복잡한 UI를 구성하도록 돕습니다.

## React의 원리, 특징, 장단점이 무엇인가요?

### 원리
- Virtual DOM을 사용하여 실제 DOM과 동기화합니다.
  - 가상 DOM은 메모리에 존재하며, React는 가상DOM을 조작하여 필요한 부분만 실제 DOM에 업데이트 합니다.
  - 이를 통해 DOM 조작이 최소화 되고 효율적인 업데이트가 가능해집니다.
- 컴포넌트 기반 아키텍처
  - React는 UI를 독립적인 컴포넌트로 나누어 개발합니다.
  - 각 컴포넌트는 자체적인 상태(state)와 속성(props)을 가지며, 이들을 조합하여 화면에 구성합니다.
  - 코드 재사용성을 높이고 유지보수를 용이하게 합니다.

### 특징
1. 선언적(Declarative)
   - 리엑트는 선언적 방식으로 UI를 구성합니다. 데이터가 변경되었을 떄 효율적으로 렌더링을 수행할 수 있습니다. 
2. 단방향 데이터 흐름
   - 데이터는 상위 컴포넌트에서 하위 컴포넌트로 props로 전달됩니다.
   - 데이터 흐름이 예측 가능하며 디버깅이 용이해집니다.

### 장단점

- 장점
  - 효율적인 렌더링(Virtual DOM 사용으로 빠른 렌더링 가능)
  - 재사용 가능한 컴포넌트(UI 수정과 재사용성이 높으며, 유지보수 용이)
  - 생태계와 커뮤니티
  - 뛰어난 Garbage Collection, 메모리 관리, 성능을 가짐
    - Garbage Collection : 더 이상 사용되지 않는 메모리를 자동으로 해제하는 기능을 말합니다.
- 단점
  - 복잡한 상태 관리
  - 초기 로딩시간이 길다

# virtual DOM에 대해서 아시나요
- [ref](https://velog.io/@yesbb/virtual-dom%EC%9D%98-%EC%84%B1%EB%8A%A5%EC%9D%B4-%EB%8D%94-%EC%A2%8B%EC%9D%80%EC%9D%B4%EC%9C%A0#prerequisite-)

일반 DOM과 유사한 `객체`를 메모리에 올려놓고, 변경 사항이 생기면 변경된 부분만 업데이트를 해서 반응성이 빠른 웹을 구현할 수 있게 해주는 추상화된 DOM을 뜻합니다.  
결론적으로 DOM을 반복적으로 직접 조작하게 되면 그만큼 브라우저가 렌더링을 자주 하게 되고 PC자원을 많이 소모하게 되는 문제를 해결하기 위한 기술입니다.  

## Virtual DOM 작동 원리에 대해 설명해주세요.
1. UI가 변경되면 전체 UI를 Virtual DOM으로 렌더링한다.
2. 현재 Virtual DOM과 이전 Virtual DOM을 비교해 차이를 계산한다.
3. 변경된 부분을 실제 DOM에 반영한다.

![](https://github.com/jsdmas/frontend-interview/assets/105098581/ad66dc25-74dd-4ba2-b343-8d168ef1d5ba)

# JSX가 뭔가요?
JavaScript XML(eXtensible Markup Language)의 약자로, 하나의 JSX파일에 javaScript,HTML을 동시에 작성 가능합니다.  
**컴포넌트의 구조와 동작을 정의하는데 활용**되며 브라우저에서 실행되기 전에 바벨을 통해 일반적인 javaScript 코드로 변환시켜야 합니다.

# 엘리먼트와 컴포넌트의 차이에 대해 설명해주세요.

## Element
- 태그를 지정하고 불변(Immutable)한 일반 객체입니다.
- React앱의 가장 작은 단위로 화면에 표시할 내용을 기술합니다.
```jsx
const element = <h1>hello</h1>
```
## component

- 독립적으로 동작하며, 자체적인 상태(state)와 속성(props)을 가질 수 있습니다.
- Element를 반환하는 함수 혹은 클래스를 말합니다.

```jsx
const DeleteAccount = () => (
  <div>
    <p>Are you sure?</p>
    <DangerButton>Yep</DangerButton>
    <Button color='blue'>Cancel</Button>
  </div>
);
```

## 차이점

| element                                     | component                                                    |
| ------------------------------------------- | ------------------------------------------------------------ |
| element는 항상 component에 의해 반환됩니다. | component는 기능적/선택적으로 입력을 받고 요소를 반환합니다. |
| element는 method가 없습니다.                | component는 method가 있습니다.                               |
| react element는 DOM노드의 객체 표현입니다.  | component는 DOM트리를 캡슐화 합니다.                         |
| 불변합니다                                  | 상태는 변할수있습니다                                        |

# 리액트에서 컴포넌트를 어떻게 생성하나요?

클래스, 함수형 두가지로 컴포넌트를 생성할 수 있으며 최신 React는 함수형 컴포넌트와 Hooks를 사용하는 것을 권장합니다.

# 클래스형 컴포넌트를 사용해보셨나요?

- ES6의 클래스 문법을 사용하여 컴포넌트를 정의합니다.
- React의 `Component` class를 상속받아 생성합니다.
- `render()`메서드를 구현하여 컴포넌트가 렌더링 할 JSX를 반환합니다.
- 상태(state)를 관리하고, 라이프사이클 메서드를 활용 가능합니다.

```jsx
import React from 'react';
class MyComponent extends React.Component {
  render(){
    return <h1>Hello, World!</h1>;
  }
}
```

# React에서 함수 컴포넌트와 클래스 컴포넌트의 차이

## class component
- 객체지향 프로그래밍의 구조를 띄고 있으며, state를 초기화히기 위해서는 construtor(생성자)함수를 필요로 합니다.
- 라이프사이클 API를 사용할 수 있습니다.

## function component
- 선언하기 좀 더 편하고 메모리 자원을 덜 사용합니다.
- 빌드 파일 크기가 클래스형 컴포넌트보다 더 작습니다.
- 라이프사이클 API 대신 v16.8 업데이트 이후에 적용된 Hooks를 통해 해결되었습니다.

  
기본 구조, state사용법, props 전달받는 법 등의 차이점이 있습니다.

# 리액트에서 함수형 컴포넌트라고 부르지 않고 함수 컴포넌트라고 부르는 이유가 무엇인가요?
원래 react 측에서는 함수형 컴포넌트 라는 단어를 사용했습니다. 하지만 이러한 네이밍이 함수형 프로그래밍과 비슷했고, 혼란을 야기할 수 있었습니다.  
처음 react의 함수형 컴포넌트를 배우는 입장에서는 `함수형 컴포넌트를 사용하면 함수형 프로그래밍이 가능해진다`와 같은 혼란을 줄 수 있었기 때문입니다.  
그러나 우리가 react에서 사용하는 함수 컴포넌트 는 훅(hook)이 들어가고, 이 훅으로 사이드 이펙트 를 빈번히 일으키기 때문에 함수형 프로그래밍이라고 볼 수 없습니다. 함수형 프로그래밍은 순수 함수를 지향하는데, 사이드 이펙트를 빈번히 일으키는 리액트의 함수 컴포넌트가 함수형 컴포넌트로 보기는 어렵다는 것입니다.  

# props와 state의 차이
- props : 부모 컴포넌트에서 자식 컴포넌트로 상속하는 데이터 값으로 읽기 전용 데이터입니다.
- state : 컴포넌트에서 사용하고 관리할 수 있는 상태값입니다. 

# Props가 컴포넌트간에 전달받는 것이라고 했는데 자식에서 부모로도 전달할 수 있는가?
1. 부모 컴포넌트에서 설정할 수 있으며 부모에서 자식으로만 데이터를 줄 수 있습니다.
   - 자식이 props를 통해 부모에게 데이터를 줄 수 없다는 뜻입니다.
2. 하지만 부모 컴포넌트로 부터 해당 state를 번경하는 setState 함수를 props로 전달받아 해당 함수를 호출하면 props 값을 변경할 수 있습니다.


# FLUX에 대해서 아시나요?
`MVC`패턴은 Model-View-Controller의 약자로, 애플리케이션을 구성하는 디자인 패턴입니다. MVC 패턴의 컨트롤러(Controller)는 모델(Model)의 데이터를 조회하거나 업데이트하는 역할을 하며, 모델(Model)의 변화는 뷰(View)에 반영됩니다.  

반면 Flux 패턴은 사용자 입력을 기반으로 Action을 만들고 Action을 Dispatcher에 전달하여 Store (Model)의 데이터를 변경한 뒤 View에 반영하는 단방향의 흐름으로 애플리케이션을 만드는 아키텍쳐입니다.  
Flux 패턴은 facebook에서 MVC의 문제를 해결할 목적으로 고안되었습니다.
# 리덕스에 대해서 아나요?
리덕스는 상태관리 라이브러리 중 하나로 여러 가지 상태관리 라이브러리 중 가장 많이 사용되고 있습니다.  
리덕스는 store(스토어)라는 변수를 이용하여 전역 상태관리를 하게 됩니다.  
전역으로 상태를 관리하기 때문에 props <-> state를 통해 부모 컴포넌트에서 자식 컴포넌트로, 자식의 자식 컴포넌트로 내려주지 않아도 사용할 수 있습니다.  

# 리덕스의 기본 원칙은 뭔가요?
1. 응용 프로그램의 전역 상태는 단일 저장소 내의 트리에 저장됩니다
2. 상태(state)는 읽기 전용입니다.
3. 순수 함수에 의해서 변경되어야 합니다.

# React에서 state의 불변성을 유지하라는 말이 있는데 이에 대해 설명해주세요
- 이는 메모리 영역에서의 직접적인 변경이 불가능 하다는 뜻입니다.
- 즉, state의 메모리 영역 값을 직접적으로 변경하더라도 React는 이전 값과 이후에 값에 대한 얕은 비교를 하기 때문에 state가 변경되었다고 인지하지 못합니다.
- state를 직접 수정할 경우 컴포넌트에서 render 메서드를 호출하지 않아 화면에 변경된 값이 랜더링 되지 않습니다.
# 리듀서 내부에서 불변성을 지키는 이유는?
각각의 고유한 참조값을 가지는 객체를 복사해서 사용함으로써 어떤 함수가 호출됐을 떄 같은 객체를 참조한다면 생길 수 있는 불필요한 리렌더링과 부수효과를 줄일 수 있습니다.
# 리액트 사용시에 부수효과로 인해 생기는 문제점이 있다면?

## 부수 효과를 일으키는 함수 (불순 함수)
함수 외부의 상태를 변경하거나 함수 외부와 상호작용 하는 함수를 말합니다. 예를 들어 전역 변수의 값을 변경하거나 콘솔에 출력하는 것이 있습니다.
```js
let x = 0;
function incrementX(){
    x++;
    console.log(x);
}
incrementX();
incrementX();
```
## 부수 효과를 일으키지 않는 함수 (순수 함수)
함수 외부의 상태를 변경하지 않고 함수 외부와 상호작용하지 않는 함수를 말합니다. 이러한 함수는 입력값에만 의존하여 결과값을 반환하며, 같은 입력값에 대해서 항상 같은 결과값을 반환합니다.
```js
function add(a,b){
    return a+ b;
}
console.log(add(1,2));
```

## 요약
- React state는 직접 조작을 피하는 방식으로 부수효과를 방지합니다.
- state, props가 변경될 때 리렌더링이 되기 때문에 의도치 않게 부수효과를 가진 함수들로 인해 불필요한 리렌더링이 잦아질 수 있습니다.
- Redux의 reducer는 순수함수여야만 하는데, store값을 변경하는 함수가 부수효과를 동반하지 않아야 store 내부의 값들이 안전하게 보호될 수 있기 때문입니다.


# ⭐ 컴포넌트의 라이프 사이클 메서드

## 이해
React 컴포넌트의 라이프 사이클 메서드는 컴포넌트가 생성되고 업데이트되며 소멸하는 과정에서 발생하는 일련의 이벤트입니다.  
이러한 이벤트는 다음과 같습니다.
1. 마운팅 (DOM에 노드 추가)
2. 업데이트 (DOM의 기존 노드 변경)
3. 언마운팅(DOM에서 노드 제거)
4. 에러 처리(코드가 작동하고 버그가 없는지 확인)

컴포넌트는 다음과 같은 경우에 업데이트합니다.
- Props가 바뀔 떄
- state가 바뀔 떄
- 부모 컴포넌트가 리렌더링 될 떄 등등
## ⭐ 메서드 종류
1. render : 컴포넌트가 화면에 표시될 내용을 결정
2. componentDidupdate : 컴포넌트가 업데이트될 떄 호출
3. componentWillUnmount : 컴포넌트가 제거될 때 호출
4. componentDidMount : 컴포넌트가 웹 브라우저상에 나타난 후 호출하는 메서드

# Hooks의 종류
Hook은 React 버전 16.8부터 새로 추가된 기능으로, 클래스를 작성하지 않고도 상태값과 여러 React의 기능을 사용할 수 있게 해줍니다.
## useState
- 가장 기본적인 Hook으로 첫 번쨰 원소는 상태 값, 두 번째 원소는 상태를 설정하는 함수입니다.
- 이 함수에 파라미터를 넣어서 호출하면 전달받은 파라미터로 값이 바뀌고 컴포넌트가 정상적으로 리렌더링 됩니다.

```jsx
import {useState} from "react";
const [value, setvalue] = useState(0);
```

## useEffect
- 리액트 컴포넌트가 렌더링될 떄마다 특정 작업을 수행하도록 설정할 수 있는 Hook입니다.
- 기본적으로 렌더링되고 난 직후마다 실행되며 두 번째 파라미터 배열에 무엇을 넣는지에 따라 실행되는 조건이 달라집니다.


```jsx
// 마운트만 실행
useEffect(()=>{
    console.log(`마운트될 때만 실행됨`);
},[]);
// 특정 값 업데이트될 때만 실행
useEffect(()=>{
    console.log(name);
},[name]);
```
## useMemo
연산의 결과값을 저장해두고 동일한 연산이 반복될 때 이전에 저장된 값을 재사용하는 것입니다.  
이를 통해 리렌더링을 최적화하는데 도움이 됩니다.  
```jsx
import React, {useMemo} from "react";
function Example({ a, b }){
    const memoizedValue = useMemo(()=>{
        // caclulation
        return a+ b;
    }, [a, b]);
    return <div>{memoizedValue}</div>
}
```
위의 예제는 useMemo가 a + b 라는 연산의 결과값을 저장하고 있습니다.  
a or b 의 값이 변경되지 않으면 이전에 저장된 값을 재사용하게 됩니다.  

## useCallback
useMemo와 상당히 비슷한 함수로, 주로 렌더링 성능을 최적화 해야하는 상황에서 사용합니다.  
만들어 놨던 함수를 재사용 할 수 있습니다.  
useMemo는 값을 메모이제이션하고 useCallback은 함수를 메모이제이션합니다.  
```jsx
import React, {useCallback} from "react";
function Example({ onClick }){
    const memoizedOnClick = useCallback(()=>{
        onClick();
    }, [onClick]);
    return <button onClick={memoizedOnClick}>Click</button>;
}
```
## useRef
- javascript에서 DOM요소를 조작하기 위해 querySelector나 getElementById등을 사용했다면, 리액트에서는 useRef 훅 함수를 사용합니다.
- useRef는 `.current`프로퍼티에 변경가능한 값을 담고있는 객체입니다.
- `.current`프로퍼티를 변경해도 리렌더링을 유발하지는 않습니다. ref객체 안의 값은 리액트 생명주기에 독립적이기 때문입니다.  

```jsx
function Example(){
    const inputEl = useRef(null);
    const handleClick = () => {
        inputEl.current.focus();
    };
    return(
        <>
            <input ref={inputEl} type="text" />
            <button onClick={handleCilck}>Focus the input</button>
        </>
    );
}
```
# useCallback을 사용할 떄와 사용하지 않고 함수를 선언할 때는 어떤 차이가 있나요?
함수를 선언할 때 `useCallback`을 사용하지 않으면 매번 컴포넌트가 리렌더링 될때마다 함수가 새로 생성됩니다.  
반면에 `useCallback`을 사용하면 의존성 배열 안의 값이 변경되지 않는 한 함수를 재사용 할 수 있습니다.  

# 리액트에서 setState는 비동기 동작인가요 동기 동작인가요?
- 리액트 라이브러리는 state를 다시 설정하는 함수인 setState를 비동기 함수로 처리해서 컴포넌트 내의 비동기 함수를 처리하는 콜백큐가 다 비워지면 리렌더링하도록 설계했습니다.
- 함수 내에서 동기적으로 실행되는 함수가 모두 실행된 뒤에 마지막에 setState를 처리합니다.  
```js
const onCLickBtn = () =>{
    console.log("before", count); // 동기함수
    setCount((value) => value + 1); // 비동기함수
    console.log("after", count); // 동기함수
} 
```
# 리액트의 성능개선 방법에 대해서 설명해주세요
- 객체 타입 state는 최대한 분할하여 선언
- React.memo를 통한 컴포넌트 memoiztion
- useMemo를 통한 함수 반환 연산값 재사용
- useCallback을 통한 함수 재생성 및 리렌터링 방지
- 코드 스플리팅 (react.lazy())
- event, onChange에 throttle, debounce 적용
- 이미지 사이즈 최적화
- react-query로 api data 캐싱

# 컴포넌트에서 이벤트를 실행시키기 위해서는 어떻게 핸들링해야 하나요?
이벤트로 설정할 함수를 호출하는 것이 아닌 직접 넣어 줄 때는 화살표 함수 문법을 사용하여 넣어 주어야 합니다.

```jsx
// 작동하지 않음
<button onClick={this.setState({ number: number + 1})}>  (x)
// 작동함
<button onClick={()=> this.setState({ number: number + 1}; )}>  (o)
// or
const plusNum = (number) => {
  setState(number : number + 1);
}
...
<button onClick={plusNum}>+ 1 </button>
```

# SPA가 뭔가요?
Single Page Application의 약자입니다.  
기존 웹 서비스는 요청시마다 서버로부터 리소스들과 데이터를 해석하고 화면에 렌더링하는 방식이었습니다. SPA 형태는 브라우저에 최초에 한번 페이지 전체를 로드하고, 이후부터는 특정 부분만 Ajax를 통해 데이터를 바인딩하는 방식입니다.  

## SPA의 장단점
- 장점
  - 전체 페이지를 업데이트 할 필요가 없기 때문에 빠르고 `깜빡`거림이 없어 자연스러운 사용자 경험을 줄 수 있습니다.
  - 필요한 리소스만 부분적으로 로딩하여 성능이 좋습니다.

- 단점
  - 초기 구동 속도가 느리다는 점이 있습니다.
  - SPA는 초기에 웹에 필요한 대부분의 리소스를 다운로드하기 때문입니다.
  - 검색엔진 최적화의 단점도 존재합니다.

# SSR이 뭔가요
Sever Side Rendering 의 약자로 서버쪽에서 렌더링 준비를 끝마친 상태로 클라이언트에 전달하는 방식입니다.  
SSR은 서버로부터 완전하게 만들어진 HTML파일을 받아와 페이지 전체를 렌더링하는 방식으로 Multi page application은 SSR 방식을 채택합니다.  
SSR을 사용하는 가장 큰 이유는 효율적인 SEO를 위해서 입니다.  

# CSR이 뭔가요
Client Side Rendering의 약자로 클라이언트 쪽에서 렌더링을 수행하는 방식입니다.  
CSR은 서버로부터 데이터만 받아와서 클라이언트 쪽에서 JavaScript를 이용해 동적으로 렌더링하는 방식입니다. SPA(Single Page Application)는 CSR 방식을 채택합니다.  

# SEO가 뭔가요
SEO란 Search Engin Optimiztion의 약자로 구글, 네이버와 같은 검색 엔진들이 서버에 등록된 웹사이트를 하나하나씩 돌아 다니면서 웹사이트의 HTML 문서를 분석해줍니다.  
이때 HTML 에 사용된 태그를 바탕으로 사용자가 검색할 때 웹사이트를 빠르게 검색할 수 있게 도와줍니다.  
SSR은 서버에서 완전한 HTML 파일을 생성하여 클라이언트에 전달하기 떄문에 검색엔진이 쉽게 페이지의 내용을 수집할 수 있습니다. 반면 CSR은 클라이언트 쪽에서 JavaScript를 이용해 동적으로 렌더링하기 떄문에 검색엔진이 페이지의 내용을 수집하는 데 어려움이 있을 수 있습니다.
## TTV, TTI
> TTV는 보여지는 시점(Time To View), TTI는 인터렉션 사용자와의 통신이 가능해지는 시점 (Time To Interact)입니다.

CSR은 사용자에게 보여짐과 동시에 모든 html과 js를 불러온 상태이기 때문에, TTV과 됨과 동시에 TTI 모든 동적인 행동을 할 수 있게 됩니다.  
하지만 SSR은 html과 일부 js파일은 서버로부터 사전에 받아 놓았기 때문에 TTV 상태에서도 TTI가 전부 활성화되어 있지는 않습니다.  

요즘에는 SSR, CSR 뿐만 아니라 SSG(Static Site Generation)또한 렌더링 방법으로 등장하였습니다. SSG는 리액트를 예로 들면 `Gatsby`또는 `Next`와 같은 라이브러리를 추가적으로 사용하여 렌더링을 하는 것인데, 웹 페이지를 정적으로 미리 생성해두고, 서버에 배포해놓는 것입니다.  
SSG에서도 자바스크립트 파일을 html파일과 함께 가지고 있을 수 있기 때문에, 동적인 요소도 충분히 추가할 수 있습니다. Next 에서는 ssr 뿐만 아니라, static generation, no pre-rendering, pre-rendering상태를 모두 지원하기 때문에 리액트로 작업을 계속한다면 next.js를 배워보는 것도 매우 효과적일 겁니다.  
