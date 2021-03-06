##### SJF (Shortest Job First)

- 실행 시간이 가장 짧은 작업 순으로 CPU 수행하는 비선점 스케줄링 기법
- 작업들이 준비상태 큐에 들어와 있으므로 프로세스의 대기시간은 모두 0초부터 계산한다.
- 대기시간 = 대기시간 - 제출시간
- 반환시간 = (실행 끝난 시간 + 1) - 번호



##### HRN (Highest Response-Ratio Next)

- SJF의 약점 보완 기법으로 실행시간이 긴 프로세스를 차별하고 짧은 프로세스를 지나치게 선호하는 점을 보강한 알고리즘으로 각 프로세스의 우선순위를 서비스 시간만이 아니고 서비스 대기시간도 계산하는 스케줄링 기법
- 우선순위 = (대기시간 + 서비스시간) / 서비스 시간



##### CPU 스케줄링 기법

| 구분   | 선점 스케줄링                                                | 비선점 스케줄링                                              |
| ------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 개념   | 한 프로세스가 CPU를 차지하고 있을 때 우선순위가 높은 다른 프로세스를 중지하고 자신이 CPU를 선점. 높은 우선순위를 가진 프로세스들이 빠른 처리를 요구하는 시스템에 유용 | 한 프로세스가 CPU를 차지하고 있으면, 작업 종료 후 CPU 반환 시까지 다른 프로세스는 CPU 선점 불가 |
| 개념도 | if 우선순위 P1 < P2일 때, P2가 중간에 CPU 선점 가능          | if 우선순위가 P1 < P2일 때, P2는 P1 종료 시까지 대기         |
| 장점   | 비교적 빠른 응답. 대화식 시분할 시스템에 적합                | 응답시간 예상이 용이. 모든 프로세스에 대한 요구를 공정하게 처리 |
| 단점   | 높은 우선순위 프로세스들이 들어오는 경우 오버헤드를 초래     | 짧은 작업을 수행하는 프로세스가 긴 작업 종료 시까지 대기     |
| 기법   | RR, SRT, 다단계 큐, 다단계 피드백 큐                         | FCFS, Priority, Deadline, SJF, HRN                           |
| 활용   | 실시간 응답환경, Deadline 응답환경                           | 처리시간 편차가 적은 특정 프로세스 환경                      |



##### 분산 운영 체제의 특징

분산시스템 환경에서 자원 관리와 사용자 인터페이스 기능을 제공하는 시스템 소프트웨어

| 특징                       | 설명                                                         |
| -------------------------- | ------------------------------------------------------------ |
| 자원공유(Resource Sharing) | 한 노드의 사용자와 다른 노드 사용자 간에 유용한 자원들은 공유 |
| 신뢰성 (Reliability)       | 여러 시스템 중 일부 시스템에 고장이 발생하는 경우에도 전체 시스템이 정상적으로 운영 |
| Transparency               | 보수의 컴퓨터를 마치 1대의 기계처럼 다루는 특성으로 특정 자원의 물리적인 위치를 알지 못하여도 사용 가능 |
| Expandability              | 노드들이 통신으로 상호 연결되어 수평적으로 확장              |
| 자율성 (Autonomy)          | 시스템을 구성하는 각 노드들은 각기 어느 정도의 자율성을 가진다. |



##### 교착상태

다중 프로세스 환경 하에 서로 다른 프로세스가 각자 자신이 소유한 자원을 포기하지 않고, 상대 프로세스의 자원을 무한대기하고 있는 상태



##### 교착상태 발생조건

| 원인        | 내용                                                         |
| ----------- | ------------------------------------------------------------ |
| 상호 배제   | 프로세스가 자원을 배타적으로 점유하여 다른 프로세스가 그 자원을 사용할 수 없다. |
| 점유와 대기 | 한 프로세스가 자원을 점유하고 있으면서 또 다른 자원을 요청하여 대기하고 있는 상태 |
| 비선점      | 한 프로세스가 점유한 자원에 대해 다른 프로세스가 선점할 수 없고, 오직 점유한 프로세스만이 해제 가능 |
| 환형 대기   | 두 개 이상의 프로세스 간 자원의 점유와 대기가 하나의 원형을 구성한 상태 |



##### 페이지 결함

기억장치에 적재되지 않은 페이지를 사용하는 현상

콜드 미스 : 데이터를 최초로 읽을 때 발생, 용량 미스 : 메모리 용량이 부족해서 발생

동그라미 친 숫자 -> 처음 메모리에 적재되거나 교체된 데이터 (미스)

동그라미 쳐 있지 않은 숫자는 그 전에 메모리에 적재되어 있는 데이터를 참조 (히트)



##### 가상 메모리 (가상 기억장치)

- <u>주 기억장치 안의 프로그램 양이 많아질 때 사용하지 않는 프로그램을 보조기억장치 안의 특별한 영역으로 옮겨서, 그 보조기억장치 부분을 주기억장치처럼 사용할 수 있는 영역</u>
- 당장 실행할 프로그램만 주 기억장치로 이동
- <u>물리적인 메모리 용량보다 더 큰 용량의 프로그램을 실행할 수 있도록 보조기억장치를 메모리처럼 사용할 수 있도록 하는 가상화 기술</u>



##### 가상 메모리 관리정책

| 관리정책  | 내용                                                         | 기법                           |
| --------- | ------------------------------------------------------------ | ------------------------------ |
| 할당 정책 | 각 프로세스에게 할당할 메모리의 크기를 관리. 실행 중 주기억장치 할당량 변화 알고리즘 | 고정할당 기법, 가변할당 기법   |
| 호출 정책 | 언제 어느 항목들을 보조기억장치에서 주 기억장치에 가져올 것인지 결정 | 요구호출 기법, 예측호출 기법   |
| 배치 정책 | 프로그램의 한 블록을 주기억자치의 어디에 배치할 것인가 관리  | First Fit, Best Fit, Worst Fit |
| 교체 정책 | 주기억장치에 적재할 공간이 없을 경우, 무엇과 교체할 것인가에 대한 관리 | FIFO, LRU, LFU, NUR            |



##### 메모리 인터리빙 기법

- 기억장치 모듈에 순차적인 접근을 함으로서 접근시간을 최소화하고 성능을 향상
- 중앙처리장치의 기억 모듈에 중복적인 데이터 접근을 방지하기 위해서 연속된 데이터 또는 명령들을 기억 장치 모듈에 순차적으로 번갈아 가면서 처리하는 방식
- 메모리를 복수 개의 모듈로 나누고 각 모듈에 연속적인 주소를 부여하여 동시에 접근이 가능하게 하는 기법



##### 메모리 인터리빙의 종류

- 상위 인터리빙 : 프로그램과 데이터들이 독립적이어서 각각의 기억 모듈에 젖아하는 것이 더 효과적인 다중 프로그래밍에 사용
- 하위 인터리빙 : 연속된 주소가 연속된 다수의 모듈에 동시 동작하며, 단점은 확장이 어렵고 어느 한 모듈의 오류가 전체에 영향을 미친다.
- 혼합 인터리빙 : 기억장치 모듈을 뱅크로 그룹화하고 각 그룹 내에서 하위 인터리빙하는 방식



##### 구역성 (Locality) or 지역성

- 프로그램의 어느 한 특정 부분만 한동안 집중적으로 참조하는 현상
- 메모리 계층구조(레지스터나 캐시 메모리 활용)나 데이터베이스의 LRU 알고리즘은 구역성 특징을 활용해 성능을 향상시킨 사례이다.

| 기법        | 내용                                                         | 사례                        |
| ----------- | ------------------------------------------------------------ | --------------------------- |
| 시간 구역성 | 최근에 액세스된 프로그램이나 데이터가 가까운 미래에 다시 액세스될 가능성이 높다. | Loop, Subroutine            |
| 공간 구역성 | 기억장치 내에 인접하여 저장된 데이터들이 연속적으로 액세스될 가능성이 높다. | Array, Table, 순차코드 실행 |
| 순차 구역성 | 분기하지 않는 한, 명령어들은 기억장치에 저장된 순서대로 인출되어 실행된다. (약 20%) | 구조적 프로그래밍           |



##### 세그먼테이션 기법

- 가상 기억장치 내의 프로그램과 데이터를 각 세그먼트가 주기억장치에 적재될 때마다 필요한 서로 다른 크기의 세그먼트로 분할

- 매핑 테이블(세그먼트 번호 : 주소 + 크기) 유지



##### 페이징 기법

- 가상 기억장치 내의 프로그램과 데이터를 고정되게 분할한 용량(페이지)을 주기억장치에 사상시키는 기법
- 프로그램의 실제 주소와 주기억장치 주소가 다르므로 PMT(Page Map Table) 필요
- 외부단편화 해결 가능, 내부단편화 발생



##### 페이징과 세그먼테이션 기법의 비교

| 항목     | 페이징                                                  | 세그먼테이션                                                 |
| -------- | ------------------------------------------------------- | ------------------------------------------------------------ |
| 할당단위 | 고정                                                    | 가변                                                         |
| 적재단위 | 프로그램 일부 적재                                      | 프로그램 전체 적재                                           |
| 장점     | 외부단편화가 없다. 교체시간이 짧다.                     | 코드, 데이터 공유가 용이하다. 내부단편화가 최소화된다.       |
| 단점     | Thrashing 문제 심각. 내부단편화 코드나 데이터 공유 논란 | 외부단편화가 발생. 주기억장치가 커야 한다. 교체시간이 길어진다. |



##### 로더의 단계별 동작

- Allocation (할당)
  - 정의 : 프로그램 수행에 필요한 기억장소를 할당 받는 기능
  - 방법 : 프로그램의 일부에 대한 기억장치를 할당 후 실행 시 필요한 부분만을 기억장치에 할당.
- Linking (링킹)
  - 정의 : 실행중인 여러 프로그램이 라이브러리나 특정 모듈을 공유하도록 프로그램 적재 시에 링크하는 기법.
  - 방법 : 링킹로더는 링커에 의해 제공된 목적파일의 재배치 정보를 통해 실행 가능한 코드를 만들어 주기억장치에 적재한다.
- Relocation (재배치)
  - 정의 : 프로그램 내 재배치 가능한 상대주소를 할당된 메모리의 절대주소로 변환하는 기능
  - 방법 : 목적 코드의 각 명령에 대해 재배치 여부를 명시하는 재배치 비트를 추가해 표시.
- Loading (적재)
  - 정의 : 할당, 링킹, 재배치 작업이 수행된 프로그램을 주기억장치에 적재하는 기능.
  - 방법 : 로더의 할당 방법에 의거, 필요한 기능을 수행.



##### 링커와 로더

- 링커의 역할 (목적파일 -> 링커 -> 실행파일)
  - 서로 독립적으로 작성되고 번역된 목적 프로그램을 연계시키는 시스템 프로그램으로 링커는 여러 오브젝트 파일과 라이브러리들의 Code Chunk들을 하나로 묶어 실행 가능한 한의 바이너리 파일을 생성한다. 링크 시 연결될 모듈은 사용자가 지정하거나 라이브러리로 주어진다.
- 로더의 역할
  - 외부 기억장치로부터 실행 프로그램을 주기억장치로 옮기기 위하여 메모리 할당, 연결, 재배치와 적재를 담당하는 시스템 프로그램으로 커널에 있는 로더가 실행파일과 라이브러리 파일을 <u>가상 메모리에 로딩한다.</u>



##### 프로세서 모델에 따른 분산 컴퓨팅 모델 분류

- 클라이언트 / 서버 모델
  - 비대칭적 분산 시스템구조
  - 대부분의 분산 시스템은 LAN을 기반으로 한 모델로 구성한다.
  - 자동사용자 시스템으로 사용자들 간에 CPU를 공유
  - 서버는 공유된 다양한 시스템 기능과 자원의 접근 제공
- 프로세서 풀 모델
  - 하나 이상의 프로세서 풀이 통합된 워크스테이션-서버 모델로 구성
  - 각 풀 프로세서는 서버가 연결되듯이 독립적으로 네트워크와 연결
  - 풀에 있는 프로세서들은 단일 회로 보드로 구성
  - 사용자 터미널은 단순히 시스템의 자원을 접근하는 수단을 제공
  - 사용자의 작업은 부분 혹은 전체적으로 풀 프로세서 상에서 수행
  - 사용자가 메인 태스크를 초기화하면, 풀 프로세서가 각 태스크에 할당되고 병렬로 수행
- 혼합 모델
  - 앞의 두 모델을 혼합한 시스템
  - 사용자의 요구와 자원처리가 매칭된다.
  - 병렬 수행 : 여러 개의 풀 프로세서가 과부하 처리를 실행하기 위해 할당
  - 사용자는 워크스테이션이나 터미널을 통해 시스템에 접근



##### NoSQL (Not Only SQL)

- <u>수평적 확장이 가능하며 다수 서버들에 데이터 복제 및 분산저장이 가능</u>한 데이터베이스이다.
- 최근에는 관계형 DB의 한계를 벗어나 Web2.0의 비정형 초고용량 데이터 처리를 위해 <u>데이터의 읽기보다 쓰기에 중점</u>을 둔, NoSQL이 많이 사용되고 있다.

- 특징

| 특징            | 설명                                                         |
| --------------- | ------------------------------------------------------------ |
| Schema-less     | 데이터 모델링을 위한 고정된 데이터 스키마 없이 키 값을 이용해 다양한 형태의 저장과 접근 가능. 데이터 저장 방식에는 크게 칼럼, 값, 문서, 그래프 4가지로 나뉨 |
| 탄력성          | 시스템의 일부 장애에도 불구하고 다운타임이 없도록 하는 동시에 대용량 데이터의 생성, 업데이트, 질의에 대응할 수 있도록 시스템 규모와 성능 확장에 용이하고 입출력의 부하 분산에도 용이한 구조를 갖춤 |
| 효율적 질의가능 | 수십 대에서 수천 대 규모로 구성된 시스템에서도 데이터의 특성에 맞게 효율적으로 데이터를 검색/처리할 수 있는 질의언어, 관련 처리기술, API 제공 |
| 캐싱 (Caching)  | 대규모의 질의에도 고성능 응답속도를 제공할 수 있는 메모리 기반의 캐싱기술의 적용이 매우 중요하고 개발 및 운영에서도 일관되게 적용할 수 있는 구조 |

(Ordered)(Document) Key / Value Store



##### 데이터 스키마 구조

- 데이터베이스 3단계 스키마 구조는 사용자 관점의 외부단계, 총체적인 관점의 개념단계, 물리적인 저장장치의 관점인 내부단계 등의 3단계로 구성되어 있다.



##### 데이터베이스 키

| 종류   | 설명                                                         |
| ------ | ------------------------------------------------------------ |
| 후보키 | 릴레이션을 구성하는 속성들 중에서 튜플을 유일하게 식별할 수 있는 하나 똔느 몇 개의 속성의 집합. 유일성과 최소성을 모두 만족 |
| 기본키 | 릴레이션의 유일한 식별자(유일성, 최소성 모두 만족). 기본키로 지정된 속성은 같은 값을 갖지 못함. 후보키 중에서 선정된 키로 중복값을 가질 수 없음. Not null, Unique, 외래키로 참조될 수 있음 |
| 대체키 | 후보키가 둘 이상 되는 경우에 기본키로 선택죄디 못한 후보키들. 후보키 = 기본키 + 대체키 |
| 슈퍼키 | 유일성만 있고 최소성이 없는 속성의 집합                      |
| 외래키 | 한 테이블의 키 중 다른 테이블의 튜플을 식별할 수 있는 키     |



##### ER 요소

- 개체 : 현실 세계의 객체로서 유형 또는 무형의 정보대상으로 존재하며 서로 구별될 수 있는 것을 뜻한다. 데이터베이스에서는 테이블을 의미 (직사각형)
- 관계 : 2개 이상의 개체 사이에 존재하는 연관성을 의미한다. (마름모)
- 속성 : 개체를 구성하는 각 열을 의미, 테이블의 컬럼을 지칭. (타원)
- 기본키 : 데이터베이스 테이블에서 한 튜플의 데이터 집합에서 유일하게 식별이 가능한 컬럼을 뜻한다. (타원 안의 밑줄ㅇ)



##### 데이터 독립성이 필요한 이유

- 데이터베이스에 대한 사용자 뷰와 DB의 구현 뷰를 분리해 변경에 따른 영향을 줄인다.
- 각 View의 독립성 유지, 계층별 뷰에 영향을 주지 않고 변경 가능
- 각 스키마에 따라 DDL, DML가 상이하다.
- 데이터의 저장구조와 접근기법으로부터 응용을 분리시키는 개념으로 데이터베이스 내의 데이터와 응용 프로그램이 서로 영향을 받지 않는다.
- 하위단계의 데이터 구조가 변경되어도 상위단계에 영향을 미치지 않는 속성을 의미한다.
- 이에 반하여 파일 시스템을 사용하는 응용 프로그램은 파일의 구조 변경 시 반드시 응용 프로그램 수정이 발생되어야 한다.



##### RDBMS와 NoSQL의 차이

| 구분          | RDBMS                                                   | NoSQL                                                        |
| ------------- | ------------------------------------------------------- | ------------------------------------------------------------ |
| 저장데이터    | 기업의 제품 판매정보, 고객정보 등 핵심 정보 저장        | 중요하지 않으나 데이터 양이 많고 급격히 늘어나는 정보 저장   |
| 환경 측면     | 일반적인 환경이나 분산환경 등에 사용                    | 클라우드 컴퓨팅처럼 수 천, 수 만대 서버의 분산환경           |
| CAP유형       | CA 충족                                                 | CP, AP 충족                                                  |
| 인덱스        | 복잡(관계형 모델 기반)                                  | 단순(키, 값 기반)                                            |
| 데이터접근    | SQL                                                     | NoSQL(API 이용)                                              |
| 트랜잭션 특성 | ACID                                                    | BASE                                                         |
| 경합해소      | MVCC                                                    | 경합 데이터 분산화 유도                                      |
| 조인지원      | 가능                                                    | 효율적 조인지원 불가능                                       |
| 장점          | 무결성, 정합성, 원자성, 독립성, 일관성                  | 비용적인 측면과 확장성 기준                                  |
| 분산 처리방법 | 오라클 RAC 등으로 분산처리방법                          | 페타바이트 수준의 대량의 데이터처리                          |
| 특징          | 고정된 스키마를 가지며 조인 등을 통하여 데이터를 검색함 | 단순한 키와 값의 쌍으로만 이루어져 인덱스와 데이터가 분리되어 별도로 운영됨 |
| 사용 예       | 오라클, MySQL 등                                        | 구글의 Bigtable, 아마존의 Dynamo, 트위터의 Cassandra         |

최근에 정형, 비정형 데이터를 다루기 위해 하이브리드 형태의 데이터베이스 시스템을 활용한다.



##### 데이터 독립성

- 논리적 데이터 독립성
  - DBMS가 하나의 논리적 데이터 구조를 가지고 각각의 응용 프로그램이 요구하는 다양한 형태의 논리적 구조로, 매핑 시킬 수 있는 능력을 보장할 수 있다.
  - 외부 스키마에 영향을 미치지 않으면서 개념 스키마에 적용되는 제약 조건들의 변경이 가능해야 한다.
- 물리적 데이터 독립성
  - 논리적 구조로부터 여러 형태의 물리적 구조를 지원할 수 있는 매핑 능력을 보장할 수 있다.
  - 시스템 선으을 향상시키기 위해 필요.
  - 응용 프로그램과 논리적 구조에 영향을 주지 않고, 물리적 구조를 변경 가능해야 한다.



##### ER 모델

- 개념적 설계 단계에서 사용하는 모델로서 개념적 데이터 모델의 가장 대표적인 모델.
- 피터첸에 의해 개발되었음.
- 개체, 속성, 관계 등에 대해 용이하게 표현할 수 있는 ER 도형 정의하고 있음



##### 카디널리티 (Cardinality)

- 특정 집합에 속한 원소의 수
- 릴레이션에 입력된 튜플의 수
- 한 개체가 관계를 통해 다른 개체와 관계된 개체들의 수



##### 데이터베이스 키의 특징

- 유일성
  - 하나의 키 값으로 하나의 튜플만을 유일하게 식별할 수 있어야 함
  - 기본키, 후보키, 슈퍼키
- 최소성
  - 속성의 집합인 키가 릴레이션의 모든 튜플을 유일하게 식별하기 위해 꼭 필요한 속성들로 구성된 것을 의미
  - 기본키, 후보키



##### 관계형 데이터베이스의 주요 용어

- 릴레이션 : 2차원의 테이블
- 레코드 : 릴레이션의 각 행
- 튜플 : 레코드를 좀 더 공식적으로 부르는 용어, 릴레이션의 행을 구성하는 속성 값들의 집합
- 속성 : 릴레이션에서 이름을 가진 하나의 열
- 도메인 : 한 속성이 나타낼 수 있는 값들의 집합 (속성이 가질 수 있는 값의 범위)
- 차수 : 한 릴레이션에 들어 있는 속성의 수, 유효한 릴레이션의 최소 차수는 1이며 릴레이션의 차수는 자주 바뀌지 않는다.
- 카디널리티 : 릴레이션의 튜플 수, 유효한 릴레이션은 카디널리티 0을 가질 수 있으며, 릴레이션의 카디널리티는 시간이 지남에 따라 계속해서 변함



##### 무결성

- 데이터베이스에 저장된 데이터 값과 그것이 표현하는 현실 세계의 실제 값이 일치하는 정확성을 의미한다.

- COMMIT, ROLLBACK, SAVEPOINT
- COMMIT
  - 수행된 결과를 실제 물리적 디스크로 저장
- ROLLBACK
  - 명령 수행 실패를 의미하며 수행된 결과를 원복시킴
- SAVEPOINT
  - 저장점 지정, 지정된 저장점부터 현재까지 일부만 ROLLBACK 가능



##### 참조 무결성

- 외래키의 값은 그 외래키가 기본키로 사용된 릴레이션과 참조 무결성 제약을 가진다.
- 외래키 속성은 반드시 참조되어야 한다.
- 데이터베이스의 참조 무결성은 2개의 관련 있는 테이블 간의 일관성을 보장을 의미한다.
- <u>참조되는 테이블의 행은 이를 참조하는 참조키가 존재하는 한 삭제될 수 없고, 기본키도 변경될 수 없다.</u>
- 외래키가 참조하는 개체의 기본키는 기본키이거나 NULL이어야 한다.



##### 도메인 무결성

- 특정 속성 값이 미리 정의된 규칙 내에서 데이터로 존재해야 한다.
- 테이블 내에 속성에 대한 무결성 규칙이다.
- 속성은 어느 한 도메인 상에서 정의되어야 하고, 정의된 속성은 반드시 해당 도메인으로부터만 값을 취할 수 있다.
- 도메인 무결성 규칙은 속성에 대한 무결성 규칙으로 데이터 타입과 길이뿐만 아니라 허용값, 기본값, 유일성, NULL 여부 등에 대한 업무 규칙을 의미한다.
- 동일한 속성의 값을 비교하기 위해서는 도메인 무결성이 지켜져야 한다.
- 도메인 무결성은 DEFAULT, NOT NULL 명령어로 구현할 수 있다.



##### 관계대수와 관계해석

- 관계대수
  - <u>관계형 데이터베이스에서 원하는 정보와 그 정보를 검색하기 위해서 어떻게 유도하는가를 기술하는 절차적인 언어</u>이며, 릴레이션을 처리하기 위해 연산자와 연산 규칙을 제공하는 언어로 피연산자가 릴레이션이고 결과도 릴레이션이다.

- 관계해석
  - 수학의 술어해석에 기반을 두고 있으며, 튜플 관계해석과 도메인 관계해석으로 구성되어 있으며, <u>원하는 데이터만 명시하고 질의를 어떻게 수행할 것인가는 명시하지 않는 선언적 언어이다.</u>



##### 관계대수 연산자

| 종류     | 연산자 기호 | 설명                                                         |
| -------- | ----------- | ------------------------------------------------------------ |
| Select   | 시그마      | 릴레이션에 존재하는 튜플 중에서 선택 조건을 만족하는 튜플의 부분집합을 구하여 새로운 릴레이션 생성. 릴레이션의 행에 해당하는 튜플을 구하는 것(수평연산) |
| Project  | 파이        | 주어진 릴레이션에서 속성 리스트에 제시된 애트리뷰트만 추출하는 연산. 릴레이션의 열에 해당하는 애트리뷰트를 추출하는 수직 연산자 |
| Join     | 나비모양    | 공통 속성을 중심으로 두 개의 릴레이션을 하나로 합쳐서 새로운 릴레이션을 만드는 연산 |
| Division | 나누기      | 오른쪽 피연산자의 속성을 제외한 속성만을 구하는 연산         |



##### 관계 대수의 일반집합 연산자

| 종류                      | 유형        | 설명                                                         |
| ------------------------- | ----------- | ------------------------------------------------------------ |
| 합집합 (UNION)            | 합집합 기호 | 두 릴레이션에 존재하는 튜플의 합집합을 구하되, 결과로 생성된 릴레이션에서 중복되는 튜플 제거 |
| 교집합 (INTERSECTION)     | 교집합 기호 | 두 릴레이션에 존재하는 튜플의 교집합 구하는 연산             |
| 차집합 (DIFERENCE)        | -           | 두 릴레이션에 존재하는 튜플의 차집합을 구하는 연산           |
| 교차곱 (CARESIAN PRODUCT) | X           | 두 릴레이션에 있는 튜플들의 순서쌍을 구하는 연산             |



##### 트랜잭션

- <u>트랜잭션은 데이터베이스의 상태를 변화시키기 위해서 수행하는 작업의 단위를 의미한다.</u>
- 사용자가 시스템에 대한 서비스 요구 시 시스템이 응답하기 위한 상태 변환 과정의 작업단위를 말하며 원자성, 일관성, 고립성, 영속성의 특징을 가지고 있다.
- 하나의 트랜잭션은 Commit 또는 Rollback을 완료한다.

| Commit                                                       | Rollback                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| 하나의 트랜잭션이 성공적으로 끝났고, 데이터베이스가 일관성 있는 상태에 있을 때, 하나의 트랜잭션이 끝났다는 것을 알려주기 위해 사용하는 연산 | 하나의 트랜잭션 처리가 비정상적으로 종료되어 트랜잭션의 원자성이 깨진 경우, 트랜잭션을 처음부터 다시 시작하거나, 부분적으로만 연산된 결과를 취소하는 연산 |

- 트랜잭션 상태전이도

활동 -> 부분완료 -> Commit -> 완료 -> 종료

활동 -> 실패 -> Rollback -> 철회 -> 종료



##### 트랜잭션의 특징 (ACID)

| 특성   | 설명                                                         | 기법              |
| ------ | ------------------------------------------------------------ | ----------------- |
| 원자성 | 분해할 수 없는 최소 단위. 연산 전체가 성공 또는 실패. 한 가지라도 실패할 경우 전체가 취소되어 무결성 보장 (All or Nothing) | Commit / Rollback |
| 일관성 | 트랜잭션이 실행 성공 후 항상 모순 없이 일관성 있는 DB 상태 보존 | 참조 무결성 기법  |
| 고립성 | 현재 수행 중인 트랜잭션이 완료될 때까지 트랜잭션이 생성한 중간 연산 결과에 다른 트랜잭션이 접근할 수 없음을 의미 |                   |
| 영속성 | 성공이 완료된 트랜잭션의 결과는 영구적으로 데이터베이스에 저장된다 | 회복기법          |



##### 트랜잭션의 상태 전이도

| 상태           | 설명                                                    |
| -------------- | ------------------------------------------------------- |
| 활동 상태      | 트랜잭션이 시작되어 연산들이 정상적으로 실행 중인 상태  |
| 부분 완료 상태 | 트랜잭션에 정의된 모든 연산의 실행이 끝난 상태          |
| 완료 상태      | 트랜잭션의 성공적 종료 상태                             |
| 실패 상태      | 트랜잭션이 완료되지 못하고 더 이상 실행되지 못하는 상태 |
| 철회 상태      | 트랜잭션이 실패한 후 실행되기 이전으로 복귀된 상태      |



##### 데이터베이스 장애 유형

- 데이터베이스의 장애는 DBMS 내의 논리적, 물리적 오류에 의해 트랜잭션의 ACID를 만족시키지 못하는 상태이다.

| 유형          | 내용                                                         |
| ------------- | ------------------------------------------------------------ |
| 트랜잭션 장애 | 트랜잭션 내부에서 입력 데이터 오류, 불명확한 데이터, 시스템 자원 요구의 과다 등 비정상적인 상황으로 인하여 트랜잭션 실행이 중지되는 현상. 논리적 오류 : 내부적인 오류로 태랜잭션을 완료할 수 없음. 시스템 오류 : Deadlock 등의 오류 조건으로 활성 트랜잭션을 강제 종료 |
| 시스템 장애   | 하드웨터 오동작, 정전, 소프트웨어 오류, 교착 상태 등에 의해 실행 중인 모든 트랜잭션들이 더 이상 실행을 계속할 수 없는 현상. 전원, 하드웨어, 소프트웨어 등의 고장. 시스템 장애로 인해 저장 내용이 영향 받지 않도록 무결성 체크 |
| 디스크 장애   | 저장 장치인 디스크 블록의 손상이나 디스크 헤드의 충돌 등에 의해 데이터베이스의 일부 또는 전부가 물리적으로 손상되는 현상. 디스크 스토리지의 일부 또는 전체가 붕괴되는 경우. 가장 최근의 덤프와 로그를 이용하여 덤프 이후에 완결된 트랜잭션을 재실행 (REDO) |
| 사용자 장애   | 사용자의 실수, 무결성 규정 위반 등으로 질의 실행이 실패하는 현상. 사용자들의 데이터베이스에 대한 이해 부족으로 발생. DBA가 데이터베이스 관리를 하다가 발생시키는 실수 |



##### 데이터베이스 장애 발생 시 회복의 개념과 구성요소

- 데이터베이스의 회복은 데이터베이스 트랜잭션을 실행하는 도중 장애가 발생하여 데이터베이스가 손상되었을 경우 손상되기 이전의 정상 상태로 복구하는 작업이다.

- 회복의 기본원칙 (중복)

| 기법              | 활동                 |
| ----------------- | -------------------- |
| 백업              | 데이터 중복          |
| Archive 또는 Dump | 다른 저장장치로 복사 |
| Log 또는 journal  | 변경내용 기록        |

- 회복을 위한 조치

| 기법 | 활동          |
| ---- | ------------- |
| REDO | 트랜잭션 복원 |
| UNDO | 트랜잭션 폐기 |

- 시스템

| 기법            | 활동          |
| --------------- | ------------- |
| DBMS 서브시스템 | 회복관리 기능 |



##### REDO, UNDO

- REDO, UNDO는 데이터의 무결성을 보장하는 트랜잭션의 특징 중 Durability을 위해 필요한 중요한 요소이다.
- REDO(Forward Recovery)는 <u>데이터베이스 내용 자체가 손상이 된 경우 가장 최근의 복제본을 적재한 후 이후 일어난 변경만을 로그를 이용해 재실행</u>함으로써 데이터베이스 회복 기법의 구성요소이다. REDO는 완료된 데이터를 회복하는 데 사용.
  - Archive 사본 + Log 활용
  - 파일 복사본과 로그를 이용한 전방향 회복조치
  - 완료된 트랜잭션의 장애에 대한 회복 조치로 트랜잭션의 영속성을 제공
- UNDO(Backward Recovery)는 <u>데이터베이스 내용 자체는 손상되지 않았지만 변경 중이거나 변경된 내용에 대한 신뢰성을 잃어버린 경우 모든 변경 내용을 취소</u>하여 데이터베이스 회복 기법의 구성요소이다. UNDO는 수행중인 데이터를 회복하는 데 사용.
  - Log + Backward 취소 연상 수행
  - 미완료 트랜잭션의 장애에 대한 회복 조치로 트랜잭션의 원자성 제공



##### 데이터베이스 회복 기법의 유형

| 회복기법      | 설명                                                         |
| ------------- | ------------------------------------------------------------ |
| 지연 갱신     | 트랜잭션이 성공적으로 종료될 때까지 데이터베이스에 대한 실질적인 갱신을 연기하는 기법 |
| 즉시 갱신     | 트랜잭션이 데이터를 변경하면 트랜잭션이 부분완료되기 전이라도 즉시 실제 데이터베이스에 반영하는 기법 |
| 그림자 페이지 | 갱신 이전의 데이터베이스를 일정 크기의 페이지 단위로 구성하여 각 페이지마다 복사 본인 그림자 페이지로 별도 보관해두고, 실제 페이지를 대상으로 트랜잭션에 대한 변경 작업 수행 |
| 검사점        | 체크포인트 회복기법. 시스템 장애가 발생했을 경우 검사점 이후 장애발생 이전에 완료된 경우 Undo 수행, 장애발생 시점까지 완료하지 못한 경우 Redo 수행을 통해 회복하는 기법 |
| 미디어 회복   | 디스크 장애가 가장 최근의 덤프 내용을 디스크에 적재하고, 로그를 이용해 가장 최근 덤프 이후 완료된 트랜잭션들에 대해 Redo 작업을 수행하여 회복하는 기법 |



##### Checkpoint (검사점)

데이터베이스의 검사점 회복기법은 체크포인트 시점을 기준으로 장애 발생 시 로그 전체를 조사하지 않고 Redo와 Undo를 이용해 로그 내에서 가장 최근의 검사점으로부터 회복 작업을 수행해 회복 시간을 단축시킨다.



##### 병행 제어

- <u>다중 사용자 환경을 지원하는 데이터베이스 시스템에서 여러 트랜잭션이 성공적으로 동시에 실행될 수 있도록 지원하는 기능으로 동시성 제어라고도 하며, 다중 사용자 환경을 지원하는 데이터베이스 시스템의 경우 필수 지원 기능</u>이다.
- <u>병행 제어는 트랜잭션의 **직렬화(직렬화)**를 보장하고, 동시 수행 트랜잭션 처리량 최대화, 데이터베이스 시스템의 공유도 최대화, 응답 시간 최소화, 데이터의 무결성과 일관성을 보장하기 위해 수행</u>한다.
- 병행제어를 하지 않으면 발생하는 문제점으로 갱신내용 손실, 오류 데이터 읽기, 모순성, 연쇄 복귀 혹은 회복 불능이 있다.



##### 병행 제어를 하지 않으면 발생하는 문제점

갱신내용 손실, 오류 데이터 읽기, 모순성, 연쇄 복귀 혹은 회복 불능

- 갱신 내용 손실
  - 트랜잭션들이 동일 데이터를 동시에 갱신할 경우 발생하는 문제로 한 트랜잭션이 데이터를 갱신한 후 트랜잭션을 종료하기 전에 다른 트랜잭션이 그 갱신 값을 또 다시 갱신하는 경우에 발생
- 오류 데이터 읽기(현행 파악 오류, Dirty Read)
  - 트랜잭션의 중간 수행 결과를 다른 트랜잭션이 참조함으로써 발생하는 오류로 트랜잭션 T2는 T1이 연산을 수행하는 중간값을 읽어 합을 계산함으로써 잘못된 결과를 얻게 되는 현상
- 모순성
  - 두 트랜잭션이 동시에 실행할 때 DB가 일관성이 없는 모순된 상태로 남는 문제로 복수의 사용자가 동시에 DB를 Access하려 갱신함으로써 데이터들의 값이 상호 일치하지 않거나 출력된 정보에 모순이 나타나는 경우가 발생
- 연쇄 복귀 혹은 회복 불능
  - 복수의 트랜잭션이 Data 공유 시 특정 트랜잭션이 실패하여 롤백하고자 해도 다른 트랜잭션이 이미 처리한 부분에 대해서는 최소 불가한 상태가 발생하며 또는 트랜잭션이 연쇄적으로 취소하는 경우가 발생



##### 비완료 의존성

- 낮은 단계의 고립성에서 발생 가능한 문제점 중의 하나로써 Dirty Read라고도 한다.
- 트랜잭션의 중간값의 데이터 참조하는 현상이다.



##### 병행제어 기법

| 기법                                  | 설명                                                         |
| ------------------------------------- | ------------------------------------------------------------ |
| 로킹 (Locking)                        | 데이터베이스 관리에서 하나의 트랜잭션에 사용되는 데이터를 다른 트랜잭션이 접근하지 못하게 하는 것을 의미하며, 트랜잭션들을 갱신할 때는 반드시 로킹 -> 실행 -> 해제의 규칙을 따라 실행 |
| 검증 기법(Validation)                 | 트랜잭션 처리 시 먼저 메모리 상에서 복사본에 대한 연산을 수행하고 검증 완료 시 DBMS에 반영하는 기법. 읽기 단계는 메모리 상에서 데이터 연산 수행. 검증 단계는 트랜잭션의 직렬성 확인 단계. 쓰기 단계는 검증 성공 시 DBMS에 반영하고, 검증 실패시 롤백하는 단계 |
| 타임 스탬프 기법 (Timestamp Ordering) | 트랜잭션 순서 규칙은 시스템 계수기, 논리적 계수기를 이용하여 해당 트랜잭션의 도착 시간 별로 타임스탬프를 할당하는 기법. 트랜잭션이 시스템 들어오는 순서대로 고유값 부여. 직렬화 기법으로 트랜잭션 간의 순서를 미리 정하는 방법. |



##### 로킹

- 데이터베이스 관리에서 하나의 트랜잭션에 사용되는 데이터를 다른 트랜잭션이 접근하지 못하게 하는 것을 의미하며, 트랜잭션들은 갱신할 때 반드시 로킹 -> 실행 -> 해제의 규칙을 따라 실행된다.

- 로킹의 단위는 병행 제어에서 한 번에 잠금할 수 있는 단위로 데이터베이스, 테이블, 레코드, 필드 등에 사용된다.
  - 로킹 단위가 크면 로킹 수가 작아 관리하기 쉽지만, 공유성 수준이 낮아지고, 로킹 단위가 작으면 로킹 수가 많아 관리하기 복잡하지만 공유성 수준이 높아진다.