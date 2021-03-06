##### 플랫폼(Platform)

- <u>자신의 시스템을 개방해</u> 개인, 기업 <u>모두 참여해 원하는 일을 할 수 있도록 환경을 구축해 가치와 혜택을 제공하는 시스템이다.</u>
- <u>소프트웨어의 가동을 위해 하드웨어, 소프트웨어, 네트워크 등이 결합되어 있으며, 제작된 소프트웨어를 실행시키면 언제나 쉽게 구동 가능하다.</u>
- ex) 클라우드 플랫폼, 앱스토어 모바일 플랫폼, 검색 포탈, 빅데이터 플랫폼 하둡



##### 플랫폼의 종류

| 종류              | 설명                                                 | 예시                                        |
| ----------------- | ---------------------------------------------------- | ------------------------------------------- |
| 하드웨어 플랫폼   | 표준기술을 통해 다양한 제품을 만들 수 있는 기술 도구 | x86서버, 메인프레임, 데스크타               |
| 소프트웨어 플랫폼 | 소프트웨어를 쉽게 개발 및 구동하기 위한 기술 도구    | 리눅스, 윈도우, 자바, 닷넷, ios, 안드로이드 |
| 서비스 플랫폼     | 다양한 서비스를 제공할 수 있는 기술 환경             | 페이스북, 인스타그램, 트위터 등             |



##### 현행 시스템 파악

1. <u>구성/기능/인터페이스 파악</u>

- 시스템 구성 현황 파악
- 시스템 기능 파악
- 시스템 인터페이스 현황 파악

2. <u>아키텍처 및 소프트웨어 구성 파악</u>

- 아키텍처 파악
- 소프트웨어 구성 파악

3. <u>하드웨어 및 네트워크 구성 파악</u>

- 시스템 하드웨어 현황 파악
- 네트워크 구성 파악



##### 현행 시스템 파악 및 목표 시스템 정의 절차 및 산출물

1. 현행 시스템 분석

   1. 형행 시스템의 구성, 기능, 인터페이스 현황 파악 단계

      - 산출물 : 현행 시스템 분석서, 현행 시스템 기능 정의서, 현행 인터페이스 현황 정의서

   2. 현황 시스템의 아키텍쳐 및 소프트웨어 구성 현황을 파악하는 단계

      - 산출물 : 현행 시스테 아키텍처 구성도, 현행 소프트웨어 구성도

   3. 현행 시스템의 하드웨어 및 네트워크 구성 현황을 파악하는 단계

      - 산출물 : 현행 하드웨어 구성도, 현행 네트워크 구성도

      

2. 목표시스템 아키텍처 선정

   - 목표 시스템의 소프트웨어 및 시스템 아키텍처 정의

   - 아키텍처 평가

     - 산출물 : 소프트웨어 아키텍처 정의서, 시스템 아키텍처 정의서, 아키텍처 평가 결과서

     

3. 목표시스템 개발표준 정의

   - 목표시스템 모델링 표준 정의
   - 프로그램 표준 정의
   - 개발환경 표준 정의
     - 산출물 : 모델링 표준 정의서, 프로그램 표준 정의서, 개발환경 표준 정의서



##### 인터페이스(Interface)

애플리케이션 소프트웨어를 <u>상호 연계하고 통합하기 위해 다양한 프로토콜이 사용</u>된다.



##### 주요 연계 프로토콜 기술

- <u>X.25</u>
  - DTE(Data Terminal Equipment)와 DCE(Data Circuit-terminating Equipment)간 인터페이스를 제공하는 프로토콜
  - <u>두 단말 장치가 패킷 교환망을 통해 패킷을 원활히 전달</u>
- <u>OpenAPI</u>
  - <u>결합도를 낮추면서 애플리케이션 소프트웨어를 구축하고, 통합을 위해 정의된 프로토콜 세트</u>
  - <u>공개된 애플리케이션 프로그래밍 인터페이스</u>를 의미
- <u>Json</u>
  - <u>속성-값 또는 키-값 쌍으로 이루어진 데이터 오브젝트를 전달하기 위해 사람이 읽을 수 있는 텍스트를 사용하는 개방형 표준 포맷</u>
- <u>DB Link</u>
  - 데이터를 연계하려는 <u>DB 시스템 간 직접 연결을 통해 데이터를 연계</u>



##### 요구사항 도출

사용자들로부터 제시되는 추상적 요구에 대해 관련 전보를 식별하고 수집해 구체적 요구사항으로 표현하는 활동

요구공학 개발의 도출 과정의 활용 기법

| 도출기법                      | 설명                                                         |
| ----------------------------- | ------------------------------------------------------------ |
| 인터뷰                        | 요구사항을 도출한 사용자를 대상으로 인터뷰 수행, 회의록 작성 필수, 녹음 및 반복 청취 |
| 관찰                          | 개인의 업무처리 방법이나 절차에 대해 직접적으로 관찰하는 방법으로 요구사항을 명확히 설명하기 힘들 때 사용하는 방법 |
| <u>프로토타입(Prototypes)</u> | 요구사항에 대해 이해하기 위해 <u>기본적인 기능만 빠르게 구현해 사용자로부터 피드백을 받는 기법</u>, 개발자의 아이디어를 <u>사용자로부터 조기에 피드백 받고자 할 때 사용</u>, 프로토타이핑 전용 언어로 <u>모의 사용자(Mock-up) 인터페이스 만들어 사용</u> |
| 벤치마킹(Benchmarking)        | 경쟁 제품, 성공 사례 및 업무 절차를 참조해 유사한 수준의 효과를 낼 수 있는 기능 요구 사항 정의 |
| <u>사용자 스토리텔링</u>      | <u>사용자의 요구사항을 이야기 형식으로 기술</u>해 자연스럽게 개발자가 요구사항에 대한 이해가 가도록 구성하는 기법, <u>애자일 방법</u>에서 주로 사용, <u>개발자와 사용자의 대화로 요구사항 함께 만들어감</u> |
| 문헌조사                      | 유사 프로젝트 및 업무 문서나 양식을 조사해 현재 시스템 정보에 대한 이해 도출, 그 외산업 및 기업 표준과 관련 정부 정책, 규제 등 문서 조사, 개발팀은 도메인 영역 교육이나 설명서 참고 |
| 업무절차 및 양식조사          | 업무 관련 문서, 절차, 양식, 운영 매뉴얼 등을 조사함으로써 업무절차와 처리 입출력의 이해, 기업 내부 표준을 검토함으로써 요구와 제한 사항을 찾아 시스템 분석서의 제한 사항으로 적용 |
| 설문                          | 이해당사자들로부터 요구를 찾는 도구, 이해당사자들을 의사결정 과정에 포함해 관심, 내부 정보, 개선 의견을 이끌어냄 |
| 브레인스토밍                  | 여러명으로부터 정보를 얻는 효과적 방법, 인터뷰와 같이 수행하면 더 많은 정보 추출이 가능하며 훈련된 요원의 주재로 과정을 정동하는 것이 성공의 키 포인트, JAD(joint Application Development) : 사용자와 개발자가 공동참여해 프로토타입 기반의 작업을 수행함으로써 비즈니스 요구사항을 명확히 도출하고 그에 따라 시스템 설계 및 개발 |



#####  JAD(joint Application Development)

<u>사용자와 개발자가 공동참여해 프로토타입 기반의 작업을 수행</u>함으로써 비즈니스 요구사항을 명확히 도출하고 그에 따라 시스템 설계 및 개발



##### 요구공학

- 요구공학(Requirements Engineering)이란 <u>시스템 요구사항 문서를 생성, 검증, 관리하기 위해 수행되는 구조화된 활동의 집합이다.</u>

- 요구공학의 목적은 <u>이해관계자 사이에 효과적인 의사소통 수단 제공, 요구사항에 대한 공통 이해를 설정한다.</u>
- <u>요구사항 손실 방지 및 에러 감지로 불필요한 비용을 절감하고, 요구사항 변경 추적을 가능하게 한다.</u>

- <u>요구사항 정리</u> 느낌, 요구사항 관리 어려움 때문에 등장한 문제해결 방안



##### 요구공항 프로세스

요구공학의 프로세스는 <u>요구사항 개발</u>과 <u>요구사항 관리</u>로 구성된다.



##### 요구공학 개발 절차

1. <u>**타**당성 조사</u>

   - <u>시스템 구축, 가능성 평가</u>: 비용, 일정, 기술, 법률 제약 사항
   - 기법 : 질문지, SWOT분석

2. <u>**도**출(Elicitation)</u>

   - <u>소프트웨어가 해결해야 할 문제를 이해하고 요구사항이 어디에 있고, 어떻게 수집할 것인가와 관련되어 있다.</u>
   - 기법 : 인터뷰, 포커스 그룹, 집단 창의력 기법, 설문조사, 관찰, 문헌조사, 프로토타입, 벤치마킹, 사용자 스토리텔링

3. <u>**분**석(Analysis)</u>

   - <u>요구사항들 간의 상충을 해결하고, 소프트웨어의 범위를 파악하며 소프트웨어가 환경과 어떻게 상호작용하는지 이해함</u>

   - 기법 : 구조적 분석 - DFD(Data Flow diagram), Data Dictionary, mini Spec, ERD /

     ​           유즈케이스 기반 분석 - UML, 모델링

4. <u>**명**세(Sepcification)</u>

   - 체계적으로 검토, 평가, 승인될 수 있는 <u>문서를 작성</u>하는 것을 의미함

   - 기법 : ER 모델링, FSM(Finite State Machine), SADT(구조적 분석과 디자인 기술)

     ​           SRS, IEEE std 830-1998

5. <u>**확**인/검증(Validation/Verification)</u>

   - <u>분석가가 요구사항을 이해했는지 확인(Validation)</u>이 필요하고, <u>요구사항 문서가 조직의 표준에 부합하고 이해 가능한지, 일관성 있고 완전한지 검증(Verification)</u>이 중요함

   - 기법 : <u>Verification(검증) - 소프트웨어개발 라이프 사이클 각 단계의 산출물이 이전 단계에서 설정된 개발 규격과 요구들을 충족시키는 지의 여부를 판단하기 위한 활동이다.</u>

     ​           <u>Validation(확인) - 소프트웨어개발 라이프사이클의 각 단계의 산출물이 최초 사용자 요구 또는 소프트웨어 요구에 적합한지 입증하기 위한 활동</u>



##### HIPO(Hierarchy Input Process Output)

- <u>HIPO는 하향식(Top-Down) 소프트웨어 개발을 위한 문서화 도구이다.</u> 기능과 자료의 읜존관계를 동시에 표현 가능해 보기 쉽고 이해하기도 쉽다. 시스템을 표현하는 모듈을 계층적으로 나타내고 각 모듈들을 문서화하기 위해 사용되어 왔다.
- Input-Process-Output으로 이루어진 모듈을 계층적으로 나타낸 도표이다.
- ex) 온라인 쇼핑몰의 가지에 회원, 제품목록 -  제품 검색, 추천 상품, 장바구니 - 주문 - 결제... 등처럼 트리 형식으로 나타낼 수 있다.



##### HIPO 도표 구성

| 도효 유형                                    | 설명                                                         |
| -------------------------------------------- | ------------------------------------------------------------ |
| <u>가시적 도표(Visual Table of Contents)</u> | 시스템의 전체적인 기능과 흐름을 보여주는 Tree 형태의 구조도  |
| <u>총체적 도표(Overview Diagram)</u>         | 프로그램을 구성하는 기능을 기술한 것으로 입력, 처리, 출력에 대한 전반적인 정보를 제공하는 도표 |
| <u>세부적 도표(Detail Diagram)</u>           | 총체적 도표에 표시된 기능을 구성하는 기본 요소들을 상세히 기술하는 도표 |



##### CASE(Computer Aided Software Engineering) - 자동화 도구

- CASE 도구 활용은 <u>구조화된 요구사항 명세서에 대해서는 자동화된 일관성 분석을 제공</u>하는 CASE 도구 활동 가능하다.
- 대규모 개발 프로젝트에서는 다양한 이해관계자들이 요구사항 명세서를 검토해야 하고, 요구 사항 명세서에 대해 형상관리를 수행해야 하기 때문에 <u>요구사항 관리 툴</u>을 이용한다.



##### CASE(Computer Aided Software Engineering)

- Diagram 작성 도구 :  소프트웨어 명세서 정의, 설계 결과의 표현
- 설계 분석기 : 설계 명세서의 정확성, 일치성, 모호성에 대한 검사
- 코드 생성기 : 명세서로부터 프로그래밍 언어로 된 모듈의 코드 생성
- Repository : CASE 도구의 중심, SDLC동안 정보를 저장
- 프로젝트 관리 지원도구
- 재 공학 도구 : 기존시스템의 설계 명세서 작성 지원
- Prototyping 도구 : 초기 UI 작성 지원



##### CASE 도구의 분류

| 분류        | 내용                                                         |
| ----------- | ------------------------------------------------------------ |
| Upper CASE  | 계획 수립, 요구분석, 기본설계 단계를 지원하고 이를 다이어그램으로 표현 |
| Middle CASE | 새 설계 작업을 지원하며 화면, 출력 등의 작성을 지원          |
| Lower CASE  | 시험, 유지보수 작업을 지원하며 소스코드와 시스템 명세서를 획득 |
| I-CASE      | 위 세 가지를 통합한 것으로 Rational ROSE, COOL 등이 국내에서 사용 중이다. |



##### 요구사항 검토(Requirements Review)

<u>요구 사항 검토는 요구 사항 검토 담당자들이 요구사항 명세서를 수작업으로 분석하는 방법</u>으로 요구사항 명세서에 오류는 없는지, 불명확한지, 표준을 준수했는지 등을 검토한다. 검토방법은 동료 검토와 워크스루, 인스펙션 등이 활용된다.



##### 요구사항 검토(Requirements Review) 방법

| 구분                           | 내용                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| <u>동료 검토(Peer Review)</u>  | 2-3명이 진행하는 리뷰의 형태, 요구사항 명세서 작정자가 설명하고 이해관계자들이 설명을 들으면서 결함을 발견하는 형태로 진행 |
| <u>워크 스루(Walk Through)</u> | 소프트웨어 <u>시스템 개발 단계마다 실시하는 비정형 검토 회의, 오류를 조기에 검출하는 데 목적을 두고 리뷰를 통해 오류를 검출하고 문서화</u>함. |
| <u>인스펙션(Inspection)</u>    | 소프트웨어 요구, 설계, 원시 코드 등의 <u>저작자 외의 다른 전문가 또는 팀이 검사해 오류를 찾아내는 공식적 검토 방법, 소프트웨어의 품질을 높이는 방법</u> 중 하나이다. |



##### 요구사항 정의

- 시스템에서 제공해야 할 특정 기능을 기능적 요구사항(Functional Requirement)으로 정의한다.
- 기능 요구사항은 "요건에 대한 시스템의 행동", "시스템이 동작하는 내용에 대해 정의한 것" 등 시스템의 기능과 관련된 요구사항을 의미한다. 기능과 관련된 요구사항 외의 기타 요구사항을 모두 비기능 요구사항이라고 한다.
- 요구사항은 기능적 요구사항과 비기능 요구사항으로 구분된다.



##### 기능적 요구사항(Functional Requirement), 비 기능적 요구사항(Non-functional Requirement)

- 기능적 요구사항 - 시스템에서 제공되어야 할 특정 기능을 정의함
  - <u>데이터 모델 : 개념적인 모델의 상태를 구체화</u>한 것으로 생성, 삭제 등의 <u>실행을 정의함</u>
  - <u>데이터 흐름 처리 모델</u> : <u>시스템 행위가 어떻게 이루어지는가를 표현</u>, 데이터 모델의 입출력이 데이터의 일부분으로 사용함
  - <u>프로세스 모델</u> : <u>병행, 상호작용, 다른 프로세서들 간의 동기화 등의 사건과 활동을 서술함</u>

- 비기능적 요구사항 - 시스템의 전체적 품질이나 기능적 요구사항의 구현 시 고려해야 하는 제약사항
  - <u>SW뿐만 아니라 시스템 전체에 대한 요구사항</u>
  - <u>성능 : 응답 속도, 자원사용량</u>
  - <u>보안 : 침입 대응, 사용자 인증/권한</u>
  - <u>아키텍처 : 확장성, 유연성</u>
  - <u>안정성 : 장애대응, 서비스 연속성</u>

- 요구사항 명세화의 성공 요소는 기능 요구사항과 비기능 요구사항에 대해 명확한 표현, 일관된 용어 및 간결한 표현을 사용해 작성하고 추적이 가능하도록 관리하는 것이다.



##### 객체지향 프로그래밍(OOP, Object Oriented Programming)

- 여러 개의 독립된 단위, 즉 "객체"들의 모임으로 파악하고자 하는 것이다. 각각의 객체는 메시지를 주고받고, 데이터를 처리할 수 있다.
- 프로그램을 유연하고 변경이 용이하게 만들기 때문에 대규모 소프트웨어 개발에 많이 사용된다. 프로그래밍을 배우기 쉽게 하고 개발과 보수를 간편하게 하기 때문에 직관적인 분석을 가능하게 하는 장점도 있다.



##### 객체지향의 구성요소

- <u>클래스(Class)</u>
  - <u>같은 종류의 객체들의 집합에 공통된 속성(Attribute), 행위(Behavior)를 정의함</u>
  - <u>객체지향 프로그램의 기본적인 사용자 정의 데이터형이다.</u>
- <u>객체(Object)</u>
  - <u>클래스의 인스턴스(실제로 메모리상에 할당된 것)</u>
  - <u>자신 고유의 데이터(Attribute)를 가지며 클래스에서 정의한 행위(Behavior)를 수행함</u>
- <u>속성(Attribute)</u>
  - <u>객체의 데이터</u>
- <u>메소드(Method)</u>
  - <u>객체의 행위(함수, 메소드)</u>
  - <u>클래스로부터 생성된 객체를 사용하는 방법임</u>
- <u>메시지(Message)</u>
  - <u>객체 간의 통신을 말한다.</u>



##### 객체지향의 특징

- <u>캡슐화(Encapsulation)</u>
  - 속성(데이터)와 메소드(연산)을 하나로 묶어서 객체로 구성
  - Readability(가독성) 향상 : 유지보수 용이
  - 재사용성이 높은 SW 개발 가능
  - 정보은닉으로 내부자료의 일관성 유지(외부에서 집적 접근하면 안 되고 함수를 통해서만 접근 가능하므로 은닉화도 효력이 나타남)
  - 객체 간 인터페이스 이용, 종속성을 최소화
- <u>추상화(Abstraction)</u>
  - 공통 성질을 추출해 수퍼클래스로 구성(공통의 속성, 기능을 묶는 것)
  - 객체 중심의 안정된 모델을 구축
  - 현실 세계를 자연스럽게 표현
  - 분석의 초점이 명확하짐

- <u>다형성(Polymorphism)</u>
  - 동일한 이름의 여러 오퍼레이션(메소드)을 다른 사양으로 정의 가능
  - 오버로딩 : 매개변수의 수 또는 타입을 달리해 구분(같은 이름 함수를 다르게 선언)
  - 오버라이딩 : 부모클래스의 메소드를 재정의(부모 클래스의 메소드를 동작 방법을 변경해 재정의)

- <u>정보은닉(Information Hiding)</u>
  - 캡슐화된 항목을 다른 객체로부터 숨김
  - 메시지 전달에 의해 다른 클래스 내의 메소드가 호출된다
- <u>상속성(Inheritance)</u>
  - 부모 클래스의 속성과 메소드를 상속받아 사용함
  - 부모와 자식 클래스 간의 관계가 수퍼 클래스와 서브 클래스로 유지된다
  - 부모 클래스는 추상적이며, 자식 클래스는 구체적 성질을 가짐(ex)생물 - 동물 - 포유류...)



##### 자료 흐름도(DFD : Data Flow Diagram)

- <u>자료 흐름도는 시스템의 처리 과정을 자료의 흐름에 중점을 두어 기술하는 분석용 도구</u>이다.
- <u>시각적으로 업무와 데이터의 흐름을 쉽게 볼 수 있어 프로그램 구현에 도움이 된다.</u>
- 구성요소는 프로세스, 자료 흐름, 자료 저장소, 단말로 이루어져 있으며 입출력 데이터와 저장소의 자료흐름을 표현한다.
- 작성 시 시스템 레벨별로 단계적 상세화하며 자료흐름의 일관성을 유지해야 한다.



##### 자료 흐름도의 구성요소

- <u>Process(프로세스)</u> - 자료의 처리, 변환 과정을 표현한다. 원 안에 프로세스의 이름을 적어 표기한다.
- <u>Data Flow(자료흐름)</u> - 자료의 흐름을 표현한다. 화살표 위에 자료이름을 작성해 표현한다.
- <u>Data Store(자료 저장소)</u> - 파일, 데이터베이스 등 저장소의 위치를 표현한다. 위 아래의 수평선 사이에 저장소 이름을 작성해 표현한다.
- <u>Terminator(단말)</u> - 자료의 출처와 도착지를 표현한다. 사각형 안에 단말 이름을 적어 표현한다.



##### 자료사전(DD: Data Dictionary)

- 자료 사전은 자료 흐름도의 대상이 되는 모든 자료에 대한 기본 사항들을 더 자세히 정의하기 위히 사용되는 도구로, 메타 데이터라고도 한다.
- 자료흐름을 구성하는 자료항목, 자료에 대한 의미, 자료저장소를 구성하는 자료항목, 자료원소의 단위 및 값을 가지고 있다.



##### 자료 사전 작성 규칙

| 기호   | 의미                               |
| ------ | ---------------------------------- |
| =      | 자료의 정의(A는 ~로 구성되어 있다) |
| +      | 자료의 연결(A와 B로 연결)          |
| ()     | 자료의 생략(없어도 되는 자료)      |
| [ \| ] | 자료의 선택(A이거나 B)             |
| {}     | 자료의 반복                        |
| **     | 자료의 설명                        |

ex)

고객파일 = *구성은 주민등록번호에 따라 순차적임\* = {주민등록번호 + 고객명세 + 고객신용 + {입금상황}}

입금방법 = [현금 | 수표 | 신용카드]



##### 클라우드 컴퓨팅(Cloud Computing)

클래우드 컴퓨팅은 <u>네트워크를 통해 가상화된 컴퓨터의 시스템 리소스(IT 리소스)를 요구하는 즉시 서비스 형태로 제공하는 방식</u>으로 제공방식에 따라 <u>IaaS, PaaS, SaaS</u>로 구분됩니다.



##### 클라우드 컴퓨팅 서비스 유형

| 서비스 유형                    | 제공기능                     | 설명                                                         |
| ------------------------------ | ---------------------------- | ------------------------------------------------------------ |
| Iaas(Infra as a Service)(host) | 인프라 서비스                | 가상화 기술, 네트워크 기술을 통해 물리적인 컴퓨팅 자원을 분할, 통합, 관리하는 가상머신(Virtual machine) 환경 서비스 제공 |
| PaaS(Platform as a Service)    | 플랫폼제공서비스             | 가상 운영체제, 프로그래밍 언어 실행환경, 데이터베이스, 웹 서버 등 자원 및 개발도구 제공 |
| SaaS(Service as a Service)     | 온디맨드(on-demanded) 서비스 | 클라우스 상에서 으용 소프트웨어와 데이터베이스 등을 제공, 구글 Docs, 네이버 클라우드, Dropbox 등 |



##### 객체 지향 분석 방법론

- 객체 지향 분석은 <u>사용자 요구사항을 분석해 요구되는 사항과 관련된 모든 객체, 클래스와 연관된 속성, 연산, 관계 등을 정의해 모델링하는 작업</u>이다.
- 럼바우(Rumbaugh), 부치(Booch), Coda, Yourdon, Wirfs-Borck 방법 등이 있다.



##### Rumbaugh(럼바우) 방법론 (OMT, Object Modeling Technique)

- <u>가장 일반적으로 사용되는 방법</u>으로 <u>분석 활동을 객체모델, 동적모델, 기능모델로 나누어 수행하는 방법으</u>로 <u>모든 소프트웨어 구성 요소를 그래픽 표기법으로 활용해 모델링하는 기법</u>이다.
- 모든 소프트웨어의 구성 요소를 <u>그래픽 표기법으로 객체를 모델링</u>해 시스템개발의 전 단계가 추상화, 캡슐화, 상속성 등 일관된 객체지향개념이 적용되는 객체지향 개발 방법이다.
- 분석 절차는 <u>객체모델링</u>-<u>동적모델링</u>-<u>기능모델링</u> 순으로 진행된다.



##### 럼바우 방법론의 분석절차

| 순서 | 분석 활동                            | 내용                                                         |
| ---- | ------------------------------------ | ------------------------------------------------------------ |
| 1    | <u>객체모델링(Object Modeling)</u>   | <u>정보모델링</u>이라고도 하며, 시스템에서 요구되는 객체를 찾아내어 속성과 연산 식별 및 객체들 간의 관계를 규정해 <u>그래픽 다이어그램</u>으로 표시하는 모델링, 실세계 문제 영역으로 객체와 클래스를 추출해 그들 간의 관계를 연관화, 집단화, 일반화 중심으로 규명해 클래스의 속성과 연산을 함께 표현함으로써 시스템의 정적 구조를 생성 |
| 2    | <u>동적모델링(Dynamic Modeling)</u>  | <u>상태 다이어그램</u>을 사용해 시스템의 <u>행위</u>를 기술하는 모델링 |
| 3    | <u>기능모델링(Function Modeling)</u> | <u>자료흐름도(DFD)</u>를 이용, 다수의 프로세스들 간의 자료 흐름을 중심으로 처리 과정을 표현, <u>어떤 데이터를 입력하면 어떤 결과를 구할 것인지 표현</u> |



##### Booch(부치) 방법

- 요구사항 분석하는 과정에서 절차지향 프로그램으로 개발하려면 동사를 식별하고, 객체 지향 프로그램으로 개발하려면 명사를 선택하라고 했다.
- 미시적 개발 프로세스와 거시적 개발 프로세스 모두 포함해 사용한다.
- 클래스와 객체 분석, 식별, 클래스의 속성과 연산을 정의한다.
- 클래스와 객체의 의미를 식별, 클래스와 객체들의 관계를 식별, 클래스와 객체 구현
- 각 작업에 대한 다이어그램, 클래스 계층 정의, 클래스들의 클러스터링 작업 수행
- <u>유스케이스</u>를 강조해 사용하는 분석 방법



##### Coad, YourDon(코드-요든) 방법

객체지향 분석 방법론 중 <u>E-R 다이어그램</u>을 사용해 객체의 행위를 모델링하며, 객체 식별, 구조 식별, 주제 정의, 속성과 인스턴스 연결 정의, 연산과 메시지 연결 정의 등의 과정으로 구성되는 것.



##### Wirfs-Brock(워프스-브록) 방법

분석과 설계 간의 구분이 없고 고객 명세서를 평가해서 설계 작업까지 <u>연속적으로 수행하는 기법</u>이다.



##### UML(Unified Modeling Language)

객체 지향 소프트웨어 개발과정에서 <u>산출물을 명세화, 시각화, 문서화할 때 사용되는 모델링 기술과 방법론을 통합해 만든 표준화된 범용 모델링 언어</u>이다.



##### UML(Unified Modeling Language)의 특징

- <u>가시화 언어</u> : 개념 모델 작성 시 오류가 적고 의사소통을 용의하게 한다.
- <u>구축 언어</u> : 다양한 객체지향 프로그램 언어로 변환 가능(순공학, 역공학)하다.
- <u>문서화 언어</u> : 시스템에 대한 평가, 통제, 의사소통 문서이다.
- <u>명세화 언어</u> : 단순 표기법이 아닌 구현에 필요한 개발적 요소 및 기능에 대한 명세를 제공한다.



##### UML(Unified Modeling Language)의 구성요소

| 구성                     | 내용                                                         |
| ------------------------ | ------------------------------------------------------------ |
| View                     | 모델화된 시스템의 서로 다른 모형 제공                        |
| Diagram                  | View의 내용을 나타내기 위한 9가지 다이어그램 제공            |
| 모델 요소(Model Element) | 객체지향 개념을 표현하기 위해 사용되는 요소. 클래스, 속성, 오퍼레이션으로 구성 |
| General Mechanism        | 모델 요소에 대해 주석 정보와 의미 제공                       |



##### UML 관계의 종류

| 클래스 간 관계 | 설명                                                         | 표기법                                                       |
| -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 의존관계       | 연관관계와 같이 한 클래스가 다른 클래스에서 제공하는 기능을 사용할 때 나타내면, 연관관계와 차이점은 두 클래스의 관계가 한 메소드를 실행하는 동안과 같은 매우 짧은 시간만 유지된다. | 점선 화살표 : class A의 메소드가 class B를 메소드의 인자로 받는 등 사용(dependency) |
| 연관관계       | 클래스들이 개념상 서로 연결됐음을 나타내며, 보통 한 클래스가 다른 클래스에서 제공하는 기능을 사용하는 상황일 때 표시한다. | 실선 or 화살표 : class A가 class B를 멤버변수로 가지고 있고 사용하는 경우(association) |
| 일반화관계     | 객체지향 개념에서 상속관계라고 하며, 한 클래스가 다른 클래스를 포함하는 상위 개념일 때 이를 IS-A 관계라고 하고, UML에서는 일반화 관계로 모델링한다. | 속이 빈 화살표(-▷) : 수퍼클래스, 서브 클래스(inheritance)    |
| 실체화 관계    | 책임들의 집합인 인터페이스와 이 책임들을 실제로 실현한 클래스들 사이의 관계를 나타낸다. | 빈 삼각형과 점선(---▷) : interface A가 있고, class B가 interface A를 구현한 경우(realization) |
| 집합관계       | 클래스들 사이의 전체 또는 부분 같은 관계를 나타내며, 전체 객체의 라이프타임과 부분객체의 라이프타임은 독립적이다. 즉, 전체 객체가 사라져도 부분 객체는 남아있다. | 속이 빈 다이아몬드(-◇) : class A가 class B를 멤버변수로 가지고 있는 경우(new를 하지 않음)(aggregation) |
| 합성관계       | 클래스들 사이의 전체 또는 부분 같은 관계를 나타내며 전체 객체의 라이프 타임과 부분 객체의 라이프 타임이 의존적이다. 즉, 전체 객체가 사라지면 부분 객체도 함께 사라진다. | 속이 찬 다이아몬드(-◆) : class A가 class B를 멤버변수로 가지고 있는 경우(new로 생성)(composition) |





