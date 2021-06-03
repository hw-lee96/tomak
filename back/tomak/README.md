#
## **[2021-05-31]**
1. gradle spring boot start
    - 현재 프로젝트 내에서 gradle을 실행할 수 있게 gradle을 설치
        > `` .\gradlew.bat ``

    - 서버 실행
        > `` .\gradlew bootRun ``
    
2. 서버 실행 중 에러 발생
    - Failed to configure a DataSource: 'url' attribute is not specified and no embedded datasource could be configured.
    - Reason: Failed to determine a suitable driver class

    - DB 관련 설정 내용이 없어서 그렇다고함.
    - 새로운 DB부터 생성

3. mariaDB 생성
    1. 로그인
        1. mariaDB command prompt 실행 후 `` mysql -u root -p `` 커맨드 입력
        2. password 입력

    2. database 확인
        - `` show databases; ``

    3.  database 생성
        - `` create database [db명]; ``
    
    4. db 사용 
        - `` use [db명]; ``
    
    5. 전체 table 확인
        - `` show tables; ``
    
    6. table 생성 예시
        - create table board (
            idx int(10) not null primary key,
            title char(150) not null,
            content char(200) not null,
            insDate datetime not null default now(),
            updDate datetime null,
            userId char(30) not null
        );
    
    7. insert 예시
        - insert into board (idx, title, content, insDate, updDate, userId) values (0, 'title1', 'content1', now(), null, 'user1');