# Oracle-Database-management-System
This README provides an overview of the Student Management Database, designed specifically for Oracle courses to manage and store information related to Student and organizational of all Compus about Student and their studies. It includes tables for Groups, Subject, Student, Teachers, Marks and Subject/Teacher.

Table Structures
##TABLE GROUPS
```sql
CREATE TABLE GROUPS(
Groupid int not null,
Name varchar(50) not null,
Primary Key (groupid)
	);
```

##TABLE SUBJECT
```sql
CREATE TABLE SUBJECT(
Subjectid int not null,
Titel varchar(50) not null,
Primary Key(subjectid)
	);
```

##TABLE STUDENT
```sql
CREATE TABLE STUDENT(
Studentid int not null,
Firstname varchar(50) not null,
Lastname varchar(50) not null,
Groupid int not null,
Primary key(studentid),
Foreign key (Groupid) References GROUPS(Groupid)
	);
```

##TABLE TEACHERS
```sql
CREATE TABLE TEACHERS(
Teacherid int not null,
Firstname varchar(50) not null,
Lastname varchar(50) not null,
Primary key(Teacherid)
	);
```

##TABLE MARKS
```sql
CREATE TABLE MARKS(
Marksid int not null,
Studentid int not null,
Subjectid int not null,
Date date,
mark int not null,
Primary key(Marksid),
Foreign key (Studentid) References STUDENT(Studentid),
Foreign key (Subjectid) References SUBJECT(Subjectid)
	);
```

##TABLE SUJECT/TEACHER
```sql
CREATE TABLE SUJECT/TEACHER(
Subjectid int not null,
Teacherid int not null,
Groupid int not null,
Foreign key (Teacherid) References TEACHERS(Teacherid),
Foreign key (Subjectid) References SUBJECT(Subjectid),
Foreign key (Groupid) References GROUPS(Groupid)
	);
```

#Another Information is included in File share above
