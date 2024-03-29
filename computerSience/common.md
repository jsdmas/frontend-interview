# 목차

- 좋은 코드
- 객체지향 프로그래밍(OOP)
- RESTful API
- MVC패턴

# 좋은 코드란?

> 읽기 쉽고, 중복이 없으며 테스트가 용이한 코드
- [Reference](https://jbee.io/etc/what-is-good-code/)

# OOP(Object Oriented Programming)?

`객체`를 먼저 설명드리자면 객체는 **프로그램 동작의 주체**가 되는 요소를 말합니다.  
`객체지향프로그래밍` 을 한마디로 설명하자면 
> 현실 세계를 프로그래밍으로 옮겨와 프로그래밍 하는것을 말합니다.
- 현실 세계의 사물들을 객체라고 보고 그 객체로부터 개발하고자 하는 애플리케이션의 특징들을 뽑아와 프로그래밍 하는것이다. 이걸 추상화라 한다.

## 장점
- 코드 재사용성 & 생산성이 높아진다.
- 객체 단위로 코드가 나눠져 작성되기 때문에 디버깅이&유지보수에 용이하다.
## 단점
- 객체간의 정보교환이 **메시지 교환**(어떤 객체가 다른 객체의 메소드를 호출하는 것을 메시징이라 한다.)을 통해 일어나므로 overhead가 발생한다. (하드웨어의 발전으로 많이 보완됨.)
- 객체는 상태를 갖고, 변수가 존재하며 이 변수를 통해 객체가 예측할 수 없는 상태를 갖게 되어 애플리케이션 내부에서 버그를 발생 시킬수가 있습니다.
- 이러한 이유로 함수형 패러다임이 주목받고 있습니다.

* class는 객체를 표현하는 하나의 수단입니다. (class != 객체)

## 객체 지향적 설계 원칙
1. 단일 책임 원칙(SRP:Single Responsibility Principle)
    클래스는 단 하나의 책임을 가져야 하며 클래스를 변경하는 이유는 단 하나의 이유이어야 한다.
2. 개방-폐쇄 원칙(OCP:Open-Closed Principle)
    확장에는 열려있어야 하며 변경에는 닫혀 있어야 한다.
3. 리스코프 치환 원칙(LSP:Liskov Substitution Principle)
    상위 타입의 객체를 하위 타입의 객체로 치환해도 상위 타입을 사용하는 프로그램은 정상적으로 동작해야 한다.
4. 인터페이스 분리 원칙(ISP:Interface Segregation Principle)
    인터페이스는 그 인터페이스를 사용하는 클라이언트를 기준으로 분리해야 한다.
5. 의존 역전 원칙(DIP:Dependency Inversion Principle)
    고수준 모듈은 저수준 모듈의 구현에 의존해서는 안된다.

## 객체 지향의 특성
1. 추상화 (Abstration) : 객체의 공통적인 속성과 기능을 추출하여 정의하는것
2. 상속 (Inheritance) : 기존 클래스를 재활용하여 새로운 클래스를 작성하는것
3. 다형성 : 한 타입의 참조변수를 통해 여러 타입의 객체를 참조할 수 있도록 만든 것
4. 캡슐화 (Encapsulation) : 서로 연관있는 속성과 기능들을 하나의 캡슐(capsule)로 만들어 데이터를 외부로부터 보호, 은닉하는 것

# RESTful API

> 자원을 정의하고 자원에 대한 주소를 지정하는 방법 전반에 대한 패턴

- [Reference](https://meetup.nhncloud.com/posts/92)
## 특징
1. Uniform (유니폼 인터페이스)
    조작을 통일되고 한정적인 인터페이스로 수행하는 아키텍처 스타일
2. Stateless (무상태성)
    작업을 위한 상태정보를 따로 저장하고 관리하지 않는다.
3. Caching (캐시 가능)
    Last-Modified태그나 E-Tag를 이용하면 캐싱 구현이 가능합니다.
4. Client-Server 구조
    서로간의 의존성이 줄어들게 됩니다.
5. Self-descriptiveness (자체 표현 구조)
    REST API 메시지만 보고도 이를 쉽게 이해할 수 있는 자체 표현 구조로 되어있습니다.
6. 계층형 구조
    클라이언트와 서버가 분리되어 있기 때문에 중간에 프록시 서버, 암호화 계층 등 중간매체를 사용할 수 있어 자유도가 높다.

## RESTful 하게 API를 디자인 한다는 것은 무엇을 의미하는가?
1. 리소스와 행위를 명시적이고 직관적으로 분리합니다.
2. Message는 Header, Body를 명확하게 분리해서 사용합니다.
3. API의 버전을 관리한다
4. 서버와 클라이언트가 같은 방식을 사용해서 요청하도록 한다.

## 장점
1. Open API를 제공하기 쉽다.
2. 멀티플랫폼 지원 및 연동이 용이하다.
3. 원하는 타입으로 데이터를 주고받을 수 있다.
4. 기존 웹 인프라(HTTP)를 그대로 사용할 수 있다.

## 단점
1. 사용할 수 있는 메소드가 한정적이다.
2. 분산환경에는 부적합하다.
3. HTTP통신 모델에 대해서만 지원한다.


# MVC 패턴이란?
MVC(Model-View-Controller)의 약자로, 소프트웨어 아키텍처 패턴 중 하나입니다.  
MVC패턴은 소프트웨어의 각 구성요소를 세 가지 역할로 나눕니다.  
- Model : 컨트롤러가 호출할 떄, 요청에 맞는 역할을 수행하며 데이터를 처리합니다.
- View : 사용자 인터페이스를 나타내며 사용자가 데이터를 볼 수 있도록 합니다.
- Controller : 사용자 인터페이스에서 발생하는 이벤트를 처리하고 Model과 View를 연결합니다.



