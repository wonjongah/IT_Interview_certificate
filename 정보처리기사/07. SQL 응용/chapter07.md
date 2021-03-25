##### SQL 유형

- 데이터 질의어(DQL) 

데이터베이스에 저장된 데이터를 검색하는데 사용하는 질의어

-> SELECT

- 데이터 조작어(DML)

데이터베이스에 저장된 데이터를 수정, 삭제, 추가하는 명령어

-> INSERT, UPDATE, DELETE

- 데이터 정의어(DDL)

데이터베이스 객체를 생성하고 수정, 삭제하는 명령어, 데이터베이스의 스키마를 정의, 스키마에 대한 명세는 시스테 카탈로그에 저장

-> CREATE, ALTER, DROP, TRUNCATE

- 데이터 제어어(DCL)

데이터베이스의 규정이나 기법을 정의하고 제어하는 언어, 사용자 권한 부여/취소, 트랜잭션 제어

-> GRANT, REVOKE, COMMIT, ROLLBACK



##### DELETE

- 한 테이블로부터 한 개 이상의 튜플(행)들을 삭제할 때 사용
- DBMS LOG에 적재
- 저장 공간 반납 안 됨
- ROLLBACK 가능
- 작업 속도 느림
- 표준 형식 (WHERE 조건 생략 시 모든 튜플 삭제)

```SQL
DELETE FROM 테이블명
WHERE 조건;
```



##### TRUNCATE

- WHERE 절 사용 불가하며, 전체 데이터가 삭제
- DBMS LOG를 사용하지 않아 삭제 시 DBMS 회복 불가능
- ROLLBACK 불가
- 작업 속도 빠름
- 표준 형식

```SQL
TRUNCATE TABLE 테이블명;
```



```SQL
SELECT [DISTINCT] 컬럼명 {, 컬럼명}
FROM 테이블명
[WHERE 조건]
[GROUP BY 컬럼명 {, 컬럼명}]
[HAVING 조건]
[ORDER BY 컬럼명 {, 컬럼명} [ASC, DESC]];
```



##### DISTINCT

SELECT 명령을 통해 검색한 결과는 디폴트로 ALL, 중복이 포함된 상태로 출력된다. 

중복을 제거한 결과를 검색하고자 할 때는 DISTINCT 키워드를 SELECT 뒤 컬럼명 앞에 기술한다.

```SQL
SELECT DISTINCT 컬럼명
```



##### 와일드 카드 %, _, []

와일드카드 문자를 이용하여 특정 조건을 만족하는 문자열을 포함하는 데이터를 검색한다.

% : 검색 대상 문자가 포함된 모든 데이터를 검색할 때 사용

_ : 데이터 중 검색 대상 문자가 포함되고 지정한 문자수 만큼 앞 글자가 포함된 데이터를 검색할 때 사용

[] : 문자열 집합으로 지정하여 검색대상 문자로 시작하는 모든 데이터를 검색할 때 사용

EX)

```SQL
LIKE '[김이]'
-- 김 혹은 이로 시작하는 문자열들
```



##### 산술 연산자

- 산술 연산자(+, -, *, /)를 이용해 검색 결과에 연산을 수행한 결과를 확인할 수 있으며, 연산 우선순위는 일반적인 연산자 서술 양식과 같다.



##### IN 연산자

- 특정 컬럼의 값이 검색하고자 하는 값 리스트에 해당하는지 검사한 후에 리스트에 해당하는 데이터들을 검색하고자 할 때 IN 연산자 사용
  - C IN (LIST) : C 컬럼이 LIST에 포함된 경우 해당 레코드 출력
  - C NOT IN (LIST) : C 컬럼이 LIST에 포함되지 않은 경우 해당 레코드 출력



##### ORDER BY [ASC|DESC]

- 검색 결과를 정렬하고자 할 때 ORDER BY 절을 사용한다.
- 오름차순 정렬을 원할 경우 ASC(기본값, 생략 가능), 내림차순 정렬을 원할 경우 DESC 기술



##### IS NULL, IS NOT NULL

칼럼 값이 NULL 값인지 확인할 때는 비교 연산자(=)를 사용하는 것이 아니라 IS NULL 혹은 IS NOT NULL 연산을 이용한다.

- IS NULL : 칼럼 값이 NULL인 모든 튜플(행)을 검색
- IS NOT NULL : 칼럼 값이 NULL이 아닌 모든 튜플(행)을 검색



##### 집계 함수

- 집계성 SQL은 총합, 평균 등의 데이터 분석을 위해 복수 개의 튜플(행)을 기준으로 데이터를 분석하는 SQL을 말하며 집계 함수, 그룹 함수, 윈도우 함수로 구성된다.
- 집계 함수는 GROUP BY 절과 함께 사용되어 복수 행에 대한 개수, 합계, 평균, 최소값, 최대값 등을 계산하는 함수로서 집계함수의 COUNT(*)은 NULL값을 포함하며, 이외의 집계함수는 NULL 값을 제거한 후 계산한다.

COUNT() -> 튜플(행)이나 값들의 개수

SUM() -> 값들의 합

AVG() -> 값들의 평균값

MAX() -> 값들의 최대값

MIN() -> 값들의 최소값

STDDEV() -> 값들의 표준편차

VARIANCE() -> 값들의 분산값

EX)

```SQL
SELECT COUNT(*)
FROM 학생;
```



##### INSERT INTO

레코드를 한번에 하나씩 삽입하고자 할 경우

```SQL
INSERT INTO 테이블명 (컬럼명1, ... , 컬럼명N)
VALUES (값1, ... , 값N);
```

테이블에 새로운 튜플을 한 번에 여러 개씩 삽입하고자 하면 INSERT 문에 서브쿼리를 이용한다.

- VALUES 절 대신 SELECT 절 기술
- 이때 SELECT 절의 검색되는 컬럼의 개수, 순서, 타입이 INSERT INTO 절의 삽입 대상 컬럼의 개수, 순서, 타입이 일치해야 한다.

```SQL
INSERT INTO 테이블명(컬럼명1, ..., 컬럼명N)
SELECT 절;

-- 사원테이블에서 급여가 4000 이상인 사원의 정보를 HIGH_SAL 테이블에 삽입
INSERT INTO HIGH_SAL(EMPNO, EMPNAME, SALARY, DNO)
SELECT * FROM EMPLOYEE WHERE SALARY >= 4000;
```



##### DELETE

DELETE 명령어는 DML에 해당하며 한 테이블로부터 한 개 이상의 튜플(행)을 삭제할 때 사용된다.

```SQL
DELETE FROM 테이블명
WHERE 조건;
```

WHERE 조건절이 없을 경우 모든 튜플(행)이 삭제되므로 사용 시 주의해야 한다.

DROP TABLE은 스키마(테이블)가 삭제되면서 저장되어 있는 모든 튜플(행)이 함께 삭제되는 부분이 DELETE 명령어와 차이점이다.



##### UPDATE

한 테이블에 들어 있는 튜플(행)들의 컬럼 값을 수정할 때 사용한다.

```SQL
UPDATE 테이블명
SET 컬럼명 = 값 또는 식
WHERE 조건;

-- WHERE 조건 생략 시 모든 튜플이 수정
-- 사원 테이블에서 사원번호 1234의 부서 번호를 3번으로 수정
UPDATE EMPLOYEE
SET DNO = 3
WHERE EMPNO = 1234;
```



##### 데이터 정의어(DDL)

CREATE - 데이터베이스 객체 생성

ALTER - 데이터베이스 객체 변경

DROP - 데이터베이스 객체 삭제

TRUNCATE - 데이터베이스 객체 내 튜플 삭제

- DDL 수행 후 기본적으로 AUTO COMMIT된다.
- CASCADE 옵셥을 사용하면 참조하는 테이블도 같이 삭제되며, 해당 테이블만 삭제하고자 할 때는 CASCADE 옵션을 빼고 사용한다.



##### 테이블 생성

```SQL
CREATE TABLE 테이블명(
속성명 DATA_TYPE [NOT NULL], .. ,
PRIMARY KEY(기본키 속성명),
UNIQUE(대체키 속성명, ...),
FOREIGN KEY(외래키 속성명, ...)
REFERENCES 참조테이블(기본키 속성명),
CONSTRAINT 제약조건명 CHECK(조건식));

-- EX
CREATE TABLE 학생(
이름 VARCHAR(15) NOT NULL,
전공 VARCHAR(15) NOT NULL,
학번 VARCHAR(15) NOT NULL,
성별 SEX,
PRIMARY KEY(학번)
FOREIGN KEY(전공)
REFERENCES 학과(학과코드),
CONSTRAINT 성별제약
CHECK(성별 = '남'));
```

PRIMARY KEY - 테이블의 기본키, 기본으로 NOT NULL + UNIQUE 제약 포함

FOREIGN KEY REFERENCES - 외래키 정의, 참조 대상을 테이블 이름(열 이름)으로 명시, 참조 무결성 위배 상황 발생 시 처리 방법으로 옵션 지정 가능(NO ACTION, SET DEFAULT, SET NULL, CASCADE)

UNIQUE - 테이블 내에서 얻은 유일한 값을 가져야 함, 테이블 내에서 같은 값을 가져서는 안 되는 항목 지정

NOT NULL - NULL일 수 없음

CHECK - 개발자가 정의하는 제약 조건, 상황에 따라 다양한 조건 설정 가능

- 데이터 모델링에서 기본키 표시는 해당 컬럼 앞에 #을 붙여서 또는 및줄을 그어서 표시하기도 한다.



##### 테이블 구조 변경

ALTER를 사용해 테이블 구조를 변경한다.

```SQL
-- 컬럼(열) 추가
ALTER TABLE 테이블명
ADD 컬럼명 데이터타입;

-- 컬럼 데이터 타입 변경
ALTER TABLE 테이블명
MODIFY 컬럼명 데이터타입;

-- 컬렴(열) 삭제
ALTER TABLE 테이블명
MODIFY 컬럼명;
```



##### DROP, TRUNCATE, RENAME, ALTER TABLE RENAME

- DROP TABLE 테이블명;

-> 테이블 삭제

- TRUNCATE TABLE 테이블명;

-> 테이블 내용 삭제

- RENAME TABLE 이전테이블명 TO 새로운테이블명;
- ALTER TABLE 이전테이블명 RENAME TO 새로운테이블명;

-> 테이블 이름 변경



##### DROP, DELETE, TRUNCATE 차이점

DROP -> 테이블을 삭제를 통한 데이터 전체 삭제

DELETE -> LOG에 삭제 내용 기록, DBMS 회복 가능

TRUNCATE -> LOG 사용 X, DBMS 회복 불가능



##### DROP USER

DDL의 DROP 명령어를 사용해 계정 삭제가 가능하다.

EX)

```SQL
DROP USER USER01;
```



##### ALTER USER

데이터베이스 관리자는 ALTER 명령문을 이용해 데이터베이스에 생성된 계정의 패스워드 변경이 가능

```SQL
ALTER USER 계정명 IDENTIFIED BY 신규패스워드;
```



##### CREATE OR REPLACE

<u>CREATE OR REPLACE</u> 명령문은 <u>뷰가 정의된 기본 테이블(학생)를 재정의하고자 할 때 뷰를 삭제하지 않고 변경이 가능한 명령어이다.</u>

- 통상적으로 뷰를 삭제하고 다시 생성하면 되지만 삭제를 하는 순간 권한을 부여받고 참조하고 있던 계정의 권한도 회수되기 때문에 다시 권한을 재부여하는 절차가 필요
- 기본 테이블의 재정의로 인한 관계의 단절을 해소하기 위해 사용

```SQL
-- VIEW
CREATE OR REPLACE VIEW 뷰명...

-- TRIGGER
CREATE OR REPLACE TRIGGER 트리거명...

-- PROCEDURE
CREATE OR REPLACE PROCEDURE 프로시저명...

-- FUNCTION
CREATE OR REPLACE FUNCTION 사용자정의함수명...
```

뷰, 프로시저, 사용자정의 함수 등은 변경 시 삭제 및 생성을 하지 않고 CREATE OR REPLACE 명령어를 사용해 재사용이 가능하다.



##### 데이터 제어어(DCL)

- 데이터 제어어는 데이터베이스의 규정이나 기법을 정의하고 제어하는 언어(CONTROL LANGUAGE)이다.
- 트랜잭션 제어 명렁을 이용해 데이터베이스의 무결성과 보안, 회복, 동시성 제어를 수행한다.

| 기능        | 명령어    | 설명                                                         |
| ----------- | --------- | ------------------------------------------------------------ |
| 무결성      | COMMIT    | 수행된 결과를 실제 물리적 디스크로 저장                      |
|             | ROLLBACK  | 명령 수행 실패를 의미하며 수행된 결과를 원복시킴             |
|             | SAVEPOINT | 저장점 지정, 지정된 저장점부터 현재까지 일부만 ROLLBACK 가능 |
| 데이터 보안 | GRANT     | 데이터베이스 사용자에게 사용 권한 부여                       |
|             | REVOKE    | 데이터베이스 사용자에게 부여된 사용 권한 취소                |



##### GRANT

- 데이터베이스의 서로 다른 객체들에 대해서 다양한 권한이 존재하며 객체의 생성자(소유자)는 객체에 대한 모든 권한을 갖는다.
- 생성자는 자신이 소유한 임의의 객체에 대한 특정 권한을 GRANT문을 사용해 다른 사용자나 역할에게 허가할 수 있다.

```SQL
GRANT 권한 [컬럼리스트] ON 객체 TO {사용자 | 역할 | PUBLIC}
[WITH GRANT OPTION];

-- GRANT절 : SELECT, INSERT, DELETE, UPDATE, REFERENCES 권한 나열
-- WITH GRANT OPTION : 부여받은 권한을 다른 사용자에게 허가 가능
```

WITH GRANT OPTION으로 권한이 회수되면 객체에 대해서는 연쇄적으로 회수가 되지만 시스템 권한(CREATE TABLE, DROP TABLE 등)은 회수가 되지 않는다.



- ROLE을 생성해 여러 사용자들에게 동일한 권한을 부여할 때 그룹화해 역할 기반으로 부여 가능하다.
- ROLE은 사용자에게 허가할 수 있는 연관된 권한들의 그룹을 말하며, 각 사용자는 여러 역할에 속할 수도 있으며 또는 여러 사용자가 같은 역할을 가질 수 있다.

```SQL
-- ROLE 생성
CREATE ROLE ROLE명;

-- ROLE에 CREATE TABLE, DROP TABLE 권한 부여
GRANT CREATE TABLE, DROP TABLE, ALTER TABLE TO ROLE명;

-- 유저에게 ROLE을 이용해 동일한 권한 부여
GRANT ROLE명 TO 유저1;
GRANT ROLE명 TO 유저2;

-- ROLE에서 특정 권한 회수 시 해당 ROLE 권한을 부여받았던 모든 사용자에게서 특정 권한 회수됨
REVOKE DROP TABLE FROM ROLE명;
```



##### COMMIT, ROLLBACK, CHECKPOINT

COMMIT과 ROLLBACK 명령어는 트랜잭션의 원자성을 보장하기 위한 명령어이다.

ATOMICITY(원자성) - 분해할 수 없는 최소 단위, 연산 전체가 성공 또는 실패, ALL OR NOTHING

- COMMIT - 거래 내역 확인

-> 하나의 논리적 단위에 대한 작업이 성공적으로 끝났고, 데이터베이스가 일관된 상태에 있을 때 트랜잭션이 수행한 갱신 연산이 완료된 것을 트랜잭션 관리자에게 알려주는 연산

- ROLLBACK - 거래 내역 취소

-> 하나의 트랜잭션 처리가 비정상 종료되어 데이터베이스의 일관성을 깨뜨렸을 때, 트랜잭션 일부가 정상 처리되었더라도 트랜잭션의 원자성을 구현하기 위해 이 트랜잭션이 수행한 모든 연산을 취소시키는 연산

- CHECKPOINT - 저장점 설정

-> ROLLBACK할 위치 지정

```SQL
SAVEPOINT SAVEPOINT명;
ROLLBACK TO SAVEPOINT SAVEPOINT명;
```



##### JOIN

| 분류        | 설명                                                         |
| ----------- | ------------------------------------------------------------ |
| 논리적 조인 | 사용자의 SQL문에 표현되는 테이블 결합 방식, INNER JOIN, OUTER JOIN, SELF JOIN |
| 물리적 조인 | 데이터베이스 옵티마이저에 의해 내부적으로 발생하는 테이블 결합 방식, NESTED JOIN, MERGE JOIN, HASH JOIN |

| 구분       | 유형             | 설명                                                         |
| ---------- | ---------------- | ------------------------------------------------------------ |
| INNER JOIN | EQUI JOIN        | 특정 컬럼을 비교해 같은 값을 추출, 자연조인(NATURAL JOIN)    |
|            | NATURAL JOIN     | 두 테이블의 모든 컬럼을 비교해 같은 걸럼명을 가진 모든 컬럼 값이 같은 경우를 추출 |
|            | CROSS JOIN       | 조인 조건이 없는 모든 데이터의 조합 추출                     |
| OUTER JOIN | LEFT OUTER JOIN  | 왼쪽 테이블의 모든 데이터와 오른쪽 테이블의 동일 데이터 추출 |
|            | RIGHT OUTER JOIN | 오른쪽 테이블의 모든 데이터와 왼쪽 테이블의 동일 데이터 추출 |
|            | FULL OUTER JOIN  | 양쪽의 모든 데이터 추출                                      |
| SELF JOIN  | SELF JOIN        | 한 테이블 내에서 조인 연산 수행                              |

