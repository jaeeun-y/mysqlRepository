# mysqlRepository

## DB code
```
CREATE TABLE student
	( student_id CHAR(6) NOT NULL,
	 name VARCHAR(20) NOT NULL,
	 address VARCHAR(50) NULL DEFAULT '미정',
     grade INT NOT NULL,
     age INT NULL,
     birthday DATE NULL,
	 gender CHAR(1) NOT NULL,
     phone CHAR(14) NULL,
     major VARCHAR(20) NULL,
     PRIMARY KEY (student_id),
     unique(phone));
     
create table subject
			( subject_id char(4) not null,
			name varchar(20) not null,
            classroom char(20) not null,
            department varchar(20) not null,
            hours int not null,
            pro_id CHAR(4) NOT NULL,
            PRIMARY KEY (subject_id),
            FOREIGN KEY (pro_id) REFERENCES professor(pro_id));
	
CREATE TABLE enrollment
	( student_id CHAR(6) NOT NULL,
		subject_id CHAR(4) NOT NULL,
        application_date DATE not null,
        midterm int null default 0,
        final int null default 0,
		grade CHAR(1) NOT NULL,
        primary key(student_id, subject_id),
        FOREIGN KEY (student_id) REFERENCES student(student_id),
		FOREIGN KEY (subject_id) REFERENCES subject(subject_id));
        
CREATE TABLE professor
	( pro_id CHAR(4) NOT NULL,
		name VARCHAR(20) NOT NULL,
        major VARCHAR(20) NULL,
        email VARCHAR(50) unique,
        phone CHAR(14),
        primary key(pro_id));

insert into professor
values('p004','김계산','컴퓨터','kimcomputer@naver.com','010-1111-2222');
insert into professor
values('p003','나철학','철학','naphilo@gmail.com','010-2222-3333');
insert into professor
values('p002','심정보','정보통신','siminfo@gmail.com','010-3333-4444');
insert into professor
values('p001','국교양','교양학부','kookculture@naver.com','010-4444-5555');
INSERT INTO professor 
VALUES('p005','박연산','컴퓨터','parkcalc@naver.com','010-5555-6666');
INSERT INTO professor 
VALUES('p006','최통신','정보통신','choinet@gmail.com','010-6666-7777');
INSERT INTO professor 
VALUES('p007','정윤리','철학','jung@gmail.com','010-7777-8888');
INSERT INTO professor 
VALUES('p008','강영어','교양학부','kangeng@naver.com','010-8888-9999');
INSERT INTO professor 
VALUES('p009','조인공','컴퓨터','choai@naver.com','010-9999-0000');
INSERT INTO professor 
VALUES('p010','한수학','컴퓨터','hanmath@naver.com','010-1212-3434');

INSERT INTO 학생
VALUES('s001','김연아','서울 서초',4,23,'여','2002-01-01','010-1111-2222','컴퓨터');
INSERT INTO 학생
VALUES('s002','홍길동','DEFAULT',1,26,'2001-02-02','남',NULL,'통계');
INSERT INTO 학생
VALUES('s003','이승엽',NULL,3,30,'1997-03-03','남',NULL,'정보통신');
INSERT INTO 학생
VALUES('s004','이영애','경기 분당',2,NULL,NULL,'여', '010-4444-5555', '정보통신');
INSERT INTO 학생
VALUES('s005','송윤아','경기 과천',4,23,'2002-02-02','여','010-6666-7777','컴퓨터');
INSERT INTO 학생
VALUES('s006','홍길동','서울 종로',2,26,'2001-04-04','남','010-8888-9999','컴퓨터');
INSERT INTO 학생
VALUES('s007','신재은','서울 동작',1,22,'2005-10-19','여','010-1111-1019','컴퓨터');
INSERT INTO student 
VALUES('s008', '신재은', '부산시 해운대구', 2, 21, '2005-04-11', 'M', '010-1008-1008', '컴퓨터');
INSERT INTO student 
VALUES('s009', '신재금', '서울시 관악구', 4, 26, '2000-11-30', 'M', '010-1009-1009', '컴퓨터');
INSERT INTO student 
VALUES('s010', '신재동', '경기도 개성시', 3, 22, '2004-01-01', 'F', '010-1010-1010', '교양학부');

insert into subject
values('c001', '데이터베이스', '126', '컴퓨터', 3, 'p004');
insert into subject
values('c002', '정보보호', '137', '정보통신', 3, 'p002');
insert into subject
values('c003', '모바일웹', '128', '컴퓨터', 3, 'p004');
insert into subject
values('c004', '철학개론', '117', '철학', 2, 'p003');
insert into subject
values('c005', '전공글쓰기', '120', '교양학부', 1, 'p001');
INSERT INTO subject 
VALUES('c006', '운영체제', '126', '컴퓨터', 3, 'p005');
INSERT INTO subject 
VALUES('c007', '네트워크', '135', '정보통신', 3, 'p006');
INSERT INTO subject 
VALUES('c008', '현대윤리', '118', '철학', 2, 'p007');
INSERT INTO subject 
VALUES('c009', '기초토익', '201', '교양학부', 2, 'p008');
INSERT INTO subject 
VALUES('c010', '알고리즘', '125', '컴퓨터', 3, 'p009');

INSERT INTO enrollment
VALUES('s001', 'c002', '2019-09-03', 93, 98, 'A');
INSERT INTO enrollment
VALUES('s004', 'c005', '2019-03-03', 72, 78, 'C');
INSERT INTO enrollment
VALUES('s002', 'c001', '2018-03-10', 31, 50, 'F');
insert into enrollment
values('s001','c004', '2019-03-05', 82, 89, 'B');
insert into enrollment
values('s004','c003', '2020-09-03', 91, 94, 'A');
insert into enrollment
values('s001','c005', '2020-09-03', 74, 79, 'A');
insert into enrollment
values('s003','c001', '2019-03-03', 81, 82, 'B');
insert into enrollment
values('s004','c002', '2018-03-05', 92, 95, 'A');
INSERT INTO enrollment 
VALUES('s008', 'c006', '2021-03-02', 85, 88, 'B');
INSERT INTO enrollment 
VALUES('s009', 'c010', '2022-03-02', 95, 97, 'A');
INSERT INTO enrollment 
VALUES('s010', 'c009', '2023-03-02', 80, 85, 'B');

```
---

## insert into
```
INSERT INTO enrollment VALUES('s005', 'c001', '2024-03-02', 90, 85, 'A');
INSERT INTO enrollment VALUES('s005', 'c003', '2024-03-03', 75, 80, 'B');

INSERT INTO enrollment VALUES('s006', 'c002', '2024-03-02', 82, 79, 'B');
INSERT INTO enrollment VALUES('s006', 'c007', '2024-03-04', 95, 98, 'A');
```

---

## query 15
<img width="618" height="552" alt="1-1" src="https://github.com/user-attachments/assets/f2e444c5-cc28-4460-b817-6e1fb8b1ac1c" />

<img width="616" height="543" alt="1-2" src="https://github.com/user-attachments/assets/c98d91a7-ec6e-49ae-91f5-c7d12a1bb4aa" />

<img width="620" height="242" alt="6INDEX" src="https://github.com/user-attachments/assets/35a14d06-4ffa-4d06-84fb-e5cae9367bda" />

<img width="622" height="441" alt="5-2delete문" src="https://github.com/user-attachments/assets/dfc1e76b-bb4f-4b09-85fb-adf507fd8ad9" />

<img width="614" height="306" alt="5-1update문" src="https://github.com/user-attachments/assets/3be971db-6caa-4288-b188-ad75a7f35299" />

<img width="756" height="429" alt="4" src="https://github.com/user-attachments/assets/d2ee8e07-499c-408c-bbc5-627a72d5aed8" />

<img width="612" height="196" alt="3-3 avg문" src="https://github.com/user-attachments/assets/d631c843-0228-40ba-bdf4-b7cbaf3c41e2" />

<img width="612" height="211" alt="3-2 sum문" src="https://github.com/user-attachments/assets/f4f79a85-4d0b-48df-8cad-6cec4b683ece" />

<img width="616" height="147" alt="3-1count문" src="https://github.com/user-attachments/assets/9fbcd758-4239-4a64-b1e2-e6218dc5f4c6" />

<img width="552" height="433" alt="2-4" src="https://github.com/user-attachments/assets/33f109f7-5c61-45c4-8643-6dd669d9e1b3" />

<img width="684" height="410" alt="2-3" src="https://github.com/user-attachments/assets/b0fbb1e5-7f7b-4e9a-96bc-bfb7fbcd8ab7" />

<img width="1405" height="381" alt="2-2" src="https://github.com/user-attachments/assets/9d992f18-3a66-44f3-96cb-810686f344e7" />

<img width="1406" height="361" alt="2-1" src="https://github.com/user-attachments/assets/4a9f1f4c-9be6-4e71-8c0c-c0cb85cbc797" />

<img width="617" height="539" alt="1-4" src="https://github.com/user-attachments/assets/606b5fc9-2a80-4a4c-8b3e-07dff251a387" />

<img width="612" height="456" alt="1-3" src="https://github.com/user-attachments/assets/54ee0b5d-2e2d-491d-a1fd-c2d1c942de12" />


