# kfood
-- 멤버 생성 테이블
-- 관리자는 id를 admin으로 생성하시면 관리자가 됩니다.
create table member(
id varchar2(20) primary key not null,
password varchar2(20) not null,
name varchar2(40) not null,
birth varchar2(50) not null,
gender varchar2(20) not null,
tel varchar2(50) not null,
email varchar2(50) not null,
address varchar2(100) not null);

--게시판 테이블 생성

create table board (
    num number PRIMARY key,
    writer varchar2(20),
    email varchar2(50),
    subject varchar2(50),
    password varchar2(10),
    reg_date date,
    ref number,
    re_step number,
    re_level number,
    readcount number,
    content varchar2(500));

create table board2 (
    num number PRIMARY key,
    writer varchar2(20),
    email varchar2(50),
    subject varchar2(50),
    password varchar2(10),
    kind    varchar2(20),
    reg_date date,
    ref number,
    re_step number,
    re_level number,
    readcount number,
    content varchar2(500));

create table board3 (
    num number PRIMARY key,
    writer varchar2(20),
    email varchar2(50),
    subject varchar2(50),
    password varchar2(10),
    reg_date date,
    ref number,
    re_step number,
    re_level number,
    readcount number,
    content varchar2(500));

create table board4 (
    num number PRIMARY key,
    writer varchar2(20),
    email varchar2(50),
    subject varchar2(50),
    password varchar2(10),
    reg_date date,
    ref number,
    re_step number,
    re_level number,
    readcount number,
    content varchar2(500));

--게시판 시퀀스 생성

 create sequence board_seq
    increment by 1
    start with 0
    minvalue 0
    maxvalue    1000
    nocycle;
 create sequence board2_seq
    increment by 1
    start with 0
    minvalue 0
    maxvalue    1000
    nocycle;
 create sequence board3_seq
    increment by 1
    start with 0
    minvalue 0
    maxvalue    1000
    nocycle;
 create sequence board4_seq
    increment by 1
    start with 0
    minvalue 0
    maxvalue    1000
    nocycle;



--테이블 외래키 추가

alter table board add
constraint fk_id foreign key (writer)
references member(id);

alter table board2 add
constraint fk_id2 foreign key (writer)
references member(id);

alter table board3 add
constraint fk_id3 foreign key (writer)
references member(id);

alter table board4 add
constraint fk_id4 foreign key (writer)
references member(id);
