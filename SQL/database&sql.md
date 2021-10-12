# 데이터베이스 database

## 데이터란?
- 컴퓨터 안에 기록되어 있는 숫자

## 데이터베이스란?
- 데이터의 집합
- 넓은 의미에서의 데이터 베이스 => 컴퓨터 안에 기록된 모든 것
- 일반적으로 통용되는 데이터 베이스 => 특정 데이터를 확인하고 싶을 때 간단하게 찾아낼 수 있도록 정리된 형태
- 데이터베이스 내의 데이터는 영구적으로 보존되어야 한다.
    - 주 기억 장치에만 데이터를 저장한다면, 전원을 끄는 순간 모든 데이터는 사라져 버린다.
    - 따라서 데이터베이스의 데이터는 하드디스크나 플래시메모리(SSD) 등 비휘발성 저장장치에 저장한다.

## 시스템 내의 데이터베이스
- 데이터베이스는 일반적으로 데이터센터의 서버에서 운용했다.
- 하지만 현재는 데이터베이스가 개인용 컴퓨터나 휴대용 기기에 내장되어 있기도 하다.

### 다양한 시스템에서의 데이터베이스
- 웹 시스템
인터넷에서 쇼핑을 하거나 무언가를 예약할 때 웹 시스템을 통해 데이터베이스에 접근한다.
- POS 시스템
편의점에서 물건을 살때, 계산대(POS 시스템)에서 데이터가 데이터베이스로 전송된다.
- 휴대전화
휴대전화의 전화번호부도 작은 데이터베이스라고 할 수 있다.

## DB & DBMS
- DB는 Database(데이터베이스)의 약자이다.
- DBMS는 Database Management System(데이터베이스 관리 시스템)의 약자이다.
    - 데이터베이스를 효율적으로 관리하는 소프트웨어이다.

### DBMS와 같은 전용 소프트웨어가 필요한 이유
1. 생산성
- 어떤 시스템에서든 데이터 검색, 추가, 삭제, 갱신과 같은 처리가 이루어진다.
- 위 기본 기능을 DBMS가 제공한다.
- 시스템을 구축할 때 기본 기능부터 구현하는 것은 비용 측면에서 효율적이지 않다.

2. 기능성
- DBMS는 데이터베이스를 다루는 기능을 많이 제공한다.
    - 복수 유저의 요청에 대응
    - 대용량의 데이터 저장 및 고속으로 검색하는 기능
    - 데이터베이스 관리 기능 유저 확장 기능

3. 신뢰성
- 대규모 데이터베이스는 많은 요청에 대응할 수 있도록 만들어져 있다.
    - 이를 위해 하드웨어를 **여러 대**로 구성하여 신뢰성을 높이는 동시에 성능 향상을 꾀한다.
    - 일부 DBMS는 컴퓨터 여러 대를 두고, 소프트웨어를 통해 확장성(Scalability)과 부하 분산(Load balancing)을 구현한다.
        - 이를 보통 '클러스터 구성' 및 '스케일 아웃'이라고 부른다.
    - 많은 DBMS가 데이터베이스의 데이터를 다른 저장장치로 내보내거나(export) 데이터베이스 안에 데이터를 집어넣는 (import) 등의 기능을 갖췄다.
        - 이 기능들을 통해 데이터베이스를 간단하게 백업할 수 있다.

## SQL
- DBMS와의 대화에 필요하다.
- 데이터베이스의 종류 중 하나인 '관계형 데이터베이스 관리 시스템(RDBMS)'을 조작할 때 사용된다.
- 현재 표준화가 진행되어 표준 언어이다.
    - 생선성을 향상시킬 수 있다.

### SQL 명령의 종류
1. DML
- Data Manipulation Language의 약자
- 데이터베이스에 새롭게 데이터를 추가하거나 삭제하거나 내용을 갱신하는 등 **데이터를 조작**할 때 사용
- SQL의 가장 기본이 되는 명령셋(set)

2. DDL
- Data Definition Language의 약자
- **데이터를 정의**하는 명령어
- 데이터베이스는 '데이터베이스 객체(object)'라는 데이터 그릇을 이용하여 데이터를 관리한다.
    - 이 같은 객체를 만들거나 삭제하는 명령어

#### 데이터베이스 객체의 종류
- 테이블
- 뷰
- 인덱스

3. DCL
- Data Control Language의 약자
- **데이터를 제어**하는 명령어
- DCL에는 트랜잭션을 제어하는 명령과 데이터 접근권한을 제어하는 명령이 포함되어 있다.

**참고**
- [도서] SQL 첫걸음