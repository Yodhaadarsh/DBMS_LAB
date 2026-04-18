**Aim: To create a new database.**
Requirement: MySQL/MariaDB environment.\
Theory: Database stores tables and related data.\
Query: CREATE DATABASE 2cse17g1_719;
<img width="909" height="108" alt="image" src="https://github.com/user-attachments/assets/9de80e6e-972d-4d33-8bfc-4a945266818c" />

✅ STEP 2 – Use Database

**Aim: To select database for operations.**
Requirement: Created database.\
Theory: USE command activates a database.\
Query:USE 2cse17g1_719;

✅ STEP 3 – Create DEPARTMENT Table

**Aim: To create department table.**
Requirement: Database selected.\
Theory: Table stores structured records.\
Query:CREATE TABLE department (
  deptno INT PRIMARY KEY,
  dname VARCHAR(15) NOT NULL
);
<img width="1008" height="502" alt="image" src="https://github.com/user-attachments/assets/9bd152eb-4c1d-4c07-9a47-ef96b1266911" />


✅ STEP 4 – Create EMPLOYEE Table

**Aim: To create employee table with constraints.**
Requirement: Department table exists.\
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
Requirement: Department table.\
Theory: INSERT adds rows.\
Query: INSERT INTO department VALUES (10,'RESEARCH');
INSERT INTO department VALUES (20,'ACCOUNTING');
INSERT INTO department VALUES (30,'SALES');
INSERT INTO department VALUES (40,'OPERATIONS');
<img width="810" height="263" alt="image" src="https://github.com/user-attachments/assets/e6f46a60-a5c4-4867-b216-2739d1dda784" />

✅ STEP 6 – Insert into EMPLOYEE

**Aim: To insert employee records.**\
Requirement: Employee table.\
Theory: Data is inserted row-wise.
Query: INSERT INTO employee VALUES (7369,'SMITH','CLERK',7902,'1980-12-17',800,NULL,20);
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

**Aim: To view inserted records.**\
Requirement: Tables populated.\
Theory: SELECT retrieves data.\
Query: SELECT * FROM employee;
SELECT * FROM department;
<img width="865" height="454" alt="image" src="https://github.com/user-attachments/assets/1ae76529-b95e-47ec-b8e7-f0bb671a9dd9" />
1) List all distinct jobs

**Aim: To display unique job roles.**\
Requirement: Employee table with job column.\
Theory: DISTINCT removes duplicate values.\
Query: SELECT DISTINCT job FROM employee;
<img width="628" height="355" alt="image" src="https://github.com/user-attachments/assets/7ff5ef30-0eb2-4988-8380-8a2d05359e84" />

2) Employees in department 30

**Aim: To display employees working in department 30.**\
Requirement: Employee table with deptno.\
Theory: WHERE filters records.\
Query: SELECT * FROM employee
WHERE deptno = 30;
<img width="1090" height="421" alt="image" src="https://github.com/user-attachments/assets/012dc430-a389-4491-8688-e07b04793b9a" />

3) Departments greater than 20

**Aim: To display department numbers and names greater than 20.**\
Requirement: Department table.\
Theory: Comparison operators filter numeric values.\
Query: SELECT deptno, dname
FROM department
WHERE deptno > 20;
<img width="767" height="345" alt="image" src="https://github.com/user-attachments/assets/dac03d3f-476a-4b08-bb57-e92c0550066e" />

4) Managers and clerks in dept 30

**Aim: To display managers and clerks in department 30.**
Requirement: Employee table.\
Theory: IN operator checks multiple values.\
Query: SELECT *
FROM employee
WHERE deptno = 30
AND job IN ('MANAGER','CLERK');
<img width="843" height="392" alt="image" src="https://github.com/user-attachments/assets/8737bdc7-4997-4a56-9956-0e51f50eb086" />

5) Clerk details

**Aim: To display name, number and department of clerks.**
Requirement: Employee table.\
Theory: SELECT specific columns.\
Query: SELECT ename, empno, deptno
FROM employee
WHERE job = 'CLERK';
<img width="843" height="392" alt="image" src="https://github.com/user-attachments/assets/c5d1416c-3e20-4265-a7e8-f79656c53988" />


6) Managers not in dept 30

**Aim: To display managers excluding department 30.**\
Requirement: Employee table.\
Theory: <> means NOT EQUAL.\
Query: SELECT *
FROM employee
WHERE job = 'MANAGER'
AND deptno <> 30;
<img width="933" height="290" alt="image" src="https://github.com/user-attachments/assets/eb3d8e4f-9588-4315-b82c-5edd49376f93" />

7) Dept 10 employees not manager/clerk

**Aim: To display employees of dept 10 excluding managers and clerks.**\
Requirement: Employee table.\
Theory: NOT IN excludes values.\
Query: SELECT *
FROM employee
WHERE deptno = 10
AND job NOT IN ('MANAGER','CLERK');
<img width="824" height="212" alt="image" src="https://github.com/user-attachments/assets/27bd0ff2-379d-4aa0-b286-691708b6679c" />

8) Salary between 1200 and 1400

**Aim: To find employees earning in given range.**\
Requirement: Salary column.\
Theory: BETWEEN filters range values.\
Query: SELECT ename, job
FROM employee
WHERE sal BETWEEN 1200 AND 1400;
<img width="776" height="367" alt="image" src="https://github.com/user-attachments/assets/3e550c35-1961-4b89-b0bf-0b6841528a0a" />

9) Clerk, Analyst or Salesman

**Aim: To display employees with specific job roles.**
Requirement: Employee job column.\
Theory: IN operator matches multiple values.\
Query: SELECT ename, deptno
FROM employee
WHERE job IN ('CLERK','ANALYST','SALESMAN');
<img width="771" height="548" alt="image" src="https://github.com/user-attachments/assets/99ef1885-9ea5-4d9c-9496-1c99ece7f892" />

10) Names starting with M

**Aim: To display employees whose names start with M.**\
Requirement: Employee name column.\
Theory: LIKE performs pattern matching.\
Query: SELECT ename, deptno
FROM employee
WHERE ename LIKE 'M%';
<img width="772" height="354" alt="image" src="https://github.com/user-attachments/assets/893454ee-e950-4015-869f-495bb64bc987" />
1) Dept 30 employees sorted by salary

**Aim: To display employees in dept 30 sorted by salary descending.** \
Requirement: Employee table with deptno and salary.\
Theory: ORDER BY sorts records.\
Query: SELECT ename, job
FROM employee
WHERE deptno = 30
ORDER BY sal DESC;
<img width="1088" height="275" alt="image" src="https://github.com/user-attachments/assets/880cf944-7174-401d-8de3-bc8f77686143" />

2) Name 5 letters (A___N)

**Aim: To find employees with 5-letter names starting with A and ending with N.** \
Requirement: Employee name column.\
Theory: LIKE with underscore (_) matches fixed length.\
Query: SELECT job, deptno
FROM employee
WHERE ename LIKE 'A___N';
<img width="1089" height="192" alt="image" src="https://github.com/user-attachments/assets/616dfafc-ee09-4f83-b3d5-49b27523b0c0" />

3) Names starting with S

**Aim: To display names starting with S.** \
Requirement: Employee name field.\
Theory: LIKE 'S%' matches starting pattern.\
Query: SELECT ename
FROM employee
WHERE ename LIKE 'S%';
<img width="1089" height="241" alt="image" src="https://github.com/user-attachments/assets/9c9177be-b75d-490d-a125-d8cdf23c3245" />

4) Names ending with S

**Aim: To display names ending with S.** \
Requirement: Employee name field.\
Theory: LIKE '%S' matches ending pattern.\
Query: SELECT ename
FROM employee
WHERE ename LIKE '%S';
<img width="1088" height="268" alt="image" src="https://github.com/user-attachments/assets/533e7f53-cecf-4066-be0e-5bca8c71a5a4" />

5) Dept or Job condition

**Aim: To display employees in specific departments or job roles.** \
Requirement: Employee table.\
Theory: OR combines multiple conditions.\
Query: SELECT ename
FROM employee
WHERE deptno IN (10,20,40)
OR job IN ('CLERK','SALESMAN','ANALYST');
<img width="995" height="436" alt="image" src="https://github.com/user-attachments/assets/86a07dd1-80ce-4968-b6a8-45b4d0560d0a" />

6) Employees earning commission

**Aim: To display employees receiving commission.** \
Requirement: Commission column.\
Theory: IS NOT NULL checks values.\
Query: SELECT empno, ename
FROM employee
WHERE comm IS NOT NULL;
<img width="846" height="169" alt="image" src="https://github.com/user-attachments/assets/da4ccca7-739d-4e94-89c6-6b26e6dd1069" />

7) Total salary (salary + commission)

**Aim: To calculate total salary.** \
Requirement: Salary and commission columns.\
Theory: Arithmetic operations compute values.\
Query: SELECT empno, (sal + IFNULL(comm,0)) AS total_salary
FROM employee;
<img width="1505" height="314" alt="image" src="https://github.com/user-attachments/assets/e49dfee2-677e-4a23-8898-d238f3f5c85c" />

8) Annual salary

**Aim: To calculate annual salary.** \
Requirement: Salary column.\
Theory: Multiplication derives yearly salary.\
Query: SELECT empno, sal * 12 AS annual_salary
FROM employee;
<img width="940" height="665" alt="image" src="https://github.com/user-attachments/assets/1e325782-49dc-43d1-a7c1-03a9f013a927" />

9) Clerks with salary > 3000

**Aim: To display clerks earning more than 3000.** \
Requirement: Employee table.\
Theory: WHERE filters multiple conditions.\
Query: SELECT ename
FROM employee
WHERE job = 'CLERK'
AND sal > 3000;
<img width="719" height="204" alt="image" src="https://github.com/user-attachments/assets/40fdfb3d-30c9-47d5-af27-50f43552338f" />

10) Clerk, salesman, analyst with salary > 3000

**Aim: To display employees in specific roles earning high salary.** \
Requirement: Employee table.\
Theory: IN + AND filters multiple conditions.\
Query: SELECT ename
FROM employee
WHERE job IN ('CLERK','SALESMAN','ANALYST')
AND sal > 3000;
<img width="978" height="212" alt="image" src="https://github.com/user-attachments/assets/3e869426-ee7d-4918-a722-164bdc09e2c8" />
1) Employees before 30-Jun-80 or after 31-Dec-81

**Aim: To display employees based on joining date condition.** \
Requirement: Employee table with hiredate.\
Theory: Date comparison filters records.\
Query: SELECT * FROM employee
WHERE hiredate < '1980-06-30'
OR hiredate > '1981-12-31';
<img width="940" height="316" alt="image" src="https://github.com/user-attachments/assets/0374e0d1-8c5c-4f7c-b05f-8cd666e08297" />

2) Names with second letter A

**Aim: To display employees whose second letter is A.** \
Requirement: Employee name column.\
Theory: LIKE with '_' matches position.\
Query: SELECT ename FROM employee
WHERE ename LIKE '_A%';
<img width="940" height="554" alt="image" src="https://github.com/user-attachments/assets/9b7e1a79-e9ee-47c5-b312-9e7d64810bca" />

3) Names exactly 5 characters

**Aim: To display employees with 5-letter names.** \
Requirement: Employee table.\
Theory: LENGTH function counts characters.\
Query: SELECT ename FROM employee
WHERE LENGTH(ename) = 5;
<img width="1021" height="322" alt="image" src="https://github.com/user-attachments/assets/c457fa59-58cd-4bbb-b4a5-f2d36c81e0c4" />

4) Names with second letter A (repeat)

**Aim: To identify employees with second letter A.** \
Requirement: Employee name column.\
Theory: Pattern matching.\
Query: SELECT ename FROM employee
WHERE ename LIKE '_A%';
<img width="1025" height="121" alt="image" src="https://github.com/user-attachments/assets/b634acba-653c-4a96-b330-1c05807de722" />

5) Not salesman, clerk or analyst

**Aim: To display employees excluding specific roles.** \
Requirement: Employee job column.\
Theory: NOT IN excludes multiple values.\
Query: SELECT ename FROM employee
WHERE job NOT IN ('SALESMAN','CLERK','ANALYST');
<img width="940" height="409" alt="image" src="https://github.com/user-attachments/assets/77b16327-6b94-4fd7-8483-c0d87d840ea4" />

6) Annual salary sorted highest first

**Aim: To display annual salary in descending order.** \
Requirement: Salary column.\
Theory: ORDER BY sorts results.\
Query: SELECT ename, sal*12 AS annual_salary
FROM employee
ORDER BY annual_salary DESC;
<img width="940" height="665" alt="image" src="https://github.com/user-attachments/assets/13abdda6-a62e-4cb9-969a-db4a8006f9ee" />

7) Salary components (HRA, DA, PF, Total)

**Aim: To calculate salary components.** \
Requirement: Salary column.\
Theory: Arithmetic expressions compute derived values.\
Query: SELECT ename, sal,
sal*0.15 AS hra,
sal*0.10 AS da,
sal*0.05 AS pf,
(sal + sal*0.15 + sal*0.10 - sal*0.05) AS totalsal
FROM employee
ORDER BY totalsal;
<img width="940" height="750" alt="image" src="https://github.com/user-attachments/assets/cd693a62-01cb-4acb-a778-cda784065445" />

8) Increase salary by 10% (no commission)

**Aim: To update salary for employees without commission.** \
Requirement: Salary and commission column.\
Theory: UPDATE modifies data conditionally.\
Query:UPDATE employee
SET sal = sal * 1.10
WHERE comm IS NULL;
<img width="940" height="252" alt="image" src="https://github.com/user-attachments/assets/85a2a271-6132-4bf1-9e45-f45c048d258c" />

9) Salary > 3000 after 20% increment

**Aim: To find employees with increased salary above 3000.** \
Requirement: Salary column.\
Theory: Arithmetic condition filtering.\
Query:SELECT * FROM employee
WHERE sal * 1.20 > 3000;
<img width="940" height="633" alt="image" src="https://github.com/user-attachments/assets/7b599ef2-4f0d-4f51-a2d5-0cd7bf6ce024" />

10) Salary having at least 3 digits

**Aim: To display employees with salary having 3 or more digits.** \
Requirement: Salary column.\
Theory: Numeric comparison checks digit count.\
Query:SELECT * FROM employee
WHERE sal >= 100;
<img width="940" height="971" alt="image" src="https://github.com/user-attachments/assets/31d7dacd-4ec8-49b2-9f83-9596560b008f" />
1) Total number of employees

**Aim: To count total employees.** \
Requirement: Employee table.\
Theory: COUNT counts rows.\
Query:SELECT COUNT(*) AS total_employees FROM employee;
<img width="940" height="273" alt="image" src="https://github.com/user-attachments/assets/21308066-b16d-4a29-b22a-82fd6d84e3e7" />

2) Total salary of all employees

**Aim: To calculate total salary.** \
Requirement: Salary column.\
Theory: SUM adds values.\
Query:SELECT SUM(sal) AS total_salary FROM employee;
<img width="940" height="281" alt="image" src="https://github.com/user-attachments/assets/46f40816-212e-4133-b9f8-8e4eadc9bf02" />

3) Maximum salary

**Aim: To find highest salary.** \
Requirement: Salary column.\
Theory: MAX returns highest value.\
Query:SELECT MAX(sal) AS max_salary FROM employee;
<img width="940" height="279" alt="image" src="https://github.com/user-attachments/assets/24bca161-a507-412c-9017-52bd7048cbe4" />

4) Minimum salary

**Aim: To find lowest salary.** \
Requirement: Salary column.\
Theory: MIN returns lowest value.\
Query:SELECT MIN(sal) AS min_salary FROM employee;
<img width="940" height="297" alt="image" src="https://github.com/user-attachments/assets/ec580d83-a66c-4464-bc3e-d16fae08adb0" />

5) Average salary

**Aim: To calculate average salary.** \
Requirement: Salary column.\
Theory: AVG computes mean.\
Query:SELECT AVG(sal) AS avg_salary FROM employee;
<img width="940" height="295" alt="image" src="https://github.com/user-attachments/assets/33a3e4bf-5998-4ed7-9ebf-981de320d6d8" />

6) Max salary of clerk

**Aim: To find highest salary among clerks.** \
Requirement: Job and salary columns.\
Theory: Condition + MAX.\
Query:SELECT MAX(sal) FROM employee
WHERE job = 'CLERK';
<img width="940" height="450" alt="image" src="https://github.com/user-attachments/assets/c4a1cb57-1e8d-4525-a331-1770fc2b7044" />

7) Max salary in dept 20

**Aim: To find highest salary in department 20.** \
Requirement: Deptno column.\
Query:SELECT MAX(sal) FROM employee
WHERE deptno = 20;
<img width="940" height="448" alt="image" src="https://github.com/user-attachments/assets/d5e93d7b-d0f7-4bdc-94f6-05cf648a1b0a" />

8) Min salary of salesman

**Aim: To find lowest salary of salesmen.** \
Requirement: Job column.\
Query:SELECT MIN(sal) FROM employee
WHERE job = 'SALESMAN';
<img width="940" height="437" alt="image" src="https://github.com/user-attachments/assets/37479924-3863-4f87-ae33-d3bbfe1823f8" />

9) Avg salary of managers

**Aim: To calculate average salary of managers.** \
Requirement: Job column.\
Query:SELECT AVG(sal) FROM employee
WHERE job = 'MANAGER';
<img width="940" height="443" alt="image" src="https://github.com/user-attachments/assets/5af19be9-bc58-4a2a-829d-88b93b7824ce" />

10) Total salary of analyst in dept 40

**Aim: To calculate total salary for analysts in dept 40.** \
Requirement: Job + deptno columns.\
Query:SELECT SUM(sal) FROM employee
WHERE job = 'ANALYST' AND deptno = 40;
<img width="940" height="482" alt="image" src="https://github.com/user-attachments/assets/fc40ad5c-ed8b-48ef-854a-6f6c4beff136" />

11) Names in uppercase

**Aim: To display names in uppercase.** \
Requirement: Name column.\
Theory: UPPER converts text.\
Query:SELECT UPPER(ename) FROM employee;
<img width="940" height="887" alt="image" src="https://github.com/user-attachments/assets/3bd4bbe8-8646-496a-81f2-908075988838" />

12) Names in lowercase

**Aim: To display names in lowercase.** \
Requirement: Name column.\
Theory: LOWER converts text.\
Query:SELECT LOWER(ename) FROM employee;
<img width="940" height="888" alt="image" src="https://github.com/user-attachments/assets/2aceff32-3ead-4552-ba90-f5d811a85e2d" />

13) Names in proper case

**Aim: To display names in proper case.** \
Requirement: Name column.\
Theory: CONCAT + functions simulate proper case in MySQL.\
Query:SELECT CONCAT(UPPER(LEFT(ename,1)), LOWER(SUBSTRING(ename,2)))
FROM employee;
<img width="940" height="683" alt="image" src="https://github.com/user-attachments/assets/36c50791-b40f-4b11-ad6b-41453dc4aee1" />

14) Length of your name

**Aim: To find length of a given name.** \
Requirement: String input.\
Theory: LENGTH counts characters.\
Query:SELECT LENGTH('RAHUL');
<img width="940" height="294" alt="image" src="https://github.com/user-attachments/assets/5a590ecc-11a4-49f6-91a9-ec0e944f8d8b" />


15) Length of all employee names

**Aim: To find length of each employee name.** \
Requirement: Employee table.\
Query:SELECT ename, LENGTH(ename) FROM employee;
<img width="940" height="748" alt="image" src="https://github.com/user-attachments/assets/c5e04723-0aa6-4fe1-a806-3efaf6855cb7" />
1) Display empno, ename, dept name using DECODE

**Aim: To display department name instead of deptno.** \
Requirement: Employee table.\
Theory: CASE replaces DECODE in MySQL.\
Query: SELECT empno, ename,
CASE deptno
  WHEN 10 THEN 'RESEARCH'
  WHEN 20 THEN 'ACCOUNTING'
  WHEN 30 THEN 'SALES'
  WHEN 40 THEN 'OPERATIONS'
END AS dept_name
FROM employee;
<img width="940" height="1127" alt="image" src="https://github.com/user-attachments/assets/3002482f-5eef-4eb9-b505-6801c19c1efe" />

2) Display your age in days

**Aim: To calculate age in days.** \
Requirement: Date input.\
Theory: DATEDIFF finds difference in days.\
Query: SELECT DATEDIFF(CURDATE(), '2000-01-01') AS age_days;
<img width="940" height="178" alt="image" src="https://github.com/user-attachments/assets/110817a7-171f-4443-83ac-c92483d795ea" />

3) Display your age in months

**Aim: To calculate age in months.** \
Requirement: Date input.\
Theory: TIMESTAMPDIFF calculates months.\
Query: SELECT TIMESTAMPDIFF(MONTH, '2000-01-01', CURDATE()) AS age_months;
<img width="940" height="148" alt="image" src="https://github.com/user-attachments/assets/4c097f16-21bc-4d82-9339-51c00d53d83c" />

4) Display current date in full format

**Aim: To display formatted current date.** \
Requirement: System date.\
Theory: DATE_FORMAT formats date.\
Query: SELECT DATE_FORMAT(CURDATE(), '%D %M %W %Y');
<img width="940" height="162" alt="image" src="https://github.com/user-attachments/assets/4a30271b-1a70-4e6f-b33d-430dc19db064" />

5) Display formatted output for each employee

**Aim: To show formatted employee output.** \
Requirement: Employee table.\
Theory: CONCAT combines strings.\
Query: SELECT CONCAT(ename,' earns ',sal) AS output
FROM employee;
<img width="940" height="567" alt="image" src="https://github.com/user-attachments/assets/499a83aa-636d-4791-9617-5afc9354694f" />

6) Scott joining sentence

**Aim: To display Scott joining info in sentence format.** \
Requirement: Employee table.\
Query: SELECT CONCAT(ename,' has joined on ',
DATE_FORMAT(hiredate,'%W %D %M %Y'))
FROM employee
WHERE ename='SCOTT';
<img width="940" height="253" alt="image" src="https://github.com/user-attachments/assets/05eb0778-7e20-4936-b8c3-b627e9751655" />

7) Nearest Saturday after current date

**Aim: To find next Saturday.** \
Requirement: Date functions.\
Query: SELECT DATE_ADD(CURDATE(),
INTERVAL (7 - DAYOFWEEK(CURDATE())) DAY);
<img width="940" height="199" alt="image" src="https://github.com/user-attachments/assets/13a43fe3-510f-41ae-b77d-ae49765038fb" />

8) Display current time

**Aim: To display system time.** \
Requirement: System clock.\
Query: SELECT CURRENT_TIME();
<img width="940" height="353" alt="image" src="https://github.com/user-attachments/assets/cf227e6e-b0f8-4577-b2c4-92cb08cbcb24" />

9) Date 3 months before today

**Aim: To find past date.** \
Requirement: Date functions.\
Query: SELECT DATE_SUB(CURDATE(), INTERVAL 3 MONTH);
<img width="940" height="202" alt="image" src="https://github.com/user-attachments/assets/dd82f29f-0d5b-45d4-90ab-1653b9cb42de" />

10) Employees joined in December
    
**Aim: To find employees joined in December.** \
Requirement: Hiredate column.\
Query: SELECT ename
FROM employee
WHERE MONTH(hiredate) = 12;
<img width="940" height="318" alt="image" src="https://github.com/user-attachments/assets/1f6cf4f3-c85d-4c4e-8489-74f9a3460728" />

11) First 2 chars of date & last 2 of salary

**Aim: To extract parts of date and salary.** \
Requirement: Employee table.\
Query: SELECT ename,
LEFT(DATE_FORMAT(hiredate,'%d%m%Y'),2) AS first2_date,
RIGHT(sal,2) AS last2_sal
FROM employee;
<img width="940" height="204" alt="image" src="https://github.com/user-attachments/assets/9567c5a8-e9e0-4bc5-9d45-cc0f1807fe96" />

12) 10% salary equals joining year

**Aim: To compare salary and joining year.** \
Requirement: Salary + hiredate.\
Query: SELECT ename
FROM employee
WHERE sal * 0.10 = YEAR(hiredate);
<img width="940" height="406" alt="image" src="https://github.com/user-attachments/assets/2b2263a9-b493-4ceb-bf33-3e9276966ba2" />

13) Joined before 15th day

**Aim: To find employees joining before 15th.** \
Requirement: Hiredate column.\
Query:SELECT ename
FROM employee
WHERE DAY(hiredate) < 15;
<img width="940" height="597" alt="image" src="https://github.com/user-attachments/assets/79b503cb-427a-4827-a992-2ce2ebd4bdb4" />

14) Joined before 15th (same concept)

**Aim: To filter based on date.** \
Requirement: Hiredate.\
Query:SELECT ename
FROM employee
WHERE DAY(hiredate) < 15;
<img width="940" height="412" alt="image" src="https://github.com/user-attachments/assets/031f600d-2a2c-48fe-b97e-923cc9c6ad1b" />

15) Employees with joining date and dept

**Aim: To display employee with hiredate and department.** \
Requirement: Employee table.\
Query: SELECT ename, hiredate, deptno
FROM employee;
<img width="940" height="713" alt="image" src="https://github.com/user-attachments/assets/eb1ee3e0-09bd-4b86-b156-83bc6083ad66" />
1) Days remaining in current year

**Aim: To calculate remaining days in current year.** \
Requirement: System date.\
Theory: Date arithmetic calculates difference between dates.\
Query: SELECT DATEDIFF(
  STR_TO_DATE(CONCAT(YEAR(CURDATE()),'-12-31'),'%Y-%m-%d'),
  CURDATE()
) AS remaining_days;
<img width="940" height="253" alt="image" src="https://github.com/user-attachments/assets/1db662e8-4e0b-4c63-b3c5-965737d963b4" />

2) Highest, lowest salary and difference

**Aim: To find max, min salary and their difference.** \
Requirement: Employee table.
Theory: Aggregate functions compute summary values.
Query: SELECT MAX(sal) AS highest,
       MIN(sal) AS lowest,
       MAX(sal) - MIN(sal) AS difference
FROM employee;
<img width="940" height="439" alt="image" src="https://github.com/user-attachments/assets/6bd26365-51f9-49d8-80c7-61ca9358fc2f" />

3) Commission > 25% of salary

**Aim: To find employees with high commission.** \
Requirement: Salary and commission fields.\
Theory: Arithmetic comparison filters records.\
Query: SELECT ename, sal, comm
FROM employee
WHERE comm > 0.25 * sal;
<img width="940" height="244" alt="image" src="https://github.com/user-attachments/assets/1b8ccf33-0e32-4c95-980a-d6a2ff504ed3" />

4) Salary in dollar format

**Aim: To display salary in currency format.** \
Requirement: Salary column.\
Theory: FORMAT formats numbers.\
Query: SELECT ename, CONCAT('$', FORMAT(sal,2)) AS salary
FROM employee;
<img width="940" height="763" alt="image" src="https://github.com/user-attachments/assets/b4b79966-3076-4f23-86fc-1f7ba281aa2c" />


5) Matrix query (Job vs Dept salary)

**Aim: To display salary per job across departments.** \
Requirement: Employee table.\
Theory: Conditional aggregation using CASE.\
Query: SELECT job,
SUM(CASE WHEN deptno=10 THEN sal ELSE 0 END) AS dept10,
SUM(CASE WHEN deptno=20 THEN sal ELSE 0 END) AS dept20,
SUM(CASE WHEN deptno=30 THEN sal ELSE 0 END) AS dept30,
SUM(sal) AS total
FROM employee
GROUP BY job;
<img width="940" height="518" alt="image" src="https://github.com/user-attachments/assets/567b2e7c-6487-4267-970e-f3b98d70656e" />

6) Total employees and year-wise count

**Aim: To count employees by year of joining.** \
Requirement: Hiredate column.
Theory: CASE with aggregation.
Query: SELECT COUNT(*) AS total,
SUM(CASE WHEN YEAR(hiredate)=1980 THEN 1 ELSE 0 END) AS y1980,
SUM(CASE WHEN YEAR(hiredate)=1981 THEN 1 ELSE 0 END) AS y1981,
SUM(CASE WHEN YEAR(hiredate)=1982 THEN 1 ELSE 0 END) AS y1982,
SUM(CASE WHEN YEAR(hiredate)=1983 THEN 1 ELSE 0 END) AS y1983
FROM employee;
<img width="940" height="352" alt="image" src="https://github.com/user-attachments/assets/171bf1b4-a055-4ade-bf4c-47c57e57de19" />

7) Last Sunday of current month

**Aim: To find last Sunday.** \
Requirement: Date functions.\
Theory: LAST_DAY and weekday adjustment.\
Query: SELECT DATE_SUB(LAST_DAY(CURDATE()),
INTERVAL (DAYOFWEEK(LAST_DAY(CURDATE()))-1) DAY);
<img width="940" height="329" alt="image" src="https://github.com/user-attachments/assets/e209730a-b508-4ffb-b794-a1db5e7ce9b4" />

8) Department-wise employee count

**Aim: To count employees per department.** \
Requirement: Employee table.\
Theory: GROUP BY groups records.\
Query: SELECT deptno, COUNT(*) AS total_employees
FROM employee
GROUP BY deptno;
<img width="940" height="343" alt="image" src="https://github.com/user-attachments/assets/78f4abe0-7656-4a4a-a58f-94f43c03d021" />

9) Job-wise employee count

**Aim: To count employees per job.** \
Requirement: Employee table.\
Query:SELECT job, COUNT(*) AS total_employees
FROM employee
GROUP BY job;
<img width="940" height="395" alt="image" src="https://github.com/user-attachments/assets/9e848adc-e512-4b21-9c02-8889989fa8c7" />

10) Department-wise total salary

**Aim: To calculate salary per department.** \
Requirement: Employee table.\
Query: SELECT deptno, SUM(sal) AS total_salary
FROM employee
GROUP BY deptno;
<img width="940" height="356" alt="image" src="https://github.com/user-attachments/assets/813a90aa-c458-4f1b-a61a-9640fe654e67" />
1) Employees with their department name

**Aim: To display employee name with department name.** \
Requirement: Employee & Department tables.\
Theory: JOIN combines data from two tables.\
Query: SELECT e.ename, d.dname
FROM employee e
JOIN department d ON e.deptno = d.deptno;
<img width="713" height="608" alt="image" src="https://github.com/user-attachments/assets/da221686-c28e-4108-9535-40cb1380ea40" />

2) Employees whose manager is JONES

**Aim: To find employees managed by JONES.** \
Requirement: Self join on employee table.\
Theory: Self JOIN links table to itself.\
Query: SELECT e.ename, m.ename AS manager
FROM employee e
JOIN employee m ON e.mgr = m.empno
WHERE m.ename = 'JONES';
<img width="940" height="352" alt="image" src="https://github.com/user-attachments/assets/2ff4f57d-e9b0-47ef-8419-4f0e61d61dec" />

3) Employee, job, dept name, manager

**Aim: To display full employee details with manager.** \
Requirement: Employee + Department tables.\
Theory: Multiple joins combine related data.\
Query: SELECT e.ename, e.job, d.dname, m.ename AS manager
FROM employee e
LEFT JOIN employee m ON e.mgr = m.empno
JOIN department d ON e.deptno = d.deptno;
<img width="1007" height="609" alt="image" src="https://github.com/user-attachments/assets/d7219023-809a-4800-85f9-ed53ed542727" />

4) Employees except clerk sorted by salary

**Aim: To display non-clerk employees sorted by salary.** \
Requirement: Employee table.\
Theory: ORDER BY sorts results.\
Query: SELECT e.ename, e.job, e.sal, d.dname
FROM employee e
JOIN department d ON e.deptno = d.deptno
WHERE e.job <> 'CLERK'
ORDER BY e.sal DESC;
<img width="940" height="600" alt="image" src="https://github.com/user-attachments/assets/1726c004-46f3-4206-a782-669ea31b7060" />


5) Employee, job and manager (including no manager)

**Aim: To show employees with or without manager.** \
Requirement: Employee table.\
Theory: LEFT JOIN includes NULL values.\
Query: SELECT e.ename, e.job,
IFNULL(m.ename,'NO MANAGER') AS manager
FROM employee e
LEFT JOIN employee m ON e.mgr = m.empno;
<img width="940" height="608" alt="image" src="https://github.com/user-attachments/assets/7587d6e6-987a-49e8-8b04-5ad8f9b84436" />

6) Employees with annual salary 36000 or not clerk

**Aim: To filter employees based on salary or job.** \
Requirement: Employee + Department tables.\
Theory: Logical OR combines conditions.\
Query: SELECT e.ename, e.job, e.sal*12 AS annual_sal, d.dname
FROM employee e
JOIN department d ON e.deptno = d.deptno
WHERE (e.sal*12 = 36000 OR e.job <> 'CLERK');
<img width="642" height="592" alt="image" src="https://github.com/user-attachments/assets/8a5d2003-dd8c-41e8-a70c-e71d3affb35e" />

7) Employees earning 30000/year not clerk

**Aim: To find employees earning 30000 annually excluding clerks.** \
Requirement: Employee table.\
Query: SELECT e.ename, e.job, e.sal*12 AS annual_sal, d.dname
FROM employee e
JOIN department d ON e.deptno = d.deptno
WHERE e.sal*12 = 30000
AND e.job <> 'CLERK';
<img width="1534" height="241" alt="image" src="https://github.com/user-attachments/assets/0c933e88-c8fa-4008-83ab-76e90d9cb719" />

8) Employee with manager name & number

**Aim: To display employee and their manager details.** \
Requirement: Employee table.\
Theory: Self JOIN with NULL handling.\
Query: SELECT e.empno, e.ename,
IFNULL(m.ename,'NO MANAGER') AS manager_name,
IFNULL(m.empno,0) AS manager_no
FROM employee e
LEFT JOIN employee m ON e.mgr = m.empno;
<img width="642" height="592" alt="image" src="https://github.com/user-attachments/assets/c09ff21c-0044-4410-8b86-00cd06969669" />

9) Dept name, dept no, total salary

**Aim: To calculate total salary per department.** \
Requirement: Employee + Department tables.
Theory: GROUP BY groups records.
Query: SELECT d.deptno, d.dname, SUM(e.sal) AS total_salary
FROM employee e
JOIN department d ON e.deptno = d.deptno
GROUP BY d.deptno, d.dname;
<img width="940" height="315" alt="image" src="https://github.com/user-attachments/assets/67f1d93a-acbe-4a7b-a886-0dbf55998eca" />

10) Employee with department name

**Aim: To display employee details with department.** \
Requirement: Employee + Department tables.\
Query: SELECT e.empno, e.ename, d.dname
FROM employee e
JOIN department d ON e.deptno = d.deptno;
<img width="911" height="695" alt="image" src="https://github.com/user-attachments/assets/16c19c2f-10b6-46fb-b917-c3f724366077" />
11) Employee name with department name

**Aim: To display employee names with department names.** \
Requirement: Employee + Department tables.\
Query: SELECT e.ename, d.dname
FROM employee e
JOIN department d ON e.deptno = d.deptno;
<img width="940" height="825" alt="image" src="https://github.com/user-attachments/assets/f04b9f25-5126-48ae-a301-93e2cb5a9172" />
1) Employee with highest salary

**Aim: To find employee(s) earning highest salary.** \
Requirement: Employee table.\
Theory: Subquery returns max value.\
Query: SELECT ename
FROM employee
WHERE sal = (SELECT MAX(sal) FROM employee);
<img width="940" height="292" alt="image" src="https://github.com/user-attachments/assets/de6a3613-5e1a-4fe6-8a2d-ec133704d6c1" />
2) Highest paid clerk

**Aim: To find clerk earning highest salary.** \
Requirement: Job and salary columns.\
Query: SELECT empno, ename
FROM employee
WHERE job='CLERK'
AND sal = (SELECT MAX(sal) FROM employee WHERE job='CLERK');
<img width="940" height="268" alt="image" src="https://github.com/user-attachments/assets/af415077-02c7-4a37-b1ba-849f5dd19776" />
3) Salesman earning more than any clerk

**Aim: To find salesman earning more than highest clerk.** \
Requirement: Employee table.\
Query: SELECT ename
FROM employee
WHERE job='SALESMAN'
AND sal > (SELECT MAX(sal) FROM employee WHERE job='CLERK');
<img width="940" height="268" alt="image" src="https://github.com/user-attachments/assets/bd9bb890-471b-4d80-986a-b73589d542c3" />

4) Clerks salary between JAMES and SCOTT

**Aim: To find clerks earning between JAMES and SCOTT.** \
Requirement: Employee table.\
Query: SELECT ename
FROM employee
WHERE job='CLERK'
AND sal > (SELECT sal FROM employee WHERE ename='JAMES')
AND sal < (SELECT sal FROM employee WHERE ename='SCOTT');
<img width="940" height="327" alt="image" src="https://github.com/user-attachments/assets/54bd28df-7ad7-43bb-8282-409cc0a2f04f" />

5) Salary > JAMES or SCOTT

**Aim: To find employees earning more than JAMES or SCOTT.** \
Requirement: Employee table.\
Query: SELECT ename
FROM employee
WHERE sal > (SELECT sal FROM employee WHERE ename='JAMES')
OR sal > (SELECT sal FROM employee WHERE ename='SCOTT');
<img width="940" height="569" alt="image" src="https://github.com/user-attachments/assets/c26c8ee5-eb98-4805-849b-5cad95264b46" />

6) Highest salary in each department

**Aim: To find highest paid employee per department.** \
Requirement: Deptno and salary.\
Theory: Correlated subquery.\
Query: SELECT ename, deptno, sal
FROM employee e
WHERE sal = (
  SELECT MAX(sal)
  FROM employee
  WHERE deptno = e.deptno
);
<img width="1031" height="334" alt="image" src="https://github.com/user-attachments/assets/2531cc33-1601-4505-87c5-b33eaf49ccc1" />

7) Highest salary in each job group

**Aim: To find highest paid employee per job.** \
Requirement: Job column.\
Query: SELECT ename, job, sal
FROM employee e
WHERE sal = (
  SELECT MAX(sal)
  FROM employee
  WHERE job = e.job
);
<img width="940" height="371" alt="image" src="https://github.com/user-attachments/assets/f3657fbf-6ad6-4aba-9619-1862ab8b1550" />

8) Employees working in ACCOUNTING

**Aim: To find employees in ACCOUNTING department.** \
Requirement: Employee + Department tables.
Query: SELECT ename
FROM employee
WHERE deptno = (
  SELECT deptno FROM department WHERE dname='ACCOUNTING'
);
<img width="940" height="87" alt="image" src="https://github.com/user-attachments/assets/f3d64ad3-6356-4411-95c4-059a9a1bf25a" />

9) Employees working in SALES

**Aim: To find employees working in SALES department.** \
Requirement: Department table (no LOC used).\
Query: SELECT ename
FROM employee
WHERE deptno = (
  SELECT deptno FROM department WHERE dname='SALES'
);
<img width="1143" height="256" alt="image" src="https://github.com/user-attachments/assets/d2865cb8-64a5-4f9a-83c5-a25ceed20151" />
10) Job groups with total salary > managers

**Aim: To find jobs whose total salary exceeds manager salary.** \
Requirement: Employee table.\
Theory: GROUP BY + HAVING with subquery.\
Query: SELECT job
FROM employee
GROUP BY job
HAVING SUM(sal) > (
  SELECT MAX(sal)
  FROM employee
  WHERE job='MANAGER'
);
<img width="940" height="314" alt="image" src="https://github.com/user-attachments/assets/7a4860a2-d62a-4d48-9dbc-d3cfa89aad39" />
1) Dept 10 salary > ANY other dept

**Aim: To find employees in dept 10 earning more than any employee in other departments.** \
Requirement: Employee table.\
Theory: ANY compares with at least one value.\
Query: SELECT ename
FROM employee
WHERE deptno = 10
AND sal > ANY (SELECT sal FROM employee WHERE deptno <> 10);
<img width="940" height="263" alt="image" src="https://github.com/user-attachments/assets/fb25f7fe-233a-4586-bb69-1e03dc418d76" />

2) Dept 10 salary > ALL other dept

**Aim: To find employees in dept 10 earning more than all employees in other departments.** \
Requirement: Employee table.\
Theory: ALL compares with all values.\
Query: SELECT ename
FROM employee
WHERE deptno = 10
AND sal > ALL (SELECT sal FROM employee WHERE deptno <> 10);
<img width="940" height="135" alt="image" src="https://github.com/user-attachments/assets/69737d11-f0d4-4ed9-abdc-e5682d43c7cd" />
3) Employees in SALES dept with salary range

**Aim: To display employees in SALES department with salary range (grade-like condition).** \
Requirement: Employee + Department tables.\
Theory: Subquery fetches deptno.\
Query: SELECT *
FROM employee
WHERE deptno = (
  SELECT deptno FROM department WHERE dname='SALES'
)
AND sal BETWEEN 1400 AND 2000;
<img width="940" height="273" alt="image" src="https://github.com/user-attachments/assets/ef9522c6-4b82-4221-94eb-1e76ab838c6f" />

4) Employees who are managers

**Aim: To display employees who act as managers.** \
Requirement: Employee table with mgr column.\
Theory: Subquery finds manager IDs.\
Query: SELECT *
FROM employee
WHERE empno IN (
  SELECT DISTINCT mgr FROM employee WHERE mgr IS NOT NULL
);
<img width="940" height="398" alt="image" src="https://github.com/user-attachments/assets/6d9f4775-5711-4d74-878b-dffe71e7bef9" />

5) Employees whose manager is JONES

**Aim: To find employees managed by JONES.** \
Requirement: Employee table.\
Query: SELECT ename
FROM employee
WHERE mgr = (
  SELECT empno FROM employee WHERE ename='JONES'
);
<img width="940" height="395" alt="image" src="https://github.com/user-attachments/assets/4ea8d3ae-ca92-46f9-aee1-a3f47ca3c6e4" />

6) Employees working in SALES department

**Aim: To display employees working in SALES.** \
Requirement: Employee + Department tables.\
Query: SELECT ename
FROM employee
WHERE deptno = (
  SELECT deptno FROM department WHERE dname='SALES'
);
<img width="940" height="494" alt="image" src="https://github.com/user-attachments/assets/767089f7-51df-4d28-98ad-05a4534ebf92" />

7) Salary between 2000–5000 in SALES dept

**Aim: To display employees in salary range and department.** \
Requirement: Employee + Department tables.\
Theory: Subquery + BETWEEN condition.\
Query: SELECT ename, sal, comm
FROM employee
WHERE sal BETWEEN 2000 AND 5000
AND deptno = (
  SELECT deptno FROM department WHERE dname='SALES'
);
<img width="940" height="494" alt="image" src="https://github.com/user-attachments/assets/fc2f8a13-2881-4f15-94b9-610a4687fbd2" />
8) Employees earning more than their manager

**Aim: To find employees earning more than their manager.** \
Requirement: Employee table (self relation).\
Theory: Self join with comparison.\
Query: SELECT e.ename
FROM employee e
JOIN employee m ON e.mgr = m.empno
WHERE e.sal > m.sal;
<img width="651" height="369" alt="image" src="https://github.com/user-attachments/assets/bb0e7ef4-72c1-493a-8dad-553a69a8964b" />

9) Employees working in same dept as manager

**Aim: To find employees working in same department as their manager.** \
Requirement: Employee table.\
Theory: Self join comparison.\
Query: SELECT e.ename
FROM employee e
JOIN employee m ON e.mgr = m.empno
WHERE e.deptno = m.deptno;
<img width="793" height="714" alt="image" src="https://github.com/user-attachments/assets/51a8caad-3cfd-482a-aeae-3bba07daf0d0" />
1) Delete employees before 31-Dec-82

**Aim: To delete employees based on hire date condition.** \
Requirement: Employee table with hiredate.\
Theory: DELETE removes records using conditions.\
Query: DELETE FROM employee
WHERE hiredate < '1982-12-31';
<img width="940" height="140" alt="image" src="https://github.com/user-attachments/assets/44c59e21-2743-4685-949e-1cefa2bd6f46" />

2) Managers with department name

**Aim: To display managers along with department name.** \
Requirement: Employee + Department tables.\
Theory: JOIN combines tables.\
Query: SELECT e.ename, e.job, d.dname
FROM employee e
JOIN department d ON e.deptno = d.deptno
WHERE e.job = 'MANAGER';
<img width="940" height="179" alt="image" src="https://github.com/user-attachments/assets/0cc53198-66c7-4f3f-9085-f35ce4cc76b8" />

3) Ford salary equals highest salary

**Aim: To check if Ford has highest salary.** \
Requirement: Employee table.\
Theory: Subquery returns max value.\
Query: SELECT ename, sal
FROM employee
WHERE ename = 'FORD'
AND sal = (SELECT MAX(sal) FROM employee);
<img width="723" height="340" alt="image" src="https://github.com/user-attachments/assets/e6d83cca-2991-427b-8ef1-2cf238a098be" />

4) Top 5 earners

**Aim: To display top 5 highest paid employees.** \
Requirement: Employee table with salary.\
Theory: ORDER BY + LIMIT filters top records.\
Query: SELECT ename, sal
FROM employee
ORDER BY sal DESC
LIMIT 5;
<img width="813" height="291" alt="image" src="https://github.com/user-attachments/assets/64c13810-d5be-44bd-9622-04bca0265825" />

5) Employees with highest salary

**Aim: To display employees earning highest salary.** \
Requirement: Employee table.\
Query: SELECT ename
FROM employee
WHERE sal = (SELECT MAX(sal) FROM employee);
6) Salary equal to avg of max and min

**Aim: To find employees whose salary equals average of highest and lowest salary.** \
Requirement: Salary column.\
Theory: Aggregate functions with arithmetic.\
Query: SELECT ename, sal
FROM employee
WHERE sal = (
  (SELECT MAX(sal) FROM employee) +
  (SELECT MIN(sal) FROM employee)
)/2;
<img width="767" height="367" alt="image" src="https://github.com/user-attachments/assets/baf12060-fa49-4c09-bd5a-5d4d51577a45" />

7) Departments having at least 3 employees

**Aim: To display departments with minimum 3 employees.** \
Requirement: Employee + Department tables.\
Theory: GROUP BY + HAVING filters grouped data.\
Query: SELECT d.dname
FROM department d
JOIN employee e ON d.deptno = e.deptno
GROUP BY d.dname
HAVING COUNT(*) >= 3;
<img width="792" height="438" alt="image" src="https://github.com/user-attachments/assets/4d6b98d9-d038-40c9-832f-950d255246f0" />

8) Managers earning more than average salary

**Aim: To find managers earning above average salary.** \
Requirement: Employee table.\
Query: SELECT ename
FROM employee
WHERE job = 'MANAGER'
AND sal > (SELECT AVG(sal) FROM employee);
<img width="940" height="208" alt="image" src="https://github.com/user-attachments/assets/3ce1c527-1de9-441d-9ffd-9f0f91393c5e" />

9) Managers earning more than avg of their employees

**Aim: To find managers earning more than their subordinates' average salary.** \
Requirement: Employee table.\
Theory: Correlated subquery.\
Query: SELECT m.ename
FROM employee m
WHERE m.empno IN (
  SELECT DISTINCT mgr FROM employee WHERE mgr IS NOT NULL
)
AND m.sal > (
  SELECT AVG(e.sal)
  FROM employee e
  WHERE e.mgr = m.empno
);
<img width="940" height="330" alt="image" src="https://github.com/user-attachments/assets/9e355ffb-cdda-4cc5-85c7-3aa143ef51cd" />

10) Net pay ≥ highest salary

**Aim: To find employees whose total pay exceeds highest salary.** \
Requirement: Salary and commission columns.\
Theory: IFNULL handles NULL commission.\
Query: SELECT ename, sal, comm,
(sal + IFNULL(comm,0)) AS net_pay
FROM employee
WHERE (sal + IFNULL(comm,0)) >= (
  SELECT MAX(sal) FROM employee
);
<img width="753" height="384" alt="image" src="https://github.com/user-attachments/assets/1ee000f5-9ad6-4282-8471-7a8f712b83e1" />
