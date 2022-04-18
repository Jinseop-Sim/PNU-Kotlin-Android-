# What is Android?
---
> Linux Kernel을 기반으로 제작한 모바일 운영체제  

- Software Stack 방식
- 전세계 모바일 플랫폼 시장이 7~80% 차지
- Java, Kotlin 언어를 통해 개발한다.
- Open Source Software Stack(Platform)

## Android 개요  
![image](https://user-images.githubusercontent.com/71700079/163787521-9171f566-c21d-47a3-beb0-e698f0d906ab.png)  
- Linux Kernel
  - 운영체제의 핵심 기능을 수행하는 기반 요소.
  - 하드웨어 제어 관리.
  - 다양한 하드웨어 드라이버 제공.
- HAL(Hardware Abstraction Layer)
  - 같은 종류의 하드웨어 대한 공통 명령어 집합.
  - Android Framework에서 하드웨어 기능을 이용할 수 있게 표준 인터페이스 제공.
- Native Libraries
  - Java Framework 외의 C/C++ 라이브러리 제공(e.g. Webkit, OpenMAX AL)
- ART(Android Runtime)
  - App에 대한 전체 실행을 주관
- Android Framework
  - Java로 구현된 API Framework
  - 모든 Android App이 사용하는 Toolkit
- Apps
  - Android 운영체제에 기본적으로 설치된 앱
  - 사용자가 설치한 앱
 
## Android App의 구성요소
> Application은 일반 클래스와 컴포넌트 클래스로 구성된다.  
> 일반클래스는 개발자가 정의하며, 컴포넌트 클래스는 Android가 생성한다.  

- Android 4대 Component
  - Activity : 화면을 구성하는 Component, 주로 UI담당.
  - Service : 기기의 Background에서 실행되는 작업을 처리. (e.g. 음원 재생, 데이터 송수신)
  - Content Provider : 데이터를 다른 App에 제공하는 기능을 표준화 (e.g. 카카오톡에서 갤러리 접근)
  - Broadcast Receiver : 시스템 이벤트가 발생할 때 실행되게 하는 Component(e.g. 부팅 완료, 배터리 방전)
- Component 실행 특징
  - App 내부 독립된 실행 단위
    - Component는 각각 독립적 실행 단위로, Code가 겹치지 않는다.
    - 새로운 Component 실행 시 Android System을 호출하여 실행한다.
  - Application 실행 시점의 다양성
    - ex) 메시지 수신 알림을 통해 채팅화면을 바로 실행 가능
  - Application Library 사용 가능
    - 현재 실행중인 Application에서 다른 Application을 Library처럼 이용 가능.
  
## Android의 Resource
> Android Resource란?  
> 코드에서 사용되는 추가 파일과, 정적인 Contents를 말한다.  
> 독립적인 유지관리를 위해서 코드에서 외부로 분리되어 있다.  
  
- Resource를 활용한 개발
  - 색상, 크기, 레이아웃, 이미지, 메뉴 등 많은 요소를 리소스로 등록해 쓸 수 있다.
