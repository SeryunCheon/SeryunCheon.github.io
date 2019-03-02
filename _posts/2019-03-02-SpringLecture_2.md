---
layout: post
springMVC: true
title:  "스프링프레임워크 -2강"
date:   2019-03-02
excerpt: "주요 개념소개/ STS소개 및 제공하는 기능, Maven과 Library, 프로젝트 시작"
tag:
 - maven
 - spring
 - STS
 - AOP
 - DI
comments: true
---

# 스프링프레임워크

### 1.Sprign Framework?
---
 - Java엔터프라이즈 개발을 편하게 해주는 오픈소스 경량급 애플리케이션 프레임워크이다.
 - - 플리케이션프레임워크: 특정 계층, 분야에 국한되지 않고 전 영역을 포괄하는 범용적 프레임워크
 - - 경량급프레임워크 : 단순하 웹컨테이너에서도 엔터프라이즈 개발의 고급기술을 대부분 사용 가능
 - - Spring은 OpenSourde의 장점을 충분히 취하면서 동시에 OpenSource 제품의 단점과 한계를 잘 극복한다.
 - - Portable Service Abstraction, DI, AOP, POJO

###   2.SPring Framework 특징
---
 1. 스피링컨테이너는 자바객체의 LifeCycle을 관리하며, 컨테이너로부터 필요한 객체를 가져와 사용할 수 있다( 우리 예전에 수업시간 때 dao나 서비스 객체 하나 만들어서 bean으로 등록하고 가져다사용할 수 있던거 ㅇㅇ 기억하면됨)
 2.  DI(Dependency Injection)지원. 스프링은 설정 파일이나 어노테이션을 통해서 객체 간의 의존관계를 설정할 수 있도록 하고 있다.
 3.  AOP(Aspect Oriendted Programming)지원. 스프링은 트랜잭션이나 로깅, 보안과같이 공통적으로 필요로 하는 모듈들을 실제 핵심 모듈에서 분리해서 적용할 수 있다.
 - - 그러니까, 보통의 객체지향 코딩은 위에서부터 아래로 차례대로 컴파일러가 읽어가며 코드를 수행하지만, 이 AOP는 관점지향프로그래밍이 가능해서 중간중간 로그인과같이 중요한 보안사항을 처리해야하는 기능들을 수행하고 싶을 때, 옆에서 치고 빠지는게 가능하다. 한 마디로, 위에서 아래로 흐르는 폭포가 있다면 폭포 '옆'에 서있는 관리자가 옆에서 중요한 사항들을 하나씩 폭포수에 찔러넣기가 가능하다는 뜻.
 
 4.  POJO(Plain Old Java Object)지원. 스프링 컨테이너에 저장되는 자바객체는 득정한 인터페이스를 구현하거거나, 특정 클래스를 상속 받지 않아도 된다. 즉, 기존의 자바 함수와 자바내장 클래스들 모~두 사용가능하단 얘기.
 5.  트랜잭션 처리를 위한 일관된 방법을 지원. JDBC, JTA등 어떤 트랜잭션을 사용하던 설정을 통해 정보를 관리하므로 트랜잭션 구현에 상관없이 동일한 코드 사용가능
 6.  영속성(persistence)과 관련된 다양한 API 지원. Spring은 MyBatis, Hibernate 등 데이터베이스 처리를 위한 ORM(Object Relational Mapping) 프레임워크들과의 연동 지원

### Spring 프레임워크를 구성하는 기능 요소
---
![스프링프레임워크기능요소](https://user-images.githubusercontent.com/30023840/53680170-e0b65300-3d1a-11e9-85ac-521c59e80b35.JPG)
 - core컨테이너:
 - - spring프레임워크의 기본기능을 제공한다.
 - - 이 모듈에 있는 BeanFactory는 스프링 기본 컨테이너이면서 스프링 BI의 기반이다.\
 - AOP:
 - - AOP 모듈을 통해 Aspect 지향 프로그래밍을 지원한다.
 - - AOP모듈은 스프링 애플리케이션에서 Aspect를 개발할 수 있는 기반을 지원한다.
 - ORM:
 - - MyBatis, Hibernate, JPA 등 널리 사용되는 ORM 프레임워크와의 연결고리를 제공한다.
 - - ORM 제품들을 Spring의 기능과 조합해서 사용할 수 있도록 해준다.
 - DAO:
 - - JDBC에 대한 추상화 게층으로 JDBC 코딩이나 예외처리 하는 부분을 간편화 시켰으며, AOP 모듈을 이용해 트랜잭션 관리 서비스도 제공한다.
 - WebMVC:
 - - Mdodel, View, Controlller의 약어. 사용자 인터페이스가 애플리케이션 로직과 분리되는 웹 애플리케이션을 만드는 경우에 일반적으로 사용되는 패러다임이다.


# STS소개 및 제공하는 기능
---

### STS(Spring Tool suite)
---
![spring_1](https://user-images.githubusercontent.com/30023840/53681731-11a18280-3d31-11e9-95e9-4a1f605a91ff.JPG)

 -  sprimg 개발업체인 SpringSource가 직접 만들어 제공하는 이클립스의 확장판으로 최신 이클립스를 기반으로 주요한 spring지원 플러그인과 관련된 도구를 모아서 Spring개발에 최적화 되도록 만들어진 IDE이다.

### STS가 제공하는 기능
---

1. Bean클래스 이름 자동완성(완전,, 꿀기능 프젝 할때 왜 자동완성 되나 했더니 STS덕분이었구나...)<br>현재 프로젝트의 모든 Source와 라이브러리, JDK안의 모든 클래스중에서 첫 글자가 SDD로 시작하는 클래스를 자동으로 보여줌
![spring_2](https://user-images.githubusercontent.com/30023840/53681732-123a1900-3d31-11e9-95b4-4a886e1908e3.JPG)<br><br>

2.  xml 설정 파일초기 생성시 생성 위저드 제공<br> Bean 설정파일 생성 위저드중 사용할 Namespace와Schema 버전을 선택하는 화면을 제공
![spring_3](https://user-images.githubusercontent.com/30023840/53681733-123a1900-3d31-11e9-8ec1-84ddac3d860c.JPG)<br><br>

3. Bean 의존관계 그래프<br>Spring IDE는 XML 설정파일을 읽어서 자동으로 그래프 그려줌<br>각 Bean이 어떻게 참조되고, 어떤 Property를 갖는지 알 수 있음

![spring_4](https://user-images.githubusercontent.com/30023840/53681734-123a1900-3d31-11e9-8a4d-6f6746f78a01.JPG)<br><br>

4. AOP적용 대상 표시<br> Spring IDE의 XML 설정파일 편집기를 이용하면 AOP의 적용대상을 손쉽게 확인할 수 있다.
![spring_5](https://user-images.githubusercontent.com/30023840/53681735-12d2af80-3d31-11e9-958a-0f260e7536c8.JPG)<br><br>

# Maven과 Library 관리
---
### Maven?
---

 - http://maven.apache.org 라이브러리 관리 + 빌드 툴
 - 편리한 Dependent Library 관리가 가능하고 여러 프로젝트에서 프로젝트 정보나 jar파일들을 공유하기 쉬우며 모든 프로젝트의 빌드 프로세스를 일관되게 가져갈 수 있음
 - 한마디로 pom.xml에 서술하는거만 편집하면 maven의존성 라이브러리 관리가 가능! 저장 하면 바로 빌드까지 됨.

### pom.xml?
---

 - Maven 프로젝트를 생성하면 pom.xml 파일이 생성된다.
 - pom.xml 파일은 Project Object Model 정보를 담고 있다.
 - ![pom_1](https://user-images.githubusercontent.com/30023840/53681846-76111180-3d32-11e9-9c0c-5b0bdab6883f.JPG)
<br>
### Pom.xml에 의존관계(디펜던시) 추가하는 법!(핵간단)
---

- http://mvnrepository.com 접근한다.
- org.springframework로 검색한다.
- spring-jdbc 모듈과 spring-web 모듈을 추가한다.(이외에도 아주 다양한 모듈 및 api  추가가능 ex.구글에서제공하는 json모듈이라던가, 다양한 모듈등!)<br><br>
- ![pom_2](https://user-images.githubusercontent.com/30023840/53681847-76111180-3d32-11e9-8f6e-6c9bdbaa8755.JPG)<br><br>
- 그리고 아래와 같이 추가된 디펜던시 목록이 확인 가능하고 하이어라키(어떤 상하관계 구조로 이루어져있나) 확인 가능하다.
![pom_3](https://user-images.githubusercontent.com/30023840/53681845-75787b00-3d32-11e9-8935-7c0ece6dc209.JPG)<br><br>


# 스프링 프로젝트 시작해볼까?
---

핵간단하니까, 글로만 서술해보도록 하겠음. 이클립스 기준으로,<br>
- Java Project -> Convert to Maven Project -> Add Spring Project Nature
- pom.xml 파일에 dependency 추가 (필요한 모듈들은 죄다 추가하시길! 구글검색하면서, 내가 원하는 어떠한 웹앱을 만들때 반드시 어떠한 모듈등이 필요하다~하면, 대부분 <a>https://mvnrepository.com</a>여기에 다 있음. 찾아서 복붙하면 됨.)