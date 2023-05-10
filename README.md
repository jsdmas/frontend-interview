# 프론트엔드 지식 & 면접질문 정리

## 목차

- [소개](#-소개)
- [Computer Sience](#computer-sience)
- [algorithm](#algorithm)
- [HTML/CSS](#htmlcss)
- [JavaScript](#JavaScript_정리1)
- [JavaScript2](#JavaScript_정리2)
- [React](#react)
- [TypeScript](#typescript)
- [참고](#참고)

## 🌱 소개
프론트엔드로 취업 전 알아야 하는 기본적인 지식들을 정리해봤습니다. 구글링 & 깃허브를 활용하여 다른사람들이 쓴 글을 참고하고 직접 정리하였습니다.   

✅ 개인적으로 정리한 내용이라 틀린내용이 있을 수 있습니다.   
## [Computer Sience](./computerSience.md)

- 프로세스와 스레드
  - 프로세스가 뭔가요?
  - 스레드가 뭔가요?
  - 프로세스와 스레드는 어떤 차이가 있나요?
- 싱글 스레드와 멀티 스레드
  - 싱글 스레드 장점
  - 싱글 스레드 단점
  - 멀티 스레드 장점
  - 멀티 스레드 단점
- HTTP
  - HTTP란 뭔가요?
  - HTTP 프로토콜의 가장 큰 특징은 뭔가요?
  - URL은 뭔가요?
  - HTTP/1.1 과 HTTP/2.0의 차이는 뭔가요?
  - HTTPS는 HTTP랑 뭐가 다른가요?
  - 심화) 공개키 (비대칭키) 방식이 뭔가요?
- 쿠키, 세션
  - 쿠키, 세션을 왜 쓰나요?
  - 쿠키가 뭔가요?
  - 세션이 뭔가요?
  - 쿠키와 세션의 차이는 어떤 점이 있을까요?
- CORS
  - CORS가 뭔가요?
  - CORS를 겪고 직접 해결해 본 경험이 있으면 말해주세요
- SaaS
  - Saas가 뭔가요?
  - 기타 비즈니스 유형은 뭐가 있나요?
- 개발 방법론
  - 폭포수 방법론이란 뭔가요?
  - 애자일 방법론이란 뭔가요?
- Cache
- 캐시란 무엇인가요?
- CI CD
  - CI CD란 뭔가요?
- CDN
  - CDN이란 뭔가요?
- 테스트
  - 테스트란 무엇인가요?
  - 테스트의 예는 어떤 것들이 있나요?
  - 테스트는 왜 해야 하나요?
  - 유닛 테스트란 무엇인가요?
  - 통합 테스트란 무엇인가요?
  - E2E 테스트란 무엇인가요?
- business logic
  - business logic 이란 무엇인가요?
- Snippet
  - snippet 이란 무엇인가요?
- 웹팩
  - 웹팩이란?
  - 모듈이란?
  - 모듈 번들링이란?
  - 웹팩이 등장한 이유 웹팩 사용 시에 이점
  - 바벨이란?
  - 웹팩의 주요 속성 4가지

## [algorithm](./algorithm/)

## [HTML/CSS](./html_css.md)

### HTML
- DOCTYPE
- meta tag
- 웹 표준 및 웹 접근성
- img 처리방식
- SVG란?
- css link, javascript script

### CSS
- display
- position
- Felxbox, Grid
- 반응형웹과 적응형웹
- PX, EM
- CSS 적용 우선순위
- CSS-in-JS
- CSS 전처리기(CSS preprocessors)

## [JavaScript_정리1](./javaScript/javaScript.md)

- 프로그래밍
  - 프로그래밍이란 뭐라고 생각하나요?
  - <span style="color: red">컴파일러는 뭐고 인터프리터는 뭔가요?</span>
- JavaScript가 뭔가요?
    - javaScript의 특징
- 변수
    - 변수란 무엇인가요?
    - <span style="color: red">식별자가 무엇인가요?</span>
    - 변수를 선언한다는 것은 어떤 것을 의미하나요?
    - var 키워드는 뭔가요?
    - <span style="color: red">호이스팅이 뭔가요?</span>
    - <span style="color: red">var 키워드의 문제점은 무엇인가요?</span>
    - <span style="color: red">let 키워드는 var 키워드와 어떤 점이 다른가요?</span>
    - <span style="color: red">TDZ</span>
    - <span style="color: red">const 키워드는 어떤 특징이 있나요?</span>
    - 식별자 네이밍 규칙은 어떤 것들이 있나요?
    - 네이밍 컨벤션은 어떤 것들이 있나요?
    - 리터럴이 뭔가요?
- 데이터 타입
    - <span style="color: red">데이터 타입의 종류는 어떤 것들이 있나요?</span>
    - 심벌 타입이 뭔가요?
    - <span style="color: red">데이터 타입은 왜 필요한가요?</span>
    - 기본형과 참조형의 가장 큰 차이가 무엇인가요?
    - 상수와 불변의 차이는 무엇인가요?
    - 불변성이 왜 필요할까요?
    - 얕은 복사와 깊은 복사의 차이는 무엇일까요?
    - undefined와 null의 차이는 뭔가요?
    - 동등 연산자(==)와 일치 연산자(===)의 차이는 무엇일까요?
    - 부동 소수점 계산
    - 일치 연산자의 예외 케이스는 어떤 경우가 있을까요? 이 경우 어떻게 해결할까요?
    - NaN은 뭔가요?
    - Number.isNaN과 window.isNaN의 차이는 뭔가요?
    - 정적 타이핑이 뭔가요?
    - 동적 타이핑이 뭔가요?
- 타입변환과 단축 평가
    - 명시적 타입 변환이 뭔가요?
    - 명시적 타입 변환 함수를 예를 들어볼 수 있나요?
    - 암묵적 타입 변환이 뭔가요?
    - truthy / falsy 한 값이 뭔가요?
- 배열
    - 자바스크립트의 배열은 자료구조의 배열과 같나요?
    - 배열의 메서드는 어떤 종류가 있나요?
    - 고차 함수에 대해서 아시나요?
    - forEach 메서드와 map 메서드의 차이점에 대해 알고 있나요?
- 객체 리터럴
    - 자바스크립트에서 객체란 뭔가요?
    - 함수와 메서드의 차이점에 대해 알고 계신가요?
    - 자바스크립트에서 객체를 생성하는 방법은 어떤 것들이 있나요?
    - 전역 객체에 대해서 아시나요?
- 원시 값과 객체 비교
    - <span style="color: red">동적 타이핑을 지원하는 자바스크립트에서 데이터의 타입을 크게 2개로 나누는 이유가 있을까요?</span>
    - <span style="color: red">값에 의한 전달이 뭔가요?</span>
    - <span style="color: red">참조에 의한 전달이 뭔가요?</span>
- 함수
    - 자바스크립트에서 함수를 정의하는 방법은 몇가지가 있나요?
    - 함수 선언문과 함수 표현식은 어떤 차이가 있나요?
    - 즉시 실행 함수(IIFE)에 대해 알고 있나요? 알고 있다면 아는 내용에 대해 말해보세요
- 스코프
    - <span style="color: red">스코프가 뭔가요?</span>
    - <span style="color: red">스코프에는 어떤 종류가 있죠?</span>
    - <span style="color: red">렉시컬 스코프를 아시나요? 안다면 렉시컬 스코프는 무엇을 의미하나요?</span>
    - 전역 변수로 변수를 선언하면 생기는 문제점은 무엇이 있을까요?
- 생성자 함수에 의한 객체 생성
    - 생성자 함수가 뭔가요?
    - 객체 리터럴로 만들 때와는 무슨 차이가 있죠? 왜 생성자 함수를 사용하나요?
    - 생성자 함수가 객체(인스턴스)를 생성하는 과정에 대해 간략하게 설명해줄 수 있나요?
- 함수와 일급 객체
    - 일급 객체가 뭔가요?
    - 자바스크립트에서 함수가 일급 객체라면, 일급 객체로 뭘 할 수 있나요?
    - <span style="color: red">꼬리 질문) 함수형 프로그래밍이 뭔가요?</span>
    - 꼬리 질문) 순수 함수가 뭔가요? 일반 함수와는 어떤 차이가 있죠?
- 프로토타입
    - <span style="color: red">객체지향 프로그래밍은 무엇을 의미하나요?</span>
    - <span style="color: red">객체지향 프로그래밍의 특징에 대해 말해볼 수 있나요?</span>
    - 자바스크립트는 객체지향 프로그램밍 언어인가요?
    - 프로토타입이 뭔가요?
- strict mode
    - strict mode가 뭔가요?
    - strict mode를 통해 무엇을 예방할 수 있죠?
- 빌트인 객체
    - 빌트인 객체가 뭔가요?
    - 빌트인 객체의 종류는 어떤게 있죠?
    - 래퍼 객체에 대해서 알고 있나요?
- this
    - <span style="color: red">this가 뭔가요?</span>
    - <span style="color: red">this 바인딩이란?</span>
    - this는 동적으로 바인딩이 된다고 하는데 바인딩 되는 객체가 어떻게 다르나요?
- 실행 컨텍스트
    - <span style="color: red">실행 컨텐스트에 대해 말해보세요</span>

## [JavaScript_정리2](./javaScript/javaScript_2.md)

- 클로저
    - <span style="color: red">클로저에 대해 아시나요?</span>
    - <span style="color: red">클로저를 사용하면 뭐가 좋죠?</span>
    - <span style="color: red">클로저를 어떻게 생성하나요?</span>
- 클래스
    - 자바스크립트에서 클래스가 생기기 전에는 어떤 방식으로 객체지향 패턴을 구현했나요?
    - 그럼 생성자 함수와 클래스는 어떤 차이가 있나요?
    - 클래스 정의
    - 클래스의 상속
- 스프레드 문법
    - spread 문법이 뭔가요?
    - 어떤 상황에서 사용할 수 있죠?
- 구조 분해 할당
    - 구조 분해 할당이 뭔가요?
    - 구조 분해 할당은 크게 어떤 종류가 있나요?
- 브라우저 렌더링 과정
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
- 제너레이터와 async await
    - 제너레이터란 뭔가요? 일반 함수와는 어떤 차이가 있죠?
    - 제너레이터의 구조
    - <span style="color: red">async/await 가 뭔가요? 기존의 Promise와는 어떤 차이가 있죠?</span>
    - <span style="color: red">Promise와 async/await의 차이점 한 줄 요약</span>
- 에러
    - 에러처리를 왜 해야 하나요?
    - 자바스크립트에서 에러를 처리하는 방법에는 뭐가 있을까요?
- 모듈
    - 모듈이 뭔가요?

## [React](./react.md)

- React 시작
- 리액트를 사용하는 이유
- virtual DOM에 대해서 아시나요
- JSX가 뭔가요?
- React에서 함수 컴포넌트와 클래스 컴포넌트의 차이<span style="color:red">★★</span>
- 리액트에서 함수형 컴포넌트라고 부르지 않고 함수 컴포넌트라고 부르는 이유가 무엇인가요?<span style="color:red">★★</span>
- props와 state의 차이<span style="color:red">★★</span>
- Props가 컴포넌트간에 전달받는 것이라고 했는데 자식에서 부모로도 전달할 수 있는가?<span style="color:red">★★</span>
- FLUX에 대해서 아시나요?style="color:red">★★</span>
- 리덕스에 대해서 아시나요?style="color:red">★★</span>
- 리덕스의 기본 원칙은?style="color:red">★★</span>
- React에서 state의 불변성을 유지하라는 말이 있는데 이에 대해 설명주세요<span style="color:red">★★</span>
- 리듀서 내부에서 불변성을 지키는 이유는?<span style="color:red">★★</span>
- 리액트 사용시에 부수효과로 인해 생기는 문제점이 있다면?style="color:red">★★</span>
  - 부수 효과를 일으키는 함수 (불순 함수)
  - 부수 효과를 일으키지 않는 함수 (순수 함수)
  - 요약
- 컴포넌트의 라이프 사이클 메서드<span style="color:red">★★</span>
  - 이해
  - 메서드 종료
- Hooks의 종류
  - useState
  - useEffect
  - useMemo
  - useCallback
    - useMemo, useCallback 의 차이점 <span style="color:red">★★</span>
  - useRef
- useCallback을 사용할 떄와 사용하지 않고 함수를 선언할 때는 어떤 차이가 있나요?
- 리액트에서 setState는 비동기 동작인가요 동기 동작인가요?
- 리액트의 성능개선 방법에 대해서 설명해주세요
- 컴포넌트에서 이벤트를 실행시키기 위해서는 어떻게 핸들링해야 하나요?
- SPA가 뭔가요
  - SPA의 단점
- SSR이 뭔가요
- CSR이 뭔가요
- SEO가 뭔가요
  - TTV, TTI


## [TypeScript](./typeScript.md)

- 타입과 인터페이스
  - 타입스크립트를 왜 쓰나요?
  - <span style="color: red">타입과 인터페이스의 차이를 아시나요?</span>
  - 프로젝트 진행 시에 어떤 상황에서 타입을 쓰고 어떤 상황에서 인터페이스를 썼나요?
  - <span style="color: red">제네릭이란 뭔가요?</span>

## 참고

- [https://github.com/junh0328/prepare_frontend_interview/](https://github.com/junh0328/prepare_frontend_interview/)  
- [https://github.com/baeharam/Must-Know-About-Frontend#page_with_curl-html](https://github.com/baeharam/Must-Know-About-Frontend#page_with_curl-html)
- [https://www.frontendinterviewhandbook.com/kr/html-questions](https://www.frontendinterviewhandbook.com/kr/html-questions)



