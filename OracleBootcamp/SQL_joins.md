-- 1. Retrieve employee names and their department names using INNER JOIN
SELECT  e.first_name, d.department_name
FROM hr.employees e
INNER JOIN hr.departments d ON e.department_id= d.department_id;

-- 2. Retrieve all employees and their respective department names (including those without a department) using LEFT JOIN
select e.FIRST_NAME ,nvl(d.department_name,'not assigned') as DEPARTMENT_NAME
FROM hr.employees e
LEFT JOIN hr.departments d ON e.department_id= d.department_id;

-- 3. Retrieve all departments and employees (including departments without employees) using RIGHT JOIN
select e.EMPLOYEE_ID,e.FIRST_NAME ,d.department_name 
FROM hr.employees e
RIGHT JOIN hr.departments d ON e.department_id= d.department_id;

-- 4. Retrieve all employees and their department names using FULL OUTER JOIN
select e.EMPLOYEE_ID,e.FIRST_NAME,d.department_name
from hr.employees e
full outer join hr.DEPARTMENTS d ON e.department_id= d.department_id;

-- 5. Retrieve employees who do not belong to any department using LEFT JOIN with NULL check
select e.EMPLOYEE_ID,e.FIRST_NAME ,d.department_name
FROM hr.employees e
LEFT JOIN hr.departments d ON e.department_id= d.department_id
where d.department_id is null;

-- 6. Retrieve departments that have no employees using RIGHT JOIN with NULL check
select e.EMPLOYEE_ID,e.FIRST_NAME ,d.department_name
FROM hr.employees e
RIGHT JOIN hr.departments d ON e.department_id= d.department_id
where e.department_id is null;


-- 7. Retrieve employees along with their manager names using SELF JOIN
select e.EMPLOYEE_ID,e.FIRST_NAME , e.MANAGER_ID
FROM hr.employees e
SELF JOIN hr.employee m ON e.MANAGER_ID=m.EMPLOYEE_ID;

-- 8. Retrieve employees along with their job title using INNER JOIN
SELECT e.EMPLOYEE_ID, e.FIRST_NAME, j.job_title
from hr.employees e INNER join hr.jobs j on e.JOB_ID = j.job_id;

-- 9. Retrieve employees along with the location of their department using INNER JOIN
SELECT  E.EMPLOYEE_ID, E.FIRST_NAME, D.DEPARTMENT_ID, L.STREET_ADDRESS
FROM  hr.employees E 
INNER JOIN hr.departments D ON E.DEPARTMENT_ID = D.DEPARTMENT_ID  
INNER JOIN hr.locations L ON D.LOCATION_ID = L.LOCATION_ID;

-- 10. Retrieve employees and the projects they are assigned to using INNER JOIN
SELECT e.employee_id, e.employee_name, p.project_name
FROM employees e
INNER JOIN projects p ON e.employee_id = p.employee_id;

-- 11. Retrieve employees who have not been assigned to any project using LEFT JOIN
select e.EMPLOYEE_ID,p.project_name
FROM employees e
LEFT JOIN projects p ON e.employee_id = p.employee_id;
WHERE PROJECT_ID IS NULL;

-- 12. Retrieve project names along with the department handling them using INNER JOIN



0
select * from hr.employees;
select * from hr.DEPARTMENTS;

SELECT
    DEPARTMENT_ID,
    DEPARTMENT_NAME,
    MANAGER_ID,
    LOCATION_ID
FROM
    HR.DEPARTMENTS;

SELECT
    EMPLOYEE_ID,
    FIRST_NAME,
    LAST_NAME,
    EMAIL,
    PHONE_NUMBER,
    HIRE_DATE,
    JOB_ID,
    SALARY,
    COMMISSION_PCT,
    MANAGER_ID,
    DEPARTMENT_ID
FROM
    HR.EMPLOYEES;
