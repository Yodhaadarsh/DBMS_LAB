**Aim: To create a new database.**
Requirement: MySQL/MariaDB environment.
Theory: Database stores tables and related data.\
Query: CREATE DATABASE 2cse17g1_719;
<img width="909" height="108" alt="image" src="https://github.com/user-attachments/assets/9de80e6e-972d-4d33-8bfc-4a945266818c" />

✅ STEP 2 – Use Database

**Aim: To select database for operations.**
Requirement: Created database.
Theory: USE command activates a database.\
Query:USE 2cse17g1_719;

✅ STEP 3 – Create DEPARTMENT Table

**Aim: To create department table.**
Requirement: Database selected.
Theory: Table stores structured records.\
Query:CREATE TABLE department (
  deptno INT PRIMARY KEY,
  dname VARCHAR(15) NOT NULL
);
<img width="1008" height="502" alt="image" src="https://github.com/user-attachments/assets/9bd152eb-4c1d-4c07-9a47-ef96b1266911" />


✅ STEP 4 – Create EMPLOYEE Table

**Aim: To create employee table with constraints.**
Requirement: Department table exists.
Theory: Tables define schema using columns and constraints.\
Query:CREATE TABLE employee (
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

**Aim: To insert department records.**
Requirement: Department table.
Theory: INSERT adds rows.
Query: INSERT INTO department VALUES (10,'RESEARCH');
INSERT INTO department VALUES (20,'ACCOUNTING');
INSERT INTO department VALUES (30,'SALES');
INSERT INTO department VALUES (40,'OPERATIONS');
<img width="810" height="263" alt="image" src="https://github.com/user-attachments/assets/e6f46a60-a5c4-4867-b216-2739d1dda784" />

✅ STEP 6 – Insert into EMPLOYEE

Aim: To insert employee records.
Requirement: Employee table.
Theory: Data is inserted row-wise.
\Query:

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
\Query:

SELECT * FROM employee;
SELECT * FROM department;
<img width="865" height="454" alt="image" src="https://github.com/user-attachments/assets/1ae76529-b95e-47ec-b8e7-f0bb671a9dd9" />
1) List all distinct jobs

Aim: To display unique job roles.
Requirement: Employee table with job column.
Theory: DISTINCT removes duplicate values.
\Query:

SELECT DISTINCT job FROM employee;
<img width="628" height="355" alt="image" src="https://github.com/user-attachments/assets/7ff5ef30-0eb2-4988-8380-8a2d05359e84" />

2) Employees in department 30

Aim: To display employees working in department 30.
Requirement: Employee table with deptno.
Theory: WHERE filters records.
\Query:

SELECT * FROM employee
WHERE deptno = 30;
<img width="1090" height="421" alt="image" src="https://github.com/user-attachments/assets/012dc430-a389-4491-8688-e07b04793b9a" />

3) Departments greater than 20

Aim: To display department numbers and names greater than 20.
Requirement: Department table.
Theory: Comparison operators filter numeric values.
\Query:

SELECT deptno, dname
FROM department
WHERE deptno > 20;
<img width="767" height="345" alt="image" src="https://github.com/user-attachments/assets/dac03d3f-476a-4b08-bb57-e92c0550066e" />

4) Managers and clerks in dept 30

Aim: To display managers and clerks in department 30.
Requirement: Employee table.
Theory: IN operator checks multiple values.
\Query:

SELECT *
FROM employee
WHERE deptno = 30
AND job IN ('MANAGER','CLERK');
<img width="843" height="392" alt="image" src="https://github.com/user-attachments/assets/8737bdc7-4997-4a56-9956-0e51f50eb086" />

5) Clerk details

Aim: To display name, number and department of clerks.
Requirement: Employee table.
Theory: SELECT specific columns.
\Query:

SELECT ename, empno, deptno
FROM employee
WHERE job = 'CLERK';
<img width="843" height="392" alt="image" src="https://github.com/user-attachments/assets/c5d1416c-3e20-4265-a7e8-f79656c53988" />


6) Managers not in dept 30

Aim: To display managers excluding department 30.
Requirement: Employee table.
Theory: <> means NOT EQUAL.
\Query:

SELECT *
FROM employee
WHERE job = 'MANAGER'
AND deptno <> 30;
<img width="933" height="290" alt="image" src="https://github.com/user-attachments/assets/eb3d8e4f-9588-4315-b82c-5edd49376f93" />

7) Dept 10 employees not manager/clerk

Aim: To display employees of dept 10 excluding managers and clerks.
Requirement: Employee table.
Theory: NOT IN excludes values.
\Query:

SELECT *
FROM employee
WHERE deptno = 10
AND job NOT IN ('MANAGER','CLERK');
<img width="824" height="212" alt="image" src="https://github.com/user-attachments/assets/27bd0ff2-379d-4aa0-b286-691708b6679c" />

8) Salary between 1200 and 1400

Aim: To find employees earning in given range.
Requirement: Salary column.
Theory: BETWEEN filters range values.
\Query:

SELECT ename, job
FROM employee
WHERE sal BETWEEN 1200 AND 1400;
<img width="776" height="367" alt="image" src="https://github.com/user-attachments/assets/3e550c35-1961-4b89-b0bf-0b6841528a0a" />

9) Clerk, Analyst or Salesman

Aim: To display employees with specific job roles.
Requirement: Employee job column.
Theory: IN operator matches multiple values.
\Query:

SELECT ename, deptno
FROM employee
WHERE job IN ('CLERK','ANALYST','SALESMAN');
<img width="771" height="548" alt="image" src="https://github.com/user-attachments/assets/99ef1885-9ea5-4d9c-9496-1c99ece7f892" />

10) Names starting with M

Aim: To display employees whose names start with M.
Requirement: Employee name column.
Theory: LIKE performs pattern matching.
\Query:

SELECT ename, deptno
FROM employee
WHERE ename LIKE 'M%';
<img width="772" height="354" alt="image" src="https://github.com/user-attachments/assets/893454ee-e950-4015-869f-495bb64bc987" />
1) Dept 30 employees sorted by salary

Aim: To display employees in dept 30 sorted by salary descending.
Requirement: Employee table with deptno and salary.
Theory: ORDER BY sorts records.
\Query:

SELECT ename, job
FROM employee
WHERE deptno = 30
ORDER BY sal DESC;
<img width="1088" height="275" alt="image" src="https://github.com/user-attachments/assets/880cf944-7174-401d-8de3-bc8f77686143" />

2) Name 5 letters (A___N)

Aim: To find employees with 5-letter names starting with A and ending with N.
Requirement: Employee name column.
Theory: LIKE with underscore (_) matches fixed length.
\Query:

SELECT job, deptno
FROM employee
WHERE ename LIKE 'A___N';
<img width="1089" height="192" alt="image" src="https://github.com/user-attachments/assets/616dfafc-ee09-4f83-b3d5-49b27523b0c0" />

3) Names starting with S

Aim: To display names starting with S.
Requirement: Employee name field.
Theory: LIKE 'S%' matches starting pattern.
\Query:

SELECT ename
FROM employee
WHERE ename LIKE 'S%';
<img width="1089" height="241" alt="image" src="https://github.com/user-attachments/assets/9c9177be-b75d-490d-a125-d8cdf23c3245" />

4) Names ending with S

Aim: To display names ending with S.
Requirement: Employee name field.
Theory: LIKE '%S' matches ending pattern.
\Query:

SELECT ename
FROM employee
WHERE ename LIKE '%S';
<img width="1088" height="268" alt="image" src="https://github.com/user-attachments/assets/533e7f53-cecf-4066-be0e-5bca8c71a5a4" />

5) Dept or Job condition

Aim: To display employees in specific departments or job roles.
Requirement: Employee table.
Theory: OR combines multiple conditions.
\Query:

SELECT ename
FROM employee
WHERE deptno IN (10,20,40)
OR job IN ('CLERK','SALESMAN','ANALYST');
<img width="995" height="436" alt="image" src="https://github.com/user-attachments/assets/86a07dd1-80ce-4968-b6a8-45b4d0560d0a" />

6) Employees earning commission

Aim: To display employees receiving commission.
Requirement: Commission column.
Theory: IS NOT NULL checks values.
\Query:

SELECT empno, ename
FROM employee
WHERE comm IS NOT NULL;
<img width="846" height="169" alt="image" src="https://github.com/user-attachments/assets/da4ccca7-739d-4e94-89c6-6b26e6dd1069" />

7) Total salary (salary + commission)

Aim: To calculate total salary.
Requirement: Salary and commission columns.
Theory: Arithmetic operations compute values.
\Query:

SELECT empno, (sal + IFNULL(comm,0)) AS total_salary
FROM employee;
<img width="1505" height="314" alt="image" src="https://github.com/user-attachments/assets/e49dfee2-677e-4a23-8898-d238f3f5c85c" />

8) Annual salary

Aim: To calculate annual salary.
Requirement: Salary column.
Theory: Multiplication derives yearly salary.
\Query:

SELECT empno, sal * 12 AS annual_salary
FROM employee;
<img width="940" height="665" alt="image" src="https://github.com/user-attachments/assets/1e325782-49dc-43d1-a7c1-03a9f013a927" />

9) Clerks with salary > 3000

Aim: To display clerks earning more than 3000.
Requirement: Employee table.
Theory: WHERE filters multiple conditions.
\Query:

SELECT ename
FROM employee
WHERE job = 'CLERK'
AND sal > 3000;
<img width="719" height="204" alt="image" src="https://github.com/user-attachments/assets/40fdfb3d-30c9-47d5-af27-50f43552338f" />

10) Clerk, salesman, analyst with salary > 3000

Aim: To display employees in specific roles earning high salary.
Requirement: Employee table.
Theory: IN + AND filters multiple conditions.
\Query:

SELECT ename
FROM employee
WHERE job IN ('CLERK','SALESMAN','ANALYST')
AND sal > 3000;
<img width="978" height="212" alt="image" src="https://github.com/user-attachments/assets/3e869426-ee7d-4918-a722-164bdc09e2c8" />
1) Employees before 30-Jun-80 or after 31-Dec-81

Aim: To display employees based on joining date condition.
Requirement: Employee table with hiredate.
Theory: Date comparison filters records.
\Query:

SELECT * FROM employee
WHERE hiredate < '1980-06-30'
OR hiredate > '1981-12-31';
<img width="940" height="316" alt="image" src="https://github.com/user-attachments/assets/0374e0d1-8c5c-4f7c-b05f-8cd666e08297" />

2) Names with second letter A

Aim: To display employees whose second letter is A.
Requirement: Employee name column.
Theory: LIKE with '_' matches position.
\Query:

SELECT ename FROM employee
WHERE ename LIKE '_A%';
<img width="940" height="554" alt="image" src="https://github.com/user-attachments/assets/9b7e1a79-e9ee-47c5-b312-9e7d64810bca" />

3) Names exactly 5 characters

Aim: To display employees with 5-letter names.
Requirement: Employee table.
Theory: LENGTH function counts characters.
\Query:

SELECT ename FROM employee
WHERE LENGTH(ename) = 5;
<img width="1021" height="322" alt="image" src="https://github.com/user-attachments/assets/c457fa59-58cd-4bbb-b4a5-f2d36c81e0c4" />

4) Names with second letter A (repeat)

Aim: To identify employees with second letter A.
Requirement: Employee name column.
Theory: Pattern matching.
\Query:

SELECT ename FROM employee
WHERE ename LIKE '_A%';
<img width="1025" height="121" alt="image" src="https://github.com/user-attachments/assets/b634acba-653c-4a96-b330-1c05807de722" />

5) Not salesman, clerk or analyst

Aim: To display employees excluding specific roles.
Requirement: Employee job column.
Theory: NOT IN excludes multiple values.
\Query:

SELECT ename FROM employee
WHERE job NOT IN ('SALESMAN','CLERK','ANALYST');
<img width="940" height="409" alt="image" src="https://github.com/user-attachments/assets/77b16327-6b94-4fd7-8483-c0d87d840ea4" />

6) Annual salary sorted highest first

Aim: To display annual salary in descending order.
Requirement: Salary column.
Theory: ORDER BY sorts results.
\Query:

SELECT ename, sal*12 AS annual_salary
FROM employee
ORDER BY annual_salary DESC;
<img width="940" height="665" alt="image" src="https://github.com/user-attachments/assets/13abdda6-a62e-4cb9-969a-db4a8006f9ee" />

7) Salary components (HRA, DA, PF, Total)

Aim: To calculate salary components.
Requirement: Salary column.
Theory: Arithmetic expressions compute derived values.
\Query:

SELECT ename, sal,
sal*0.15 AS hra,
sal*0.10 AS da,
sal*0.05 AS pf,
(sal + sal*0.15 + sal*0.10 - sal*0.05) AS totalsal
FROM employee
ORDER BY totalsal;
<img width="940" height="750" alt="image" src="https://github.com/user-attachments/assets/cd693a62-01cb-4acb-a778-cda784065445" />

8) Increase salary by 10% (no commission)

Aim: To update salary for employees without commission.
Requirement: Salary and commission column.
Theory: UPDATE modifies data conditionally.
\Query:

UPDATE employee
SET sal = sal * 1.10
WHERE comm IS NULL;
<img width="940" height="252" alt="image" src="https://github.com/user-attachments/assets/85a2a271-6132-4bf1-9e45-f45c048d258c" />

9) Salary > 3000 after 20% increment

Aim: To find employees with increased salary above 3000.
Requirement: Salary column.
Theory: Arithmetic condition filtering.
\Query:SELECT * FROM employee
WHERE sal * 1.20 > 3000;
<img width="940" height="633" alt="image" src="https://github.com/user-attachments/assets/7b599ef2-4f0d-4f51-a2d5-0cd7bf6ce024" />

10) Salary having at least 3 digits

Aim: To display employees with salary having 3 or more digits.
Requirement: Salary column.
Theory: Numeric comparison checks digit count.
\Query:SELECT * FROM employee
WHERE sal >= 100;
<img width="940" height="971" alt="image" src="https://github.com/user-attachments/assets/31d7dacd-4ec8-49b2-9f83-9596560b008f" />
1) Total number of employees

Aim: To count total employees.
Requirement: Employee table.
Theory: COUNT counts rows.
Query:SELECT COUNT(*) AS total_employees FROM employee;
<img width="940" height="273" alt="image" src="https://github.com/user-attachments/assets/21308066-b16d-4a29-b22a-82fd6d84e3e7" />

2) Total salary of all employees

Aim: To calculate total salary.
Requirement: Salary column.
Theory: SUM adds values.
\Query:SELECT SUM(sal) AS total_salary FROM employee;
<img width="940" height="281" alt="image" src="https://github.com/user-attachments/assets/46f40816-212e-4133-b9f8-8e4eadc9bf02" />

3) Maximum salary

Aim: To find highest salary.
Requirement: Salary column.
Theory: MAX returns highest value.
\Query:SELECT MAX(sal) AS max_salary FROM employee;
<img width="940" height="279" alt="image" src="https://github.com/user-attachments/assets/24bca161-a507-412c-9017-52bd7048cbe4" />

4) Minimum salary

Aim: To find lowest salary.
Requirement: Salary column.
Theory: MIN returns lowest value.
\Query:SELECT MIN(sal) AS min_salary FROM employee;
<img width="940" height="297" alt="image" src="https://github.com/user-attachments/assets/ec580d83-a66c-4464-bc3e-d16fae08adb0" />

5) Average salary

Aim: To calculate average salary.
Requirement: Salary column.
Theory: AVG computes mean.
\Query:SELECT AVG(sal) AS avg_salary FROM employee;
<img width="940" height="295" alt="image" src="https://github.com/user-attachments/assets/33a3e4bf-5998-4ed7-9ebf-981de320d6d8" />

6) Max salary of clerk

Aim: To find highest salary among clerks.
Requirement: Job and salary columns.
Theory: Condition + MAX.
\Query:SELECT MAX(sal) FROM employee
WHERE job = 'CLERK';
<img width="940" height="450" alt="image" src="https://github.com/user-attachments/assets/c4a1cb57-1e8d-4525-a331-1770fc2b7044" />

7) Max salary in dept 20

Aim: To find highest salary in department 20.
Requirement: Deptno column.
\Query:SELECT MAX(sal) FROM employee
WHERE deptno = 20;
<img width="940" height="448" alt="image" src="https://github.com/user-attachments/assets/d5e93d7b-d0f7-4bdc-94f6-05cf648a1b0a" />

8) Min salary of salesman

Aim: To find lowest salary of salesmen.
Requirement: Job column.
\Query:SELECT MIN(sal) FROM employee
WHERE job = 'SALESMAN';
<img width="940" height="437" alt="image" src="https://github.com/user-attachments/assets/37479924-3863-4f87-ae33-d3bbfe1823f8" />

9) Avg salary of managers

Aim: To calculate average salary of managers.
Requirement: Job column.
\Query:SELECT AVG(sal) FROM employee
WHERE job = 'MANAGER';
<img width="940" height="443" alt="image" src="https://github.com/user-attachments/assets/5af19be9-bc58-4a2a-829d-88b93b7824ce" />

10) Total salary of analyst in dept 40

Aim: To calculate total salary for analysts in dept 40.
Requirement: Job + deptno columns.
\Query:SELECT SUM(sal) FROM employee
WHERE job = 'ANALYST' AND deptno = 40;
<img width="940" height="482" alt="image" src="https://github.com/user-attachments/assets/fc40ad5c-ed8b-48ef-854a-6f6c4beff136" />

11) Names in uppercase

Aim: To display names in uppercase.
Requirement: Name column.
Theory: UPPER converts text.
\Query:SELECT UPPER(ename) FROM employee;
<img width="940" height="887" alt="image" src="https://github.com/user-attachments/assets/3bd4bbe8-8646-496a-81f2-908075988838" />

12) Names in lowercase

Aim: To display names in lowercase.
Requirement: Name column.
Theory: LOWER converts text.
\Query:SELECT LOWER(ename) FROM employee;
<img width="940" height="888" alt="image" src="https://github.com/user-attachments/assets/2aceff32-3ead-4552-ba90-f5d811a85e2d" />

13) Names in proper case

Aim: To display names in proper case.
Requirement: Name column.
Theory: CONCAT + functions simulate proper case in MySQL.
\Query:SELECT CONCAT(UPPER(LEFT(ename,1)), LOWER(SUBSTRING(ename,2)))
FROM employee;
<img width="940" height="683" alt="image" src="https://github.com/user-attachments/assets/36c50791-b40f-4b11-ad6b-41453dc4aee1" />

14) Length of your name

Aim: To find length of a given name.
Requirement: String input.
Theory: LENGTH counts characters.
\Query:SELECT LENGTH('RAHUL');
<img width="940" height="294" alt="image" src="https://github.com/user-attachments/assets/5a590ecc-11a4-49f6-91a9-ec0e944f8d8b" />


15) Length of all employee names

Aim: To find length of each employee name.
Requirement: Employee table.
\Query:SELECT ename, LENGTH(ename) FROM employee;
<img width="940" height="748" alt="image" src="https://github.com/user-attachments/assets/c5e04723-0aa6-4fe1-a806-3efaf6855cb7" />
