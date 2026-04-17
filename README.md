# DBMS_LAB
Aim: To create a new database named 2CSE5_0755.\
Requirement: SQL DBMS with database creation privileges.\
Theory: CREATE DATABASE command creates a new database for storing tables and data.\
Query to Perform: Create database named 2CSE5_719.\
<img width="940" height="316" alt="image" src="https://github.com/user-attachments/assets/0b4729c7-11e7-4b7c-b8bc-c64fdea3903f" />
1) Create EMPLOYEE Table

Aim: To create EMPLOYEE table with given constraints.
Requirement: MySQL/MariaDB database environment.
Theory: CREATE TABLE defines structure with primary key and constraints.
Query:

CREATE TABLE employee (
  empno INT(4) PRIMARY KEY,
  ename VARCHAR(20) NOT NULL,
  job VARCHAR(20),
  mgr INT(4),
  hiredate DATE,
  sal DECIMAL(10,2),
  comm DECIMAL(7,2),
  deptno INT(2)
);
2) Create DEPARTMENT Table

Aim: To create DEPARTMENT table with primary key.
Requirement: SQL environment.
Theory: Tables store structured data using rows and columns.
Query:

CREATE TABLE department (
  deptno INT(2) PRIMARY KEY,
  dname VARCHAR(15) NOT NULL
);
3) Insert Values into DEPARTMENT

Aim: To insert department records.
Requirement: Department table created.
Theory: INSERT adds rows into table.
Query:

INSERT INTO department VALUES (10,'RESEARCH');
INSERT INTO department VALUES (20,'ACCOUNTING');
INSERT INTO department VALUES (30,'SALES');
INSERT INTO department VALUES (40,'OPERATIONS');
4) Insert Values into EMPLOYEE

Aim: To insert employee data into table.
Requirement: Employee table created.
Theory: INSERT INTO adds records row-wise.
Query:

INSERT INTO employee VALUES (7369,'SMITH','CLERK',7902,'1980-12-17',800,NULL,20);
INSERT INTO employee VALUES (7499,'ALLEN','SALESMAN',7698,'1981-02-20',1600,300,30);
INSERT INTO employee VALUES (7521,'WARD','SALESMAN',7698,'1981-02-22',1250,300,30);
INSERT INTO employee VALUES (7566,'JONES','MANAGER',7839,'1981-04-02',2975,NULL,20);
INSERT INTO employee VALUES (7654,'MARTIN','SALESMAN',7698,'1981-09-28',1250,1400,30);
INSERT INTO employee VALUES (7698,'BLAKE','MANAGER',7839,'1981-05-01',2850,NULL,30);
INSERT INTO employee VALUES (7782,'CLARK','MANAGER',7839,'1981-06-09',2450,NULL,20);
INSERT INTO employee VALUES (7788,'SCOTT','ANALYST',7566,'1982-12-09',3000,NULL,40);
INSERT INTO employee VALUES (7839,'KING','PRESIDENT',NULL,'1981-11-17',5000,NULL,20);
INSERT INTO employee VALUES (7844,'TURNER','SALESMAN',7698,'1981-09-08',1500,0,30);
INSERT INTO employee VALUES (7876,'ADAMS','CLERK',7788,'1983-01-12',1100,NULL,20);
INSERT INTO employee VALUES (7900,'JAMES','CLERK',7698,'1981-12-03',950,NULL,30);
INSERT INTO employee VALUES (7902,'FORD','ANALYST',7566,'1981-12-03',3000,NULL,20);
INSERT INTO employee VALUES (7934,'MILLER','CLERK',7782,'1982-01-23',1300,NULL,10);
5) Display Table Data

Aim: To view records stored in tables.
Requirement: Tables with inserted data.
Theory: SELECT retrieves data from tables.
Query:

SELECT * FROM employee;
SELECT * FROM department;
