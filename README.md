Aim: To create a new database.
Requirement: MySQL/MariaDB environment.
Theory: Database stores tables and related data.
Query:

CREATE DATABASE 2cse17g1_719;
<img width="909" height="108" alt="image" src="https://github.com/user-attachments/assets/9de80e6e-972d-4d33-8bfc-4a945266818c" />

✅ STEP 2 – Use Database

Aim: To select database for operations.
Requirement: Created database.
Theory: USE command activates a database.
Query:

USE 2cse17g1_719;

✅ STEP 3 – Create DEPARTMENT Table

Aim: To create department table.
Requirement: Database selected.
Theory: Table stores structured records.
Query:

CREATE TABLE department (
  deptno INT PRIMARY KEY,
  dname VARCHAR(15) NOT NULL
);
<img width="1008" height="502" alt="image" src="https://github.com/user-attachments/assets/9bd152eb-4c1d-4c07-9a47-ef96b1266911" />


✅ STEP 4 – Create EMPLOYEE Table

Aim: To create employee table with constraints.
Requirement: Department table exists.
Theory: Tables define schema using columns and constraints.
Query:

CREATE TABLE employee (
  empno INT PRIMARY KEY,
  ename VARCHAR(20) NOT NULL,
  job VARCHAR(20),
  mgr INT,
  hiredate DATE,
  sal DECIMAL(10,2),
  comm DECIMAL(7,2),
  deptno INT,
  FOREIGN KEY (deptno) REFERENCES department(deptno)
);
<img width="659" height="358" alt="image" src="https://github.com/user-attachments/assets/a2cdc662-a051-42a3-aa75-e6e1967bd9b6" />


✅ STEP 5 – Insert into DEPARTMENT

Aim: To insert department records.
Requirement: Department table.
Theory: INSERT adds rows.
Query:

INSERT INTO department VALUES (10,'RESEARCH');
INSERT INTO department VALUES (20,'ACCOUNTING');
INSERT INTO department VALUES (30,'SALES');
INSERT INTO department VALUES (40,'OPERATIONS');
<img width="810" height="263" alt="image" src="https://github.com/user-attachments/assets/e6f46a60-a5c4-4867-b216-2739d1dda784" />

✅ STEP 6 – Insert into EMPLOYEE

Aim: To insert employee records.
Requirement: Employee table.
Theory: Data is inserted row-wise.
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
<img width="1008" height="502" alt="image" src="https://github.com/user-attachments/assets/1172838d-5d4f-4403-b748-de3224058ee0" />

✅ STEP 7 – Display Data

Aim: To view inserted records.
Requirement: Tables populated.
Theory: SELECT retrieves data.
Query:

SELECT * FROM employee;
SELECT * FROM department;
<img width="865" height="454" alt="image" src="https://github.com/user-attachments/assets/1ae76529-b95e-47ec-b8e7-f0bb671a9dd9" />
1) List all distinct jobs

Aim: To display unique job roles.
Requirement: Employee table with job column.
Theory: DISTINCT removes duplicate values.
Query:

SELECT DISTINCT job FROM employee;
<img width="628" height="355" alt="image" src="https://github.com/user-attachments/assets/7ff5ef30-0eb2-4988-8380-8a2d05359e84" />

2) Employees in department 30

Aim: To display employees working in department 30.
Requirement: Employee table with deptno.
Theory: WHERE filters records.
Query:

SELECT * FROM employee
WHERE deptno = 30;
<img width="1090" height="421" alt="image" src="https://github.com/user-attachments/assets/012dc430-a389-4491-8688-e07b04793b9a" />

3) Departments greater than 20

Aim: To display department numbers and names greater than 20.
Requirement: Department table.
Theory: Comparison operators filter numeric values.
Query:

SELECT deptno, dname
FROM department
WHERE deptno > 20;
<img width="767" height="345" alt="image" src="https://github.com/user-attachments/assets/dac03d3f-476a-4b08-bb57-e92c0550066e" />

4) Managers and clerks in dept 30

Aim: To display managers and clerks in department 30.
Requirement: Employee table.
Theory: IN operator checks multiple values.
Query:

SELECT *
FROM employee
WHERE deptno = 30
AND job IN ('MANAGER','CLERK');
<img width="843" height="392" alt="image" src="https://github.com/user-attachments/assets/8737bdc7-4997-4a56-9956-0e51f50eb086" />

5) Clerk details

Aim: To display name, number and department of clerks.
Requirement: Employee table.
Theory: SELECT specific columns.
Query:

SELECT ename, empno, deptno
FROM employee
WHERE job = 'CLERK';
<img width="843" height="392" alt="image" src="https://github.com/user-attachments/assets/c5d1416c-3e20-4265-a7e8-f79656c53988" />


6) Managers not in dept 30

Aim: To display managers excluding department 30.
Requirement: Employee table.
Theory: <> means NOT EQUAL.
Query:

SELECT *
FROM employee
WHERE job = 'MANAGER'
AND deptno <> 30;
<img width="933" height="290" alt="image" src="https://github.com/user-attachments/assets/eb3d8e4f-9588-4315-b82c-5edd49376f93" />

7) Dept 10 employees not manager/clerk

Aim: To display employees of dept 10 excluding managers and clerks.
Requirement: Employee table.
Theory: NOT IN excludes values.
Query:

SELECT *
FROM employee
WHERE deptno = 10
AND job NOT IN ('MANAGER','CLERK');
<img width="824" height="212" alt="image" src="https://github.com/user-attachments/assets/27bd0ff2-379d-4aa0-b286-691708b6679c" />

8) Salary between 1200 and 1400

Aim: To find employees earning in given range.
Requirement: Salary column.
Theory: BETWEEN filters range values.
Query:

SELECT ename, job
FROM employee
WHERE sal BETWEEN 1200 AND 1400;
<img width="776" height="367" alt="image" src="https://github.com/user-attachments/assets/3e550c35-1961-4b89-b0bf-0b6841528a0a" />

9) Clerk, Analyst or Salesman

Aim: To display employees with specific job roles.
Requirement: Employee job column.
Theory: IN operator matches multiple values.
Query:

SELECT ename, deptno
FROM employee
WHERE job IN ('CLERK','ANALYST','SALESMAN');
<img width="771" height="548" alt="image" src="https://github.com/user-attachments/assets/99ef1885-9ea5-4d9c-9496-1c99ece7f892" />

10) Names starting with M

Aim: To display employees whose names start with M.
Requirement: Employee name column.
Theory: LIKE performs pattern matching.
Query:

SELECT ename, deptno
FROM employee
WHERE ename LIKE 'M%';
<img width="772" height="354" alt="image" src="https://github.com/user-attachments/assets/893454ee-e950-4015-869f-495bb64bc987" />
1) Dept 30 employees sorted by salary

Aim: To display employees in dept 30 sorted by salary descending.
Requirement: Employee table with deptno and salary.
Theory: ORDER BY sorts records.
Query:

SELECT ename, job
FROM employee
WHERE deptno = 30
ORDER BY sal DESC;
2) Name 5 letters (A___N)

Aim: To find employees with 5-letter names starting with A and ending with N.
Requirement: Employee name column.
Theory: LIKE with underscore (_) matches fixed length.
Query:

SELECT job, deptno
FROM employee
WHERE ename LIKE 'A___N';
3) Names starting with S

Aim: To display names starting with S.
Requirement: Employee name field.
Theory: LIKE 'S%' matches starting pattern.
Query:

SELECT ename
FROM employee
WHERE ename LIKE 'S%';
4) Names ending with S

Aim: To display names ending with S.
Requirement: Employee name field.
Theory: LIKE '%S' matches ending pattern.
Query:

SELECT ename
FROM employee
WHERE ename LIKE '%S';
5) Dept or Job condition

Aim: To display employees in specific departments or job roles.
Requirement: Employee table.
Theory: OR combines multiple conditions.
Query:

SELECT ename
FROM employee
WHERE deptno IN (10,20,40)
OR job IN ('CLERK','SALESMAN','ANALYST');
6) Employees earning commission

Aim: To display employees receiving commission.
Requirement: Commission column.
Theory: IS NOT NULL checks values.
Query:

SELECT empno, ename
FROM employee
WHERE comm IS NOT NULL;
7) Total salary (salary + commission)

Aim: To calculate total salary.
Requirement: Salary and commission columns.
Theory: Arithmetic operations compute values.
Query:

SELECT empno, (sal + IFNULL(comm,0)) AS total_salary
FROM employee;
8) Annual salary

Aim: To calculate annual salary.
Requirement: Salary column.
Theory: Multiplication derives yearly salary.
Query:

SELECT empno, sal * 12 AS annual_salary
FROM employee;
9) Clerks with salary > 3000

Aim: To display clerks earning more than 3000.
Requirement: Employee table.
Theory: WHERE filters multiple conditions.
Query:

SELECT ename
FROM employee
WHERE job = 'CLERK'
AND sal > 3000;
10) Clerk, salesman, analyst with salary > 3000

Aim: To display employees in specific roles earning high salary.
Requirement: Employee table.
Theory: IN + AND filters multiple conditions.
Query:

SELECT ename
FROM employee
WHERE job IN ('CLERK','SALESMAN','ANALYST')
AND sal > 3000;
