# 목차

- ⭐ 브라우저 렌더링 과정을 설명해주세요.
- 브라우저는 어떻게 동작 하나요?
- Webpack, Babel, Polyfill에 대해 설명해주세요.
- ESLint와 Prettier에 대해 설명해주세요.
- SPA와 MPA에 대해 설명해주세요.
- ⭐ CSR과 SSR의 차이는 무엇인가요?
- ⭐ CORS와 해결 경험을 말씀해주세요.
- bundle의 사이즈를 줄이려면 어떻게 해야 하나요?
- ⭐ 쿠키, 세션, 웹스토리지의 차이에 대해 설명해주세요.
  - 브라우저에서 탭 이동 혹은 탭 종료 시에는 세션 스토리지에 어떤 영향을 끼치나요?
- ⭐ 로그인 처리를 할 때 쿠키와 세션을 어떻게 사용하시나요?
- ⭐ 토큰 기반 인증 방식에 대해 설명해주세요.
  - ⭐ JWT 토큰을 쿠키에 저장했을 때 취약점에 대해 설명해주세요.
- ⭐ 크로스 브라우징에 대해 설명해주세요.
  - 크로스 브라우징 이슈를 해결했던 경험을 말씀해주세요.
- 웹사이트 성능 최적화에는 어떤 방법이 있나요?
- ⭐ REST API에 대해 설명해주세요.
- Git Flow에 대해 설명해주세요.
- ⭐ SEO에 대해 설명해주세요.
- BOM과 DOM에 대해 설명해주세요.
- ⭐ 리플로우와 리페인트에 대해 설명해주세요.
  - visibility 속성은 리플로우를 발생시킬까요?
- Agile에 대해 설명해주세요.
- dependencies 와 devDependencies 차이에 대해 설명해주세요.
- XSS와 CSRF에 대해 설명해주세요.
- 인증과 인가에 대해 설명해주세요.
- package.json에서 private에 대해 설명해주세요.
- 프로젝트를 npm에 배포하려면 어떤 설정이 필요할까요?
- ⭐ SEO는 어떤 식으로 신경쓰셨나요?
- ⭐ 어플리케이션의 성능은 어떤식으로 측정하셨나요?
- LightHouse 결과가 좋지 않을 때, 프로젝트에서 병목 현상은 어떻게 해결할 수 있을까요?
- ⭐ 주소창에 주소를 입력했을 때의 흐름을 설명해주세요.

# ⭐ 브라우저 렌더링 과정을 설명해주세요.

브라우저가 화면에 나타나는 요소를 렌더링 할 떄, 웹킷(Webkit)이나 게코(Gecko)등과 같은 렌더링 엔진을 사용합니다.  
렌더링 엔진이 HTML, CSS, JS로 렌더링할 때, CRP(Critical Rendering Path)라는 프로세스를 사용하며 다음 단계들로 이루어진다.

1. HTML 파싱 후, DOM(Document Object Model)트리 구축
2. CSS 파싱 후, CSSOM(CSS Object Model)트리 구축
3. JavaScript 실행
   - HTML 중간에 스크립트가 있다면 HTML 파싱이 중단됩니다.
4. DOM과 CSSOM을 조합하여 렌더트리(Render Tree)구축
   - `display:none`속성과 같이 화면에서 보이지도 않고 공간을 차지하지 않는 것은 렌더트리로 구축되지 않습니다.
5. 뷰포트 기반으로 렌더트리의 각 노드가 가지는 정확한 위치와 크기 계산(Layout/Reflow 단계)
6. 계산한 위치/크기를 기반으로 화면에 그림(Paint 단계)

# 브라우저는 어떻게 동작 하나요?

1. 사용자가 참조하고자 하는 웹페이지를 서버에 요청(Request)하고 서버의 응답(Response)를 받는다.
2. 브라우저는 서버로부터 HTML, CSS, JavaScript, 이미지 파일 등을 응답받는다.
3. HTML, CSS 파일은 렌더링 엔진의 HTML파서와 CSS파서에 의해 파싱(Parsing)되어 DOM, CSSOM 트리로 변환되고 렌더 트리로 결합된다.
4. 이렇게 생성된 렌더 트리를 기반으로 브라우저는 웹페이지를 표시합니다.

> 자바스크립트는 렌더링 엔진이 아닌 자바스크립트 엔진이 처리합니다.

HTML 파서는 script 태그를 만나면 자바스크립트 코드를 실행하기 위해 DOM생성 프로세스를 중지하고 자바스크립트 엔진으로 제어 권한을 넘깁니다.  
제어 권한을 넘겨받은 javaScript 엔진은 script 태그 내의 자바스크립트 코드 또는 script 태그의 src 어트리뷰트에 정의된 자바스크립트 파일을 로드하고 파싱하여 실행합니다.  
자바스크립트 실행이 완료되면 다시 HTML파서로 제어 권한을 넘겨서 브라우저가 중지했던 시점부터 DOM 생성을 재개합니다.  
이처럼 브라우저는 **동기(Synchronus)**적으로 HTML, CSS, JavaScript를 처리합니다.

위의 이유로 script태그는 body태그의 맨 아래에 위치하게 되는데 얻는 이점은 아래와 같습니다.

- HTML 요소들이 스크립트 로딩 지연으로 인해 렌더링에 지장 받는 일이 발생하지 않아 페이지 로딩 시간이 단축됩니다.
- DOM이 완성되지 않은 상태에서 자바스크립트가 DOM을 조작한다면 에러가 발생합니다.

# Webpack, Babel, Polyfill에 대해 설명해주세요.

**Polyfill**

> polyfill은 기본적으로 지원하지 않는 이전 브라우저에서 최신 기능을 제공하는 데 필요한 코드입니다.

**Babel**

> 바벨의 자바스크립트의 컴파일러입니다.
> 컴파일(Compile)은 주어진 언어로 작성된 컴퓨터 프로그램을 다른 언어의 동등한 프로그램으로 변환하는 프로세스입니다.

**Webpack**

> javaScript의 모듈 번들러로, javaScript파일을 포함한 에셋을 컴파일, 번들링 하는 데 사용됩니다.

# ESLint와 Prettier에 대해 설명해주세요.

**ESLint**

> 자바스크립트 코드에서 발견된 문제 패턴을 식별하기 위한 정적 코드 분석기 입니다.
> **Prettier**
> 일관적인 코드 스타일을 유지할 수 있게 도와주는 툴입니다.

# SPA와 MPA에 대해 설명해주세요.

### SPA(Single Page Application)

![](https://github.com/jsdmas/frontend-interview/assets/105098581/60c22b0c-b9a1-4afe-aea7-1ce6a1d12544)

- 한 개(Single)의 페이지로 구성된 Application
- 서버로부터 완전한 페이지를 불러오지 않고 현재의 페이지를 동적으로 다시 작성함으로써 사용자와 소통하는 웹 어플리케이션이나 웹사이트를 말합니다.
- SPA의 핵심 가치는 사용자 경험(UX)향상에 있으며 부가적으로 어플리케이션 속도의 향상도 기대할 수 있어 모바일 퍼스트 전략에 부합합니다.

**작동방식**

- SPA는 웹 어플리케이션에 필요한 모든 정적 리소스를 최초 접근 시 단 한번만 다운로드 합니다.
- 이후 새로운 페이지 요청 시, 페이지 갱신에 필요한 데이터만을 JSON으로 전달받아 페이지를 갱신합니다.
  - 기존 페이지 내부를 수정해서 보여주는 방식입니다.
- SPA를 일반적으로 CSR(Client Side Rendering)방식으로 렌더링 한다고 말합니다.

**장점**

1. 속도 및 응답시간
   - 전체 페이지를 다시 렌더링하지 않고 변경되는 부분만을 갱신하므로 새로고침이 발생하지 않아 네이티브앱과 유사한 사용자 경험을 제공합니다.
2. 모바일 친화적
3. 로컬 스토리지 캐시
   - 애플리케이션은 하나의 요청만 보내고 모든 데이터를 저장한 다음 이 데이터를 사용할 수 있으며 오프라인에서도 작동합니다.

**단점**

1. 초기 구동 속도
2. SEO 이슈

### MPA(Multiple Page Application)

![](https://github.com/jsdmas/frontend-interview/assets/105098581/907cf1a6-afca-46de-873e-59b95c15397e)

- 여러 개(Multiple)의 페이지로 구성된 어플리케이션

**작동방식**

- 새로운 페이지를 요청할 때마다 서버에서 렌더링된 정적 리소스(HTML, CSS, JavaScript)가 다운로드 됩니다.
- 페이지를 이동하거나 새로고침하면 전체 페이지를 다시 렌더링합니다.
- MPA는 SSR(Sever Side Rendering)방식으로 렌더링 합니다.
- 여러개의 독립적인 페이지로 구성되어 있습니다.

**장점**

- SEO 친화적
- 간편한 개발
- 초기 로딩 속도가 빠릅니다.

**단점**

- 실시간 업데이트를 구현하는데 어려움
- 서버 부하 : 각 페이지 요청마다 서버에서 HTML을 생성하고 전송해야 하므로 부하가 발생
- 페이지 간의 전환 시에 끊김이 발생할 수 있으며 페이지를 로드할 떄마다 서버와의 통신이 필요하기 떄문에 사용자 경험 좋지않다.

# ⭐ CSR과 SSR의 차이는 무엇인가요?

## CSR (Client Side Rendering)

> 렌더링이 클라이언트 측에서 일어납니다. javaScript파일이 다운되고 실행되면 클라이언트 측에서 콘텐츠를 동적으로 생성하고 렌더링합니다.
> **장점**

- 서버 부담 감소
- 사용자 경험 향상

**단점**

- 초기 로딩 시간
- SEO 최적화 문제

## SSR (Sever Side Rendering)

> 서버에서 콘텐츠를 렌더링하여 클라이언트에게 전달하는 방식입니다.
> **장점**

- 초기 로딩 시간
- SEO 최적화

**단점**

- 서버 부하
- 사용자 경험

# ⭐ CORS와 해결 경험을 말씀해주세요.

**CORS (Cross-Origin Resource Sharing)**

> 다른 출처의 리소스 공유에 대한 허용/비허용 정책입니다.

### 동작

1. 클라이언트에서 HTTP요청 헤더에 Origin을 담아 전달합니다.
2. 서버는 응답헤더에 Access-Origin-Allow-Origin을 담아 클라이언트에 전달합니다.
3. 클라이언트에서 Origin과 서버가 보내준 Access-Control-Allow-Origin을 비교합니다.

# bundle의 사이즈를 줄이려면 어떻게 해야 하나요?

1. Bundle Analayzer를 통해 크기가 큰 패키지를 확인하고 제거합니다.
2. webpack을 사용해 트리 쉐이킹, 압축, 난독화 합니다.
3. 코드 스플리팅

# ⭐ 쿠키, 세션, 웹스토리지의 차이에 대해 설명해주세요.

> 모두 클라이언트 상에서 key/value 쌍을 저장할 수 있는 메커니즘으로 value는 반드시 문자열 이어야 합니다. 모두 동일 출처 정책(SOP)를 따르기 때문에 다른 도메인에서 접근할 수 없습니다.

|               | cookie                | local storage         | session storage       |
| ------------- | --------------------- | --------------------- | --------------------- |
| 생성자        | 클라이언트/서버       | 클라이언트            | 클라이언트            |
| 지속시간      | 설정 여부에 따라 다름 | 명시적으로 지울떄까지 | 탭/윈도우 닫을 떄까지 |
| 용량          | 5KB                   | 5MB/10MB              | 5MB                   |
| 서버와의 통신 | O                     | X                     | X                     |
| 취약점        | XSS/CSRF공격          | XSS공격               | XSS공격               |

- 세션
  - 유저가 웹사이트에서 로그인하면 세션이 서버 메모리(혹은 데이터베이스)상에 저장됩니다.
  - 서버에서 브라우저에 쿠키에다가 session Id를 저장합니다.
  - 쿠키에 정보가 담겨있기 때문에 브라우저는 해당 사이트에 대한 모든 Request에 Session Id를 쿠키에 담아 전송합니다.
  - 서버는 클라이언트가 보낸 Session Id 와 서버 메모리로 관리하고 있는 Session Id를 비교하여 인증을 수행합니다.
  - 단점
    - 해커가 세션ID 자체를 탈취하여 클라이언트인척 위장할 수 있다는 한계가 존재합니다.
    - 서버에서 세션 저장소를 사용하므로 요청이 많아지면 서버에 부하가 심해집니다.

## 브라우저에서 탭 이동 혹은 탭 종료 시에는 세션 스토리지에 어떤 영향을 끼치나요?

세션 스토리지는 페이지 세션이 유지되는 동안에만 데이터를 저장하며, 페이지 세션이 종료되면 해당 세션에 저장된 데이터는 삭제됩니다.

# ⭐ 로그인 처리를 할 때 쿠키와 세션을 어떻게 사용하시나요?

1. 사용자인증
   - 사용자 인증이 성공하면 서버는 고유한 세션ID를 생성하고 해당 세션을 서버 측에 저장합니다.
2. 세션 ID 쿠키 설정
   - 서버는 클라이언트에게 응답으로 세션ID를 가지고 있는 쿠키를 설정합니다.(쿠키의 값으로 세션ID를 가진다.)
   - 클라이언트는 이 세션 ID 쿠키를 저장하고, 서버에 다음 요청을 보낼 때마다 해당 세션ID를 함께 전송합니다.
3. 세션 데이터 관리
   - 클라이언트는 단지 세션ID를 쿠키로 저장하고, 서버에 요청할 때마다 세션ID를 전달하여 서버에서 해당 세션의 데이터를 사용합니다.

# ⭐ 토큰 기반 인증 방식에 대해 설명해주세요.

> 인증받은 사용자에게 토큰을 발급하고, 로그인이 필요한 작업일 경우 헤더에 토큰을 함께 보내 인증받은 사용자인지 확인합니다.

이는 서버 기반 인증 시스템과 달리 상태를 유지하지 않으므로 Stateless한 특징을 가지고 있습니다.(세션 기반 인증 단점을 극복)

토큰 기반 인증 방식은 클라이언트가 서버에 접속하면 서버에서 해당 클라이언트에게 인증되었다는 의미로 `토큰`을 부여합니다.  
이 토큰은 `유일`하며 토큰을 발급받은 클라이언트는 또 다시 서버에 요청을 보낼 때 요청 헤더에 토큰을 심어서 보냅니다.  
서버에서는 클라이언트로부터 받은 토큰을 서버에서 제공한 토큰과의 일치 여부를 체크하여 인증 과정을 처리하게 됩니다.

토큰은 세션과 달리 **클라이언트에 저장**되기 때문에 메모리나 스토리지 등을 통해 세션을 관리했던 서버의 부담을 덜 수 있습니다.  
(토큰 자체에 데이터가 들어있기 때문에 클라이언트에서 받아 위조되었는지 판별만 하면 되기 때문입니다.)

### Token 인증 방식

![](https://github.com/jsdmas/frontend-interview/assets/105098581/0de41441-4452-4360-a430-72b7849aec32)

1. 사용자가 아이디와 비밀번호로 로그인합니다.
2. 서버 측에서 사용자에게 **유일한 토큰**을 발급합니다.
3. 클라이언트는 서버 측에서 전달받은 토큰을 쿠키나 스토리지에 저장해두고, 서버에 요청을 할 때마다 해당 토큰을 HTTP 요청 헤더에 포함시켜 전달합니다.
4. 서버는 전달받은 토큰을 검증하고 요청에 응답합니다.
   - 토큰에는 요청한 사람의 정보가 담겨있기 때문에 서버는 DB를 조회하지 않고 누가 요청했는지 알 수 있습니다.

### 단점

1. 쿠키/세션 과 다르게 토큰 자체의 데이터 길이가 길어, 인증 요청이 많아질수록 네트워크 부하가 심해질 수 있습니다.
2. Payload 자체는 암호화 되지 않기 때문에 유저의 **중요한 정보는 담을 수 없습니다.**
3. 토큰을 **탈취**당하면 대처하기 어렵습니다. (사용 기간을 제한하는 식으로 극복)

### JWT(JSON Web Token)

> 인증에 필요한 정보들을 암호화시킨 JSON토큰을 의미합니다. JSON 데이터를 Base64 URL-safe Encode를 통해 인코딩하여 직렬화 했습니다.

### JWT구조

> Header(헤더), Payload(내용), Signature(서명)

- Header
  - JWT에서 사용할 타입과 해시 알고리즘 종류가 담겨있습니다.
- Payload
  - 서버에서 첨부한 사용자 권한 정보와 데이터가 담겨있습니다.
- Signature
  - Header, Payload를 인코딩한 후 Header에 명시된 해시함수를 적용하고 개인키(Primary Key)로 서명한 전자서명이 담겨있습니다.

## ⭐ JWT 토큰을 쿠키에 저장했을 때 취약점에 대해 설명해주세요.

- [ref](https://velog.io/@0307kwon/JWT%EB%8A%94-%EC%96%B4%EB%94%94%EC%97%90-%EC%A0%80%EC%9E%A5%ED%95%B4%EC%95%BC%ED%95%A0%EA%B9%8C-localStorage-vs-cookie)
- [ref2](https://inpa.tistory.com/entry/WEB-%F0%9F%93%9A-JWTjson-web-token-%EB%9E%80-%F0%9F%92%AF-%EC%A0%95%EB%A6%AC)

> CSRF 공격에 취약합니다.
> 자동으로 http request에 담아서 보내기 때문에  
> 공격자가 request url만 안다면 사용자가 관련 link를 클릭하도록 유도하여 request를 위조하기 쉽습니다.

#### CSRF

정상적인 request를 가로채 피해자인 척 하고 백엔드 서버에 변조된 request를 보내 악의적인 동작을 수행하는 동작을 의미합니다.  
(피해자 정보 수정, 정보 열람 등)

# ⭐ 크로스 브라우징에 대해 설명해주세요.

> 모든 브라우저에서 의도한 대로 올바르게(호환성) 작동하게 하는 것을 말합니다.

- 브라우저마다 각기 다른 엔진을 사용하여 코드가 일관되게 동작하지 않는 문제가 발생합니다.
- 이러한 문제를 해결하기 위해 크로스 브라우징 작업을 사용합니다.

## 크로스 브라우징 이슈를 해결했던 경험을 말씀해주세요.

chrom 브라우저와 firefox 브라우저에서 css스타일이 다르게 적용되어 스타일 차이를 최소화 하기위해 resetCss를 적용하여 웹 페이지를 디자인 해본 경험이 있습니다.

# 웹사이트 성능 최적화에는 어떤 방법이 있나요?

1. CSS는 HTML 문서 최상단(`<head>`아래)에 배치하기
   - 랜더 트리를 구성하기 위해서는 DOM 트리와 CSSOM 트리가 필요합니다.
   - DOM 트리는 파싱 중에 태그를 발견할 때마다 순차적으로 구성할 수 있지만, CSSOM 트리는 CSS를 모두 해석해야 구성할 수 있습니다.
   - 즉, CSSOM 트리가 구성되지 않으면 렌더 트리를 만들지 못하고 렌더링이 차단됩니다. (이런 이유로 CSS는 렌더링 차단 리소스라 합니다.)
   - 위와 같은 이유로 렌더링이 차단되지 않도록 CSS는 항상 HTML 문서 최상단(`<head>`아래)에 배치합니다.
2. script 태그는 HTML 문서 최하단(`</body>` 직전)에 배치하기
   - javaScript는 DOM 트리와 CSSOM 트리를 동적으로 변경할 수 있기 때문에 HTML 파싱을 차단하는 블록 리소스 입니다.
   - `<script>`태그를 만나면 스크립트가 실행되며 그 이전까지 생성된 DOM에만 접근할 수 있습니다.
   - 스크립트 실행이 완료될 때까지 DOM 트리 생성이 중단됩니다.
   - 이러한 이유로 javaScript도 렌더링 차단 리소스라고 합니다.
   - HTML 파싱을 멈추지 않게 하려면 `defer`, `async` 속성을 명시하면 스크립트가 DOM 트리와 CSSOM 트리를 변경하지 않겠다는 의미이기 때문에 브라우저가 파싱을 멈추지 않습니다.
3. 리소스 요청 수 줄이기
   - CSS, javaScript, 이미지 등 웹 페이지에 포함된 리소스는 서버 요청 후 다운로드되어야 사용할 수 있습니다.
   - 이미지 스프라이트
   - CSS, javaScript 번들(여러 개의 모듈 파일을 하나로 묶어서 1개 파일로 생성 - webpack 사용)
4. 리소스 용량 줄이기
   - 중복 코드 제거
   - 압축(Minify)하여 사용하기 (HTML,CSS,javaScript 모두 압축해 사용할 수 있으며 불필요한 주석, 공백 등을 제거한 후 난독화하여 사용)

# ⭐ REST API에 대해 설명해주세요.

### REST (REpresentational State Transfer)

> 전반적인 웹 어플리케이션에서 상호작용하는데 사용되는 웹 아키텍처 모델입니다.
> 즉, 자원을 주고받는 웹 상에서의 통신 체계에 있어서 범용적인 스타일을 규정한 아키텍쳐 라고 할 수 있습니다.

### API (Application Programming Interface)

> 구글 맵 API, 카카오 맵 API 와 같이 기존에 있는 응용 프로그램을 통해서 데이터를 제공받거나 기능을 사용하고자 할 때 사용하는 인터페이스 및 규격 을 말합니다.
> API는 프로그래밍 언어, 운영체제 등에서도 사용되는 범용적인 용어입니다.  
> 따라서, REST API라는 것은 REST 원칙을 적용하여 서비스 API를 설계한 것을 말하며 대부분의 서비스가 REST API를 제공합니다.

## REST API 특징

1. **균등한 인터페이스(Uniform Interface)**
   - REST가 HTTP의 표준만 따른다면 어떠한 기술이던지 접목하여 사용할 수 있기 떄문에 플랫폼이나 언어의 제약에 구애받지 않습니다.
2. **무상태성(Stateless)**
   - 서버는 클라이언트 상황을 고려하지 않고 API 요청에 대해서만 처리하기 때문에 이를 **"상태가 없다"**라고 표현합니다.
   - 이렇게 되면 클라이언트를 고려하지 않아도 되기 떄문에 구현이 간결해집니다.
3. **캐싱 가능(Cacheable)**
   - REST는 HTTP 표준을 기반으로 만들어졌기 떄문에 HTTP의 특징인 캐싱을 사용할 수 있습니다.
   - REST API를 활용하여 `GET` 메소드를 `Last-Modified` 값과 함께 보낼 경우, 컨텐츠의 변화가 없을 때 캐시된 값을 사용하게 됩니다.
4. **자체 표현성(Self-Descriptiveness)**
   - REST API의 자원명시 규칙 및 메소드는 그 자체로 의미를 지니기 떄문에 어떠한 요청에 있어서 그 요청 자체로 어떤 것을 표현하는지 알아보기 쉽습니다.
5. **클라이언트-서버 구조(Client-Server Architecture)**
   - REST 서버가 API를 제공하는 방식이기 떄문에 클라이언트에서 처리하는 부분과 독립적으로 동작합니다.
   - 따라서, 서로간의 의존성이 줄어들고 클라이언트와 서버를 최대한 독립적으로 개발할 수 있도록 도와줍니다.
6. **계층형 구조(Layout System)**
   - 클라이언트는 계층형 구조가 불가능 하지만 REST 서버의 경우, 보안/로드 밸런싱/암호화 등을 추가할 수 있고 Proxy 및 게이트웨이 등의 중간매체를 사용할 수 있습니다.

## REST API의 핵심

1. URL은 리소스를 표현해야 합니다.

- 동사가 아닌 명사

```
/students/1
```

- 리소스는 Collection과 Document로 표현할 수 있다.

```
/locations/seoul/schools/3
```

2. 리소스에 대한 행위는 HTTP의 Method로 표현해야 합니다.
   - GET, POST, DELETE, PUT

## HTTP 상태코드

> 요청에 의한 응답의 상태코드 또한 명확하게 돌려주는 것이 잘 설계된 REST API 입니다.

- 2xx : 성공관련
- 3xx : 리다이렉션 관련
- 4xx : 클라이언트 에러 관련
- 5xx : 서버 에러 관련

# Git Flow에 대해 설명해주세요.

> 소스코드를 관리하고 출시하기 위한 브랜치 관리 전략(branch management strategy)중 하나입니다.

![](https://github.com/jsdmas/frontend-interview/assets/105098581/b4640642-8165-47be-98d9-b09e9e32a4c8)

# ⭐ SEO에 대해 설명해주세요.

> 검색엔진 결과 페이지에서 웹사이트 또는 웹페이지의 상위 노출도를 높이는 작업을 SEO라고 합니다.

검색엔진 최적화를 위한 작업으로는 메타 태그를 활용하고 robots.txt파일을 수정하여 페이지 크롤링을 제어하는 방법 등이 있습니다.

# BOM과 DOM에 대해 설명해주세요.

## BOM (Browser Object Model)

- 브라우저에 접근할 수 있는 객체의 모음 (location, window, document, navigator, history, screen...)
- window 객체를 통해 접근 가능
- DOM이 현재 눈에 보이는 웹문서에 대한 제어와 변경이라면 BOM은 window를 제어합니다.

## DOM (Document Object Model)

- 문서(HTML, XML등)의 구조화된 표현을 제공하며 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공합니다.
- DOM은 nodes와 object로 문서를 표현합니다.

# ⭐ 리플로우와 리페인트에 대해 설명해주세요.

- [ref](https://kwangsunny.tistory.com/42)
  > 리플로우, 리페인트는 DOM 요소가 시각적으로 변경됐을떄, 이 변화를 다시 계산하고 화면에 그려주는 작업입니다.

## 리플로우(reflow)

> DOM 요소의 기하학적 속성이 변경될때, 브라우저 사이즈가 변할떄, 스타일시트가 로딩되었을 때 발생하는 변화들을 다시 계산해주는 작업을 뜻합니다.(Layout 이라고도 합니다.)

직접적으로 요소의 시각적 속성을 바꿔주는 행위 말고 단순히 어떤 메서드를 호출하거나 프로퍼티 값을 가져오는 것 만으로도 리플로우가 발생하는 경우가 있습니다.

- [ref](https://gist.github.com/paulirish/5d52fb081b3570c81e3a)
- window.scrollX, window.scrollY, window.innerHeight, window.innerWidth, window.getComputedStyle() 등
- 이유는 div와 같은 요소에 직접적으로 px사이즈를 주지 않는 이상 픽셀 사이즈는 화면 사이즈에 따라 매 순간 달라집니다.(width : 50% 등)
- 다시 말해, 우리가 알고싶은 값은 요소의 계산된 스타일 값이고, 위의 메서드 혹은 프로퍼티값을 사용하면 요소의 계산된 스타일 값을 알 수 있습니다.
- 그래서 div.clientHeight를 쓰게 되면 **div의 최신값을 계산하기 위해 리플로우가 발생하게 됩니다.**

## 리페인트(repaint)

> 변경된 요소를 실제로 화면에 그려주는 작업을 repaint라고 합니다. 그래서 리플로우가 발생하면 필연적으로 리페인트가 실행됩니다.

## visibility 속성은 리플로우를 발생시킬까요?

> 배경색이나 visibility 속성이 변했을떄는 리플로우는 발생하지 않고 리페인트만 발생합니다.
> 이유는 위치, 크기, 테두리 두께, 폰트 사이즈 같이 **기하학적인 변화가 아닌 단순히 색상만 바뀌기 때문입니다.**

### 리플로우, 리페인트 줄이기

1. DOM 속성 변경 코드 그룹핑 하기
2. 리플로우 유발 메서드는 별도 저장해 사용하기
3. CSS 수정은 일괄로 변경 해주기
4. display:none 사용하기

# Agile에 대해 설명해주세요.

> 소프트웨어 개발 관리 방법론 중 하나로, 처음부터 끝까지 계획을 수립하고 개발하는 폭포수(Waterfall) 방법론과는 달리 개발과 함께 즉시 피드백을 받아서 유동적으로 개발하는 방법입니다.

특징은 다음과 같습니다.

1. 개인과 개인의 상호작용이 프로세스 및 툴보다 우선
2. 작동하는 소프트웨어가 포괄적인 문서보다 우선
3. 고객과의 협업이 계약 협상보다 우선
4. 변화에 대응하는 것이 계획을 따르는 것보다 우선

# dependencies 와 devDependencies 차이에 대해 설명해주세요.

> javaScript 프로젝트에서 패키지 의존성을 관리하는데 사용됩니다.

- dependencies
  - 애플리케이션 또는 프로젝트가 실행되는 데 필요한 외부 패키지 의존성을 정의합니다.
- devDependencies
  - 개발 시에만 필요한 패키지 의존성을 정의합니다.
  - 개발 환경에서 도움을 주는 도구, 테스트 프레임워크, 번들러, 리포팅 도구 등을 포함합니다.

# XSS와 CSRF에 대해 설명해주세요.

## XSS(Cross Site Scripting, 사이트간 스크립팅)

> 웹사이트 관리자가 아닌 사람이 웹사이트에 악성 스크립트를 삽입할 수 있는 취약점을 이용한 공격기법입니다.
> 사용자로부터 받은 입력을 제대로 검증하지 않을 때 나타나며, 사용자의 정보를 탈취하거나 비정상적인 기능을 실행할 수 있습니다.

1. 저장 XSS : 웹사이트에 취약점이 있는 웹 서버에 스크립트를 저장시켜서 해당 웹사이트를 요청하는 사용자로 하여금 스크립트를 실행하게 하는 기법입니다.
2. 반사 XSS : 검색을 사용할 떄 결과가 없으면 브라우저에서 입력한 값을 문서에 포함하여 응답하는데 이를 사용하여 스크립트를 실행하는 기법으로 악성 URL을 배포하여 클릭하도록 유도하는 방법을 사용합니다.

- 대응법
  - 입/출력 값 검증 및 무효화
  - 보안 라이브러리 사용

## CSRF(Cross Site Request Forgery, 사이트간 요청변조)

> 사용자가 의도치 않게 공격자가 의도한 행동을 하여 취약점을 노출시키거나 수정/삭제/생성 등을 하게 만드는 공격 기법입니다.
> 이메일을 열어보거나 악성 사이트에 접근했을 떄 특정한 요청을 하는 CSRF 스크립트를 실행하는 방식입니다.

- 대응법
  - referrer검증
  - CSRF토큰
  - 캡챠 사용 : 사용자와의 상호작용을 통해서 숫자/문자를 입력하여 검증합니다.

# 인증과 인가에 대해 설명해주세요.

> 인증과 인가는 정보 시스템에서 사용자의 접근 제어 및 권한 관리를 위해 사용되는 개념입니다.

## 인증(Authentication)

사용자가 자신의 신원을 확인하고, 시스템에 대한 신뢰성 있는 엑세스를 얻는 과정입니다.  
보통 아이디/비밀번호 조합, 토큰 기반 인증 등을 사용하여 인증을 수행합니다.

## 인가(Authorization)

인증된 사용자에 대한 접근 권한을 관리하는 과정입니다.  
사용자에게 특정 리소스나 기능에 대한 권한을 할당하고, 이를 기반으로 사용자가 특정 시스템의 특정 작업을 수행할 수 있는지 결정합니다.

# package.json에서 private에 대해 설명해주세요.

package.json 파일은 Node.js 프로젝트의 구성 정보를 담고 있는 파일입니다.  
"private"속성은 package.json 파일이 현재 프로젝트를 npm 공개 레지스트리에 게시하지 않도록 지정하는 데 사용됩니다.

# 프로젝트를 npm에 배포하려면 어떤 설정이 필요할까요?

- "name": 프로젝트의 고유한 이름
- "version": 프로젝트 버전
- "description": 프로젝트 설명
- "main": 프로젝트의 진입점 파일
- "scripts": 배포를 위한 스크립트 명령어들
- "keywords": 프로젝트와 관련된 키워드들
- "author": 프로젝트 작성자 정보
- "license": 프로젝트 라이선스
  pacakage.json에 작성 후 npm publish 실행

# ⭐ SEO는 어떤 식으로 신경쓰셨나요?

react-helmet 라이브러리를 사용하여 각각의 페이지마다 **메타 데이터를 설정**하고 **title**을 지정해 주었습니다.

# ⭐ 어플리케이션의 성능은 어떤식으로 측정하셨나요?

1. LightHouse를 성능 지표(FCP, TTI 등)를 측정하였습니다.
2. chrom 개발자 도구의 메모리 탭, 네트워크를 보면서 성능을 측정하였습니다.

# LightHouse 결과가 좋지 않을 때, 프로젝트에서 병목 현상은 어떻게 해결할 수 있을까요?

- 저같은 경우 이미지 lazy-loading, webpack 설정(트리 쉐이킹, 난독화)을 통해 병목 현상을 줄이고 성능을 개선시켰습니다.

# ⭐ 주소창에 주소를 입력했을 때의 흐름을 설명해주세요.

- [ref](https://aws.amazon.com/ko/blogs/korea/what-happens-when-you-type-a-url-into-your-browser/)

1. 웹 브라우저에 URL을 입력하고 Enter키를 누릅니다.
2. 웹 브라우저가 도메인의 IP 주소를 조회합니다. (먼저 캐시를 찾고, 그 다음 DNS를 검색합니다.)
3. 웹 브라우저가 찾은 IP주소를 기반으로 서버와의 TCP 연결을 시작합니다.
4. 웹 브라우저가 HTTP요청을 서버로 전송합니다. (필요한 경우, HTTPS 보안 통신이 진행됩니다.)
5. 웹 서버가 요청을 처리하고 응답을 다시 웹 브라우저로 전송합니다.
6. 웹 브라우저가 전송 받은 콘텐츠를 렌더링합니다.
