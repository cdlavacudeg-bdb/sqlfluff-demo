select  E.EMPLOYEE_ID,  E.FIRST_NAME ,E.LAST_NAME,
E.SALARY,E.DEPARTMENT_ID ,D.DEPARTMENT_NAME,
case when e.salary>10000 then 'HIGH'
else 'LOW'end salary_level,
NVL(e.COMMISSION_PCT,0) COMM ,
sysdate AS RUNDATE
from HR.EMPLOYEES   E
LEFT  join  HR.DEPARTMENTS  d
on   E.DEPARTMENT_ID=d.DEPARTMENT_ID
where  1=1
and E.DEPARTMENT_ID in( 10,20 ,30,40)
AND salary>5000
and (E.JOB_ID='IT_PROG'
or JOB_ID='SA_MAN')
and E.HIRE_DATE<to_date('2018-01-01','YYYY-MM-DD')
order    by   DEPARTMENT_ID ,SALARY desc;




-- segundo query deliberadamente mal escrito
SELECT *
FROM HR.EMPLOYEES emp , HR.JOBS j
WHERE emp.JOB_ID=j.JOB_ID
AND emp.manager_id=j.job_id
AND emp.salary> (select avg(salary) from HR.EMPLOYEES)
ORDER by emp.FIRST_NAME , emp.last_name;



with dept_sal as(
select department_id,
sum(salary) total_sal,avg(salary) avg_sal
from hr.employees
group by department_id
)
select *
from dept_sal ds
where avg_sal> ( select avg(salary) from HR.EMPLOYEES )
order by  1;




SELECT emp.employee_id,emp.first_name, emp.last_name ,
( SELECT count(*) FROM HR.EMPLOYEES e2 WHERE e2.manager_id=emp.employee_id )as TEAMSIZE
FROM hr.employees emp
where emp.employee_id in
(select employee_id from hr.employees where salary>9000)
and emp.department_id not in(
select department_id from hr.departments
where location_id=1700)
;



select
department_id,
sum(case when SALARY>10000 then 1 else 0 end)high_paid,
sum(case when salary<=10000 then 1 else 0 end ) low_paid
from HR.EMPLOYEES
group by department_id
having sum(salary)>50000
order by department_id;

