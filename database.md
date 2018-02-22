**Step 4: Database 구성하기**
==================
### 1. Database 생성하기
mysql에서 다음 쿼리문을 실행하여 Database를 생성합니다.

~~~
create database chatbot;

CREATE TABLE department(
    id integer auto_increment,
    name varchar(30),

    primary key(id)
);

CREATE TABLE diseases(
	id integer auto_increment,
    name varchar(300),
    dept_id integer not null,

    primary key(id),
    constraint fk_dept_id1 foreign key(dept_id) references department(id) on delete cascade
);

CREATE TABLE professors(
   id integer auto_increment,
   name varchar(30),
   dept_id integer not null,
   major varchar(100),
   pimg varchar(300),
   purl varchar(300),

   primary key(id),
   constraint fk_dept_id2 foreign key(dept_id) references department(id) on delete cascade
);

CREATE TABLE reservation(
	id integer auto_increment,
    user_id bigint not null,
    user_name varchar(100) not null,
    user_phone varchar(100),
    prof_id integer not null,
    dept_id integer not null,
    date varchar(30) not null,
    primary key(id),
    constraint fk_prof_id3 foreign key(prof_id) references professors(id) on delete cascade,
    constraint fk_dept foreign key(dept_id) references department(id) on delete cascade
);

CREATE TABLE `faq_list` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `Question` longtext NOT NULL,
  `Answer` longtext,
  `url` varchar(300) DEFAULT NULL,
  PRIMARY KEY (`id`)
);
~~~
각각이 database table을 만들었다면 이제 csv파일을 다운받아 import해줍니다.
csv파일은 csvfile폴더에 있습니다.
 다음의 쿼리문을 실행하여 csv파일을 import 해줍니다.

~~~
LOAD DATA LOCAL INFILE 'C:/Users/KD/Desktop/department.csv'
INTO TABLE medicine_list FIELDS TERMINATED BY ',' ENCLOSED BY '"'
LINES TERMINATED BY '\n' (id,name);
~~~

~~~
LOAD DATA LOCAL INFILE 'C:/Users/KD/Desktop/diseases.csv'
INTO TABLE medicine_list FIELDS TERMINATED BY ',' ENCLOSED BY '"'
LINES TERMINATED BY '\n' (id,name,dept_id);
~~~

~~~
LOAD DATA LOCAL INFILE 'C:/Users/KD/Desktop/professors.csv'
INTO TABLE medicine_list FIELDS TERMINATED BY ',' ENCLOSED BY '"'
LINES TERMINATED BY '\n' (id,name,dept_id,major,pimg,purl);
~~~

~~~
LOAD DATA LOCAL INFILE 'C:/Users/KD/Desktop/FAQ_data.csv'
INTO TABLE medicine_list FIELDS TERMINATED BY ',' ENCLOSED BY '"'
LINES TERMINATED BY '\n' (id,Question,Answer,url);
~~~

~~~
LOAD DATA LOCAL INFILE 'C:/Users/KD/Desktop/medicine.csv'
INTO TABLE medicine_list FIELDS TERMINATED BY ',' ENCLOSED BY '"'
LINES TERMINATED BY '\n' (id,name,synonyms,efficacy,howtouse,precaution,url,imageurl);
~~~
**Tip. 경로명이 정확한지 확인해주세요.**
