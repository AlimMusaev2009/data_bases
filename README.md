# data_bases

USE academy;

CREATE TABLE IF NOT EXISTs shedule(
	id INT primary key auto_increment,
    day_name varchar(100) not null,
	data_day date
);

create table if not exists teachers(
	id INT primary key auto_increment,
    full_name varchar(100) not null,
    email varchar(100)  unique,
    phone_number varchar(100) unique,
    employment_date date
);

create table if not exists courses(
	id INT primary key auto_increment,
    course_name varchar(100) not null,
    speciality varchar(100) not null,
    created_at date
);

create table if not exists classes(
	id INT primary key auto_increment,
    class_name varchar(100) not null,
    places tinyint
);

create table if not exists student_groups(
	id INT primary key auto_increment,
    group_name varchar(100) not null,
    course_id int not null,
    student_count tinyint,
    created_at date,
    foreing key (course_id) references courses(id)
);
