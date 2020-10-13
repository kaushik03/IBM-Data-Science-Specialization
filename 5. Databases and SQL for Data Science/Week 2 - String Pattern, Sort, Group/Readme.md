# Assignments: 

## For Loading Data
- [x] Script is available
- [x] Data is loaded in `Data` Folder

## 1. String Patterns, Sorting & Grouping

> HR Database
------------------------

1. We will be working on a sample HR database. 
    1. This HR database schema consists of 5 tables called EMPLOYEES, JOB_HISTORY, JOBS,
    DEPARTMENTS and LOCATIONS. 
    2. Each table has a few rows of sample data
    
2.  There are three parts to this lab:
    -  Creating tables
    - Loading data into tables
    - Composing and running queries
### Sample for Tables imported into the DB2 instance.

<img src= "/assets/Sample Datasets.JPG" raw = true
alt = "Sample"/>

### COMPOSING AND RUNNING QUERIES

1.  Retrieve all employees whose address is in Elgin,IL 

    ```
    SELECT F_name FROM employees WHERE address like '%Elgin,IL%'

    ```
2. Retrieve all employees who were born during the 1970's.
    
    ```
    SELECT f_name, l_name FROM employees WHERE b_date like '197%'

    ```
3.  Retrieve all employees in department 5 whose salary is between 60000 and 70000 .

    ```
    SELECT f_name, l_name FROM employees WHERE (salary between 60000 and 70000 AND dep_id) = 5
    ```
4.  Retrieve a list of employees ordered by department ID

    ```
    SELECT * from employees ORDERBY dep_id

    ```
5.  Retrieve a list of employees ordered in descending order by department ID and within each department ordered alphabetically in descending order by last name.
    
    ```
    select F_NAME, L_NAME, DEP_ID 
    from EMPLOYEES
    order by DEP_ID desc, L_NAME desc;

    ```
6. For each department ID retrieve the number of employees in the department.

    ```
    SELECT dep_id, count(*) from employees 
    group by dep_id;

    ```
7. For each department retrieve the number of employees in the department, and the average employees salary in the department.
    ```
    SELECT dep_id, count(*) AS "Total_employees",
    avg(Salary) AS "average_pay" FROM employees
    group by dep_id;
    ```
8. order the above result set by Average Salary.

    ```
    SELECT dep_id, count(*) AS "Total_employees",
    avg(Salary) AS "average_pay" FROM employees
    group by dep_id
    order by avg(salary);
    ```
9.  limit the result to departments with fewer than 4 employees
    ```
    select DEP_ID, COUNT(*) AS "NUM_EMPLOYEES", AVG(SALARY) AS "AVG_SALARY"
    from EMPLOYEES
    group by DEP_ID
    having count(*) < 4
    order by AVG_SALARY;
    ```

---------------------------------

## 2. Built-In functions

- Aggregagte Functions
    - SUM()
    - MIN()
    - MAX()
    - AVG()
- Date & Time Functions
- Static and String Functions
    - ROUND()
    - UCASE()
    - LCASE()
    - LENGTH()
    - DISTINCT()

## 3. Sub-queries and Nested Functions.
 ` Aggregate Functions can't be used in a where clause`

