# Oracle-Database-management-System
This README provides an overview of the Student Management Database, designed specifically for Oracle courses to manage and store information related to Student and organizational of all Compus about Student and their studies. It includes tables for Groups, Subject, Student, Teachers, Marks and Subject/Teacher.

Table Structures 

#ORACLE DATABASE MANAGEMENT SYSTEM

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

#INSERT DATA INTO TABLES

##INSERT INTO GROUPS
```sql
INSERT INTO GROUPS VALUES('10001','A');
```
```sql
INSERT INTO GROUPS VALUES('10002','B');
```
```sql
INSERT INTO GROUPS VALUES('10003','C');
```

##INSERT INTO SUBJECT
```sql
INSERT INTO SUBJECT VALUES('AMAT8111','Applied Mathematics');
```
```sql
INSERT INTO SUBJECT VALUES('EDRM8113','Study and Research Method');
```
```sql
INSERT INTO SUBJECT VALUES('ENGL8115','General English');
```

##INSERT INTO STUDENT
```sql
INSERT INTO STUDENT VALUES('24556','INEZA UWASE','Anitha','10001');
```
```sql
INSERT INTO STUDENT VALUES('24523','UMUTONIWASE','Angelo','10001');
```
```sql
INSERT INTO STUDENT VALUES('25999','KUNDWA','Fabrice','10002');
```

##INSERT INTO TEACHERS
```sql
INSERT INTO TEACHERS VALUES('099','ISHIMWE','David');
```
```sql
INSERT INTO TEACHERS VALUES('231','FIONA','Kasime');
```
```sql
INSERT INTO TEACHERS VALUES('098','KWITONDA','Jane');
```

##INSERT INTO MARKS
```sql
INSERT INTO MARKS VALUES('1','24523','ENGL8115','To_Date('09/02/2023')','55');
```
```sql
INSERT INTO MARKS VALUES('2','24556','AMAT8111','To_Date('12/05/2023')','67');
```
```sql
INSERT INTO MARKS VALUES('3','26789','RELB8116','To_Date('12/05/2023')','89');
```

##INSERT INTO SUBJECT/TEACHERS
```sql
INSERT INTO SUBJECT/TEACHERS VALUES('ENGL8115','099','10001');
```
```sql
INSERT INTO SUBJECT/TEACHERS VALUES('AMAT8111','231','10002');
```
```sql
INSERT INTO SUBJECT/TEACHERS VALUES('RELB8116','098','10001');
```
#SELECT DATA FROM TABLE

##SELECT ALL DATA FROM TABLE STUDENT
```sql
SELECT * FROM STUDENT;
```

##SELECT ALL DATA FROM TABLE MARKS
```sql
SELECT * FROM MARKS;
##UPDATE TABLE GROUPS
```sql
UPDATE GROUPS SET Name='D' WHERE GROUPID = '10001';
```

##UPDATE TABLE SUBJECT
```sql
UPDATE SUBJECT SET Title='Academic English Writting' WHERE Subjectid = 'ENGL8115';
```

##UPDATE TABLE STUDENT
```sql
UPDATE STUDENT SET Lastname='Alice' WHERE Studentid = '24556';
```

##UPDATE TABLE TEACHERS
```sql
UPDATE TEACHERS SET Lastname='Keza' WHERE Studentid = '099';
```

##UPDATE TABLE MARKS
```sql
UPDATE MARKS SET Marks='97' WHERE Studentid = '24556';
```

#DELETE DATA INTO TABLES

##DELETE DATA IN GROUPS TABLE
```sql
DELETE FROM GROUPS WHERE Groupid='10001';
```

##DELETE DATA IN TEACHERS TABLE
```sql
DELETE FROM TEACHERS WHERE Teacherid='231';
```

#JOIN QUERY FOR RETRIEVE DATA IN MULTIPLE TABLES

```sql
SELECT STUDENT.Firstname, STUDENT.Lastname, GROUPS.Name
FROM STUDENT,GROUPS
INNER JOIN STUDENT = Studentid
ON GROUPS = Groupid;
```
#RELAIONSHIP OF TABLE


[Alt text](image3.JPEG)
