# mysqlRepository

##DB code
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

insert into professor
values('p004','김계산','컴퓨터','kimcomputer@naver.com','010-1111-2222');
insert into professor
values('p003','나철학','철학','naphilo@gmail.com','010-2222-3333');
insert into professor
values('p002','심정보','정보통신','siminfo@gmail.com','010-3333-4444');
insert into professor
values('p001','국교양','교양학부','kookculture@naver.com','010-4444-5555');

```
---

##insert into
```
INSERT INTO enrollment VALUES('s005', 'c001', '2024-03-02', 90, 85, 'A');
INSERT INTO enrollment VALUES('s005', 'c003', '2024-03-03', 75, 80, 'B');

INSERT INTO enrollment VALUES('s006', 'c002', '2024-03-02', 82, 79, 'B');
INSERT INTO enrollment VALUES('s006', 'c007', '2024-03-04', 95, 98, 'A');
```

---

##
