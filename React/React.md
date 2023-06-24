# 목차

<details>
<summary>접기 / 펼치기</summary>

- [React](#react)
  - React의 원리, 특징, 장단점이 무엇인가요?
  - state
  - React에서 State를 어떻게 관리하나요?
  - Props에 대해 설명해주세요.
    - ⭐ Props Drilling에 대해 설명해주세요.
    - ⭐ Props Drilling을 어떻게 해결할 수 있나요?
    - ⭐ Key Props를 사용하는 이유에 대해 설명해주세요.
  - 데이터를 자식에서 부모로도 전달할 수 있나요?
  - Props와 State의 차이에 대해 설명해주세요.
  - 왜 state를 직접 바꾸지 않고 setState (useState)를 사용해야 하나요?
  - React 에서 상태 변화가 생겼을 때, 변화를 어떻게 알아채는지에 대해 설명해주세요.
  - React에서 State의 불변성은 어떻게 유지할 수 있나요?
  - setState는 동기적으로 동작하나요? 아니면 비동기적으로 동작하나요?
    - 왜 비동기적으로 동작하나요?
  - HTML과 React의 이벤트 처리 차이점에 대해 설명해주세요.
- [virtual DOM에 대해서 아시나요](#virtual-dom에-대해서-아시나요)
  - Virtual DOM 작동 원리에 대해 설명해주세요.
- [JSX가 뭔가요?](#jsx가-뭔가요)
- 엘리먼트와 컴포넌트의 차이에 대해 설명해주세요.
- 리액트에서 컴포넌트를 어떻게 생성하나요?
- 클래스형 컴포넌트를 사용해보셨나요?
- 함수형 컴포넌트의 장점에 대해 설명해주세요.
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
- Pure Component
- [⭐ Hooks](#⭐-hooks)<span style="color:red">★★</span>
  - useState
  - useEffect
    - ⭐ 함수형 컴포넌트에서 클래스형 컴포넌트의 라이프 사이클 메소드를 비슷하게 사용하는 방법에 대해 설명해주세요.
  - useLayoutEffect
  - useEffect와 useLayoutEffect의 차이점에 대해 설명해주세요.
  - useMemo
  - useCallback
  - useRef
- [useCallback을 사용할 떄와 사용하지 않고 함수를 선언할 때는 어떤 차이가 있나요?](#usecallback을-사용할-떄와-사용하지-않고-함수를-선언할-때는-어떤-차이가-있나요)
- [리액트에서 setState는 비동기 동작인가요 동기 동작인가요?](#리액트에서-setstate는-비동기-동작인가요-동기-동작인가요)
- [리액트의 성능개선 방법에 대해서 설명해주세요](#리액트의-성능개선-방법에-대해서-설명해주세요)
- [컴포넌트에서 이벤트를 실행시키기 위해서는 어떻게 핸들링해야 하나요?](#컴포넌트에서-이벤트를-실행시키기-위해서는-어떻게-핸들링해야-하나요)
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

## State
> state는 react에서 component의 **변경 가능한 데이터**를 의미합니다.
- state는 그냥 javaScript 객체입니다.
- 사전에 미리 정해진 것이 아닌 개발자가 state를 정의합니다.
- 렌더링이나 데이터 흐름에 사용되는 값만 state에 포함시켜야합니다.
  - state가 변경될 경우 component가 재렌더링 되기 떄문
  - 관련없는 값을 포함하면 불필요한 경우 컴포넌트가 재렌더링이 되서 성능저하가 발생한다.
- state는 직접 수정하면 안됩니다.
  - 직접 수정하게되면 개발자가 의도한대로 작동하지 않기떄문입니다.
## React에서 State를 어떻게 관리하나요?

state를 관리하는 이유는
1. 동적인 UI 업데이트
2. 사용자 상호작용 처리
3. 데이터 관리

관리방법은 아래와 같습니다.

- class component
  - `this.state`객체를 사용하여 상태를 초기화합니다.
  - `this.setState()`메서드를 사용하여 상태를 업데이트합니다.
  - `setState`는 이전 상태를 변경하지 않고, 새로운 상태를 생성하는 함수를 전달하는 방식으로 사용합니다. (불변성 유지)
    - 상태를 직접 변경하게 되면 react가 변경 사항을 감지하지 못하고 적절한 렌더링이 이루어지지 않을 수도 있습니다.
- function component
  - `useState`훅을 사용하여 상태를 초기화하고, 배열 형태의 반환값으로 현재 상태와 상태를 업데이트하는 함수를 받습니다.
  - 상태 업데이트 시에는 업데이트 함수를 호출합니다.

## Props에 대해 설명해주세요.

> properties의 줄임말로, 어떠한 값을 컴포넌트에게 전달해줘야 할 떄 props를 사용합니다.

properties : class나 Object의 속성을 나타내는 변수나 상수를 의미합니다.

```jsx
function App(){
  return(
    <Hello name="world" />
  );
}

function Hello(props){
  return(
    <h1>Hello , {props.name}!</h1>
  );
}
```

- 컴포넌트에게 전달되는 props는 파라미터(함수나 클래스의 선언부에 있는 변수)를 통해 조회할 수 있습니다.  
- props는 `객체` 형태로 전달됩니다.

### ⭐ Props Drilling에 대해 설명해주세요.

> props를 오로지 하위 컴포넌트로 전달하는 용도로만 쓰이는 컴포넌트들을 거치면서 React Component 트리의 한 부분에서 다른 부분으로 데이터를 전달하는 과정입니다.

코드를 읽을떄 prop 추적이 힘들어지며 유지보수도 어려워집니다.

### ⭐ Props Drilling을 어떻게 해결할 수 있나요?

1. 전역 상태관리 라이브러리 사용
   - `redux`, `recoil`, `Mobx`, `context API`
2. 컴포넌트 분리

### ⭐ Key Props를 사용하는 이유에 대해 설명해주세요.
> key는 React가 어떤 항목을 변경, 추가 또는 삭제할지 식별하는 것을 돕는 역할을 합니다.
- key는 엘리먼트에 안정적인 고유성을 부여하기 위해 배열 내부의 엘리먼트에 지정해야 합니다.  
- 만약 key props를 부여하지 않는다면 React는 어떤 항목이 변경, 추가, 삭제되었는지 식별하는데 어려움을 겪게 됩니다.
  - 해당 이유로 다시 한번 전체를 리렌더링 하게됩니다.
- 즉, **key props를 주었을 때는 변경된 부분을 식별해 필요한 부분만 리렌더링 해줍니다.**
- **key props를 주지 않는다면 불필요한 리렌더링이 발생하게 됩니다.**

## 데이터를 자식에서 부모로도 전달할 수 있나요?

**콜백 함수**를 통해 가능합니다.  
부모 컴포넌트는 자식 컴포넌트에게 콜백 함수를 props로 전달한 후 자식 컴포넌트는 해당 콜백함수를 호출하여 데이터를 부모 컴포넌트로 전달할 수 있습니다.
```jsx
function ParentComponent(){
  const foo = (data) => {
    console.log(data);
  }
  return(
    <ChildComponent foo={foo}/>
  )
}

function ChildComponent({foo}){
  const [data,setData] = useState(2);
  // 부모 component의 callback함수에 data를 넣는다.
  foo(data);
  return(
    <div>Child</div>
  )
}

```

## Props와 State의 차이에 대해 설명해주세요.

1. React 이벤트 이름은 소문자 대신 camelCase를 사용하여 표시합니다.
2. JSX에 문자열 대신 함수를 전달합니다.

html
```html
<button onclick="activateButton()">클릭하세요</button>
```
React
```jsx
<button onClick={activateButton}>클릭하세요</button>
```

### Props(properties)
- 컴포넌트 외부에서 컴포넌트에 전달되는 데이터입니다.
- 읽기 전용(read-only)이며, 부모 컴포넌트에서 자식 컴포넌트로 전달됩니다.
- 속성이나 설정값으로 사용되며, 컴포넌트 내부에서 변경되지 않습니다.

### State
- 컴포넌트 내부에서 관리되는 데이터입니다.
- 컴포넌트의 상태를 나타내며, 컴포넌트 내부에서 변경 가능합니다.
- 컴포넌트의 동작과 렌더링에 영향을 줍니다.

## 왜 state를 직접 바꾸지 않고 setState (useState)를 사용해야 하나요?

1. 불변성(immutable)유지 : 새로운 상태를 생성하고 업데이트해야 React에서 상태 변경 여부를 판단하고 컴포넌트를 필요한 경우에만 렌더링합니다.
2. 직접 state를 수정하면 react는 render함수를 호출하지 않습니다.

## React 에서 상태 변화가 생겼을 때, 변화를 어떻게 알아채는지에 대해 설명해주세요.

- state 객체의 주소값이 변경되면 상태가 변화되었다는 것을 알아차립니다.(얕은 비교를 통해 상태변화 감지)
- 상태를 업데이트할 떄 `useState` 훅의 setState 함수를 이용하면 react는 내부적으로 이전 상태와 새로운 상태를 비교합니다.
- **react는 이전 상태 객체와 새로운 상태 객체의 주소값을 비교하여 상태의 변화를 감지합니다.**

만약 이전 상태 객체와 새로운 상태 객체의 주소값이 다르다면, React는 상태가 변경되었다고 판단하고 해당 컴포넌트를 리렌더링 합니다.  
이떄, Virtual DOM을 사용하여 실제 DOM과 비교하고, 변경된 부분만 실제 DOM으로 반영합니다.


## React에서 State의 불변성은 어떻게 유지할 수 있나요?

1. useState 훅을 사용하여 상태를 업데이트 합니다.
2. 객체나 배열의 경우 직접 수정하지 않고 새롭게 생성하여 사용합니다.

## setState & useState 는 동기적으로 동작하나요? 아니면 비동기적으로 동작하나요?

> 비동기적으로 동작합니다.

### 왜 비동기적으로 동작하나요?

> 하나의 페이지나 컴포넌트 내에도 수많은 상태값들이 존재합니다. 만약 이 상태가 하나하나 바뀔 때마다 화면을 리렌더링 한다면 문제가 생길수도 있습니다.
> 때문에 리액트는 성능 향상을 위해서 setState를 연속 호출하면 배치 처리하여 한번에 렌더링하도록 하였습니다.
> 아무리 많은 setState가 연속적으로 사용되더라도 배치 처리에 의해서 한 번의 렌더링으로 최신 상태를 유지하는 것입니다.

```jsx
function foo(){
  const [cnt, setCnt] = useState(0);
  return(
    <div>{cnt}</div>
    // setCnt가 아무리 많아도 1씩 증가된다.
    <button onClick={()=>{
      setCnt(cnt + 1);
      setCnt(cnt + 1);
      setCnt(cnt + 1);
      }}>increment</button>
  )
}
```
#### 배치(batch)
> React가 더나은 성능을 위해 여러개의 state 업데이트를 하나의 리렌더링으로 묶는 것을 의미합니다.
> 16ms 동안 변경된 상태 값들을 하나로 묶습니다.

#### 동기적으로 처리하는방법

1. 함수를 인자로 넣기
```jsx
function foo(){
  const [cnt, setCnt] = useState(0);
  return(
    <div>{cnt}</div>
    <button onClick={()=>{
      setCnt(cnt => cnt + 1);
      setCnt(cnt => cnt + 1);
      setCnt(cnt => cnt + 1);
      }}>increment</button>
  )
}
```
2. useEffect의 의존성 배열 사용

```jsx
function foo(){
  const [cnt, setCnt] = useState(0);
  // cnt값이 업데이트 되면 바로 console.log 함수가 실행되므로 업데이트된 state값을 바로 볼 수 있습니다.
  useEffect(()=>{
    console.log(cnt);
  },[cnt]);
  return(
    <div>{cnt}</div>
    <button onClick={()=>{
      setCnt(cnt => cnt + 1);
      }}>increment</button>
  )
}
```


## HTML과 React의 이벤트 처리 차이점에 대해 설명해주세요.


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
JavaScript XML(eXtensible Markup Language)의 약자로, 하나의 JSX파일에 javaScript,HTML을 동시에 작성 가능합니다.(자바스크립트 확장문법)  
**컴포넌트의 구조와 동작을 정의하는데 활용**되며 브라우저에서 실행되기 전에 바벨을 통해 일반적인 javaScript 코드로 변환시켜야 합니다.  
jsx는 아래의 예시와 같이 createElement와 같은 javaScript객체로 변환합니다. (리액트에서 JSX를 쓰는 것이 필수는 아닙니다.)
```jsx
// JSX사용
const element = (
  <h1 className="greeting">
    Hello, World!
  </h1>
)
// JSX사용 X
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, World!'
)
```
## 장점

1. 간결함 & 가독성 향상
2. Injection Attacks 방어 
   - 일반 문자열값이 아닌 소스코드를 입력하여 해당 코드가 실행되도록하는 해킹 방법
   - 기본적으로 React DOM은 렌더링 하기 전 임베딩 된 값을 모두 문자열로 변환합니다.
   - 그렇기 떄문에 명시적으로 선언되지 않은 값은 괄호사이에 들어갈 수 없습니다.

```jsx
const title = response.potentiallyMaliciousInput;
const element = <h1>{title}</h1>;
```

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
- 상태를 직접 변경 가능해서 **가변적(mutable)**입니다.

```jsx
import React from 'react';
class MyComponent extends React.Component {
  render(){
    return <h1>Hello, World!</h1>;
  }
}
```

# 함수형 컴포넌트의 장점에 대해 설명해주세요.

1. 리랜더링 될 떄의 값을 유지합니다. **(불변적 : immutable)**
   - class 컴포넌트는 this가 mutable(변경가능)합니다.
2. 함수형 컴포넌트는 props에 따른 렌더링 결과를 보장받습니다.
   - immutable한 props를 받기 떄문에 결국 렌더링 결과가 보장받습니다.
3. 코드가 간결해지고 가독성이 더 좋습니다.


# React에서 함수 컴포넌트와 클래스 컴포넌트의 차이

## class component
- 객체지향 프로그래밍의 구조를 띄고 있으며, state를 초기화히기 위해서는 construtor(생성자)함수를 필요로 합니다.
- 라이프사이클 API를 사용할 수 있습니다.
- state를 직접 변경가능해서 mutable(가변적)입니다.
- setState 사용 방법이 함수형과 다르게 한번에 변경 가능합니다.

## function component
- 선언하기 좀 더 편하고 메모리 자원을 덜 사용합니다.
- 빌드 파일 크기가 클래스형 컴포넌트보다 더 작습니다.
- 라이프사이클 API 대신 v16.8 업데이트 이후에 적용된 Hooks를 통해 해결되었습니다.
- state를 직접 변경 못해서 immutable(불변적)입니다.
- 변수 각각에 대해 setState함수가 따로 존재합니다.

  
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
- [ref](https://react.vlpt.us/basic/25-lifecycle.html)

| 분류       | 클래스형 컴포넌트      | 함수형 컴포넌트      |
| ---------- | ---------------------- | -------------------- |
| Mounting   | construtor()           | 함수형 컴포넌트 내부 |
| Mounting   | render()               | return()             |
| Mounting   | ComponentDidMount()    | useEffect()          |
| Updating   | componentDidUpdate()   | useEffect()          |
| UnMounting | componentWillUnmount() | useEffect()          |



![](https://github.com/jsdmas/frontend-interview/assets/105098581/535f6731-1c54-42a7-9b38-90b923b2cf4d)
생명주기 메서드(LifeCycle Method)는 컴포넌트가 브라우저상에 나타나고, 업데이트되고, 사라지게 될 떄 호출되는 메서드들 입니다.  
생명주기 메서드는 예전에는 class형 컴포넌트에서만 사용할 수 있었으나 함수형 컴포넌트에서도 사용할 수 있게되었습니다(`useEffect`와 비슷하나 작동방식은 다릅니다).  

### 마운트 (Mount)
아래는 마운트될 때 발생하는 생명주기 입니다.
- constructor
- getDerivedStateFromProps
- render
- componentDidMount

#### constructor
`constructor`는 컴포넌트 생성자 메서드입니다. 컴포넌트가 만들어지면 가장 먼저 실행되는 메서드입니다.  
```js
constructor(props){
  super(props);
  console.log("constructor");
}
```

#### getDerivedStateFromProps
`getDerivedStateFromProps`는 `props`로 받아온 것을 `state`에 넣어주고 싶을 떄 사용합니다.
```js
static getDerivedStateFromProps(nextProps, prevState){
  console.log("getDerivedStateFromProps");
  if(nextProps.color !== prevState.color){
    return { color:nextProps.color };
  }
  return null;
}
```
다른 생명주기 메서드와는 다르게 앞에 `static`을 필요로 하고, 이 안에서는 `this`를 조회 할 수 없습니다.  
여기서 특정 객체를 반환하게 되면 해당 객체 안에 있는 내용들이 컴포넌트의 `state`로 설정이 됩니다.  
반면 `null`을 반환하면 아무 일도 발생하지 않습니다.  
이 메서드는 컴포넌트가 처음 렌더링 되기 전에도 호출 되고, 그 이후 리렌더링 되기 전에도 매번 실행됩니다.

#### render
컴포넌트를 렌더링하는 메서드입니다.

#### componentDidMount
컴포넌트의 첫번쨰 렌더링을 마치고 나면 호출되는 메서드입니다.  
이 메서드가 호출되는 시점에는 우리가 만든 컴포넌트가 화면에 나타난 상태입니다.  
여기서는 주로 D3, masorny 처럼 DOM 을 사용해야하는 외부 라이브러리 연동을 하거나, 해당 컴포넌트에서 필요로하는 데이터를 요청하기 위해 axios, fetch 등을 통하여 ajax 요청을 하거나, DOM 속성을 읽거나 직접 변경하는 작업을 진행합니다.

### 업데이트 (Update)

컴포넌트가 업데이트 되는 시점에의 생명주기 메서드들 입니다.
- getDerivedStateFromProps
- shouldComponentUpdate
- render
- getSnapshotBeforeUpdate
- componentDidUpdate

#### getDerivedStateFromProps
컴포넌트의 props 나 state 가 바뀌었을때도 이 메서드가 호출됩니다.

#### shouldComponentUpdate
`shouldComponentUpdate` 메서드는 컴포넌트가 리렌더링 할지 말지를 결정하는 메서드입니다. (`React.memo`와 역할이 비슷합니다.)
```js
shouldComponentUpdate(nextProps, nextState) {
  console.log("shouldComponentUpdate", nextProps, nextState);
  // 숫자의 마지막 자리가 4면 리렌더링하지 않습니다
  return nextState.number % 10 !== 4;
}
```

#### getSnapshotBeforeUpdate
`getSnapshotBeforeUpdate` 는 컴포넌트에 변화가 일어나기 직전의 DOM 상태를 가져와서 특정 값을 반환하면 그 다음 발생하게 되는 `componentDidUpdate` 함수에서 받아와서 사용을 할 수 있습니다.
```js
 getSnapshotBeforeUpdate(prevProps, prevState) {
    console.log("getSnapshotBeforeUpdate");
    if (prevProps.color !== this.props.color) {
      return this.myRef.style.color;
    }
    return null;
  }
```

#### componentDidUpdate
`componentDidUpdate` 는 리렌더링이 마치고, 화면에 우리가 원하는 변화가 모두 반영되고 난 뒤 호출되는 메서드입니다. 3번째 파라미터로 `getSnapshotBeforeUpdate` 에서 반환한 값을 조회 할 수 있습니다.
```js
componentDidUpdate(prevProps, prevState, snapshot) {
    console.log("componentDidUpdate", prevProps, prevState);
    if (snapshot) {
      console.log("업데이트 되기 직전 색상: ", snapshot);
    }
  }
```

### 언마운트 (UnMount)
컴포넌트가 화면에서 사라지는것을 의미합니다. 

#### componentWillUnmount
`componentWillUnmount` 는 컴포넌트가 화면에서 사라지기 직전에 호출됩니다.


# Pure Component

- React.component는 shouldComponentUpdate를 따로 설정해주지 않은 경우 항상 true를 반환합니다.
  - 즉, `setState`가 실행되면 state, props의 변경 여부를 신경쓰지 않고 무조건적으로 컴포넌트를 업데이트 합니다.
- class형 컴포넌트에서 성능을 개선하기 위해서 최대한 리렌더링을 줄이기 위한 컴포넌트가 `PureComponent`입니다.
- pureComponent는 `shouldComponentUpdate()`안에 `얕은비교`가 적용됩니다.
  - 얕은비교 (shallow-compare)
  - 변수와 문자열에서는 값을 비교합니다.
  - 객체에서는 reference 값을 비교합니다.

# ⭐ Hooks
- Hook은, 클래스를 작성하지 않고도 함수 컴포넌트에서도 상태값과 여러 React의 기능을 사용할 수 있게 해줍니다.
- Hook은 무조건 **최상위 레벨**(react 함수 컴포넌트의 최상위 레벨)에서만 호출해야 합니다.
  - 반복문, 조건문 중첩된 함수 안에서는 호출할 수 없습니다.
  - Hook은 컴포넌트가 렌더링 될 때마다 매번 같은 순서로 호출되어야 합니다.
    - 이렇게 해야 react가 다수의 useState Hook과 useEffect Hook의 호출에서 컴포넌트의 State를 올바르게 관리할 수 있습니다.
- **리액트 함수 컴포넌트에서만** 호출 가능합니다.
- eslint-plugin-react-hooks : 훅의 규칙을 따르는지 아닌지를 판별하여 코딩에 도움을 줍니다.
- 여러 개의 컴포넌트에서 하나의 Custom Hook을 사용할 때 컴포넌트 내부에 있는 모든 state와 effects는 모두 분리되어 있습니다.

```jsx
function Cunter(props){
  let count = 0;
  return (
    <div>
      <p>총 {count}번 클릭했습니다.</p>
      <button onClick={()=> count++}>클릭</button>
    </div>
  )
}
```
위의 코드의 경우 count값을 증가 시킬수는 있지만 reRendering이 일어나지 않아 새로운 count값이 화면에 표시되지 않게 됩니다.  
(react는 컴포넌트의 state나 props의 변경을 추적하여 리렌더링을 수행하기때문)  
위의 경우처럼 함수형 컴포넌트에서 class컴포넌트처럼 기능을 수행하고자 만든 기능이 hook입니다.

## useState
- 가장 기본적인 Hook으로 첫 번쨰 원소는 상태 값, 두 번째 원소는 상태를 설정하는 함수입니다.
- 이 함수에 파라미터를 넣어서 호출하면 전달받은 파라미터로 값이 바뀌고 컴포넌트가 정상적으로 리렌더링 됩니다.

```jsx
import {useState} from "react";
const [value, setvalue] = useState(0);
```

## useEffect 
- side effect(react에서는 효과, 영향)를 수행하기 위한 Hook
- 렌더링이 끝난 이후 실행됩니다.
- class 컴포넌트에서 제공하는 생명주기함수인  componentDidMount, componentDidUpdate,  componentWillUnMount 와 동일한 기능을 하나로 통합하여 제공합니다.

```js
useEffect(이펙트 함수, 의존성 배열); 
```
  
### ⭐ 함수형 컴포넌트에서 클래스형 컴포넌트의 라이프 사이클 메소드를 비슷하게 사용하는 방법에 대해 설명해주세요.

| deps의 값               | 구조                    | 설명                                                                                                 |
| ----------------------- | ----------------------- | ---------------------------------------------------------------------------------------------------- |
| 값이 없을 경우          | useEffect(()=>{})       | 화면이 렌더링 된 이후 수행이 되며, 리 렌더링이 발생하는 경우 다시 수행이 된다.(update될 때마다 수행) |
| 빈 배열 인경우          | useEffect(()=>{},[])    | 화면이 렌더링 된 이후에만 수행이 된다.(mount, unmount)                                               |
| 배열 값이 존재하는 경우 | useEffect(()=>{},\[값]) | 화면이 렌더링 된 이후에 수행이 되고, value가 변경될 경우 해당 메서드가 수행이 된다.                  |


#### useEffect => ComponentDidMount

```jsx
useEffect(()=>{ console.log('Component is mounted'); })
```

#### useEffect => ComponentDidUpdate
data가 변경될 때마다 useEffect 이펙트 함수 실행
```jsx
useEffect(()=>{ console.log('Component is mounted'); }, [data])
```

#### useEffect => ComponentWillUnmount
useEffect return 값으로 함수를 줄떄 ComponentWillUnmount
```jsx
useEffect(()=>{
  console.log('Component is mounted');
  return () => {
      console.log('Component is unmounted');
    };
})
```

## useLayoutEffect
- useEffect와 동일하지만, 렌더링 후 layout과 paint 전에 **동기적**으로 실행됩니다.
- 때문에 설령 DOM을 조작하는 코드가 존재하더라도, 사용자는 깜빡임을 보지 않습니다.

## useEffect와 useLayoutEffect의 차이점에 대해 설명해주세요.

- useEffect
  - 컴포넌트들이 render와 paint된 후 실행됩니다.
  - **비동기적(asynchronus)**으로 실행됩니다.
  - paint된 후 실행되기 때문에 useEffect내부에 dom에 영향을 주는 코드가 있을 경우 사용자 입장에서는 **화면의 깜빡임**을 보게됩니다.
- useLayoutEffect
  - 컴포넌트들이 render된 후 실행되며, 그 이후에 paint됩니다.
  - **동기적(synchrouns)**으로 실행됩니다.
  - paint가 되기 전 실행되기 때문에 dom을 조작하는 코드가 존재하더라도 사용자는 **깜빡임을 경험하지 않습니다.**

## useMemo
- Memoized value를 return 하는 Hook
  - Memoization : 비용이 높거나 연산량이 많은 호출 결과를 저장해두었다가 같은 입력값으로 함수를 호출시 새로 함수를 호출하지 않고 이전에 저장해둔 함수를 반환하는 것
- 리렌더링을 최적화하는데 도움이 됩니다.

```jsx
// Memoized value를 생성하는 create 함수와 의존성 배열을 받는다. 
const memoizedValue = useMemo(
  ()=>{
    // 연산량이 높은 작업을 수행하여 결과를 반환
    return computeExpensiveValue(의존성 변수1, 의존성 변수2);
  },
  [의존성 변수1, 의존성 변수2]
)
```
- useMemo로 전달된 함수는 렌더링이 일어나는 동안 실행됩니다. 
  - 일반적으로 렌더링이 일어나는 동안 실행되선 안되는 작업을 useMemo함수에 넣어선 안됩니다.
  - ex : 서버에서 데이터 받아오기, 수동으로 DOM 변경하기 등
- 의존성 배열을 넣지 않을 경우, 매 렌더링마다 함수가 실행됩니다. 
- 의존성 배열이 빈 배열일 경우, 컴포넌트 마운트 시에만 호출됩니다.

## useCallback
- useMemo와 비슷하지만 값이 아닌 `함수`를 반환합니다. 
- 의존성 배열의 값이 바뀐 경우에만 함수를 새로 정의하고 return 해줍니다.

```jsx
const memoizedCallback = useCallback(
  ()=>{
    doSomething(의존성 변수1, 의존성 변수2)
  },
  [의존성 변수1, 의존성 변수2]
  )
```
- useCallback 함수를 정의하지 않고 컴포넌트 내에 함수를 정의한다면 매번 렌더링이 일어날 때마다 함수가 새로 정의됩니다.

```jsx
function foo(props){
  const [count, setCount] = useState(0);
  // 컴포넌트가 마운트 될 때만 함수가 정의됨
  const handleClick = useCallback((event) => {
    // 클릭 이벤트 처리
  },[]);
  
  return(
    <div>
      <button onClick={()=>setCount(count+1)}>{count}</button>
      <ChildComponent handleClick={handleClick}/>
    </div>
  )
}
```
위의 예시처럼 useCallback 사용시 부모 컴포넌트가 바뀌지 않으면 부모컴포넌트에서 handleClick이벤트를 넘겨줘도 handleClick이 바뀌지 않으면 자식 컴포넌트도 재렌더링이 일어나지 않게됩니다.

## useRef
- javascript에서 DOM요소를 조작하기 위해 querySelector나 getElementById등을 사용했다면, 리액트에서는 useRef 훅 함수를 사용합니다.
- Reference를 사용하기 위한 Hook 
  - Reference : 특정 컴포넌트에 접근할 수 있는 객체
- refObject.current
  - current : 현재 참조하고 있는 Element (변경가능)
  - `.current`프로퍼티를 변경해도 리렌더링을 유발하지는 않습니다. ref객체 안의 값은 리액트 생명주기에 독립적이기 때문입니다.
  - 변경가능한 current라는 속성을 가진 하나의 상자라고 생각하면 편합니다.
- useRef훅은 내부의 데이터가 변경되었을 떄 별도로 알리지 않습니다. (재렌더링 X)

```jsx
function Example(){
    // 초기값이 null인 ref객체 반환 
    const inputEl = useRef(null); // 컴포넌트의 lifeTime 전체에 걸쳐서 유지됩니다. (마운트 해제 전까지 계속 유지)
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
