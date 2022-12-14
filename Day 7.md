# Day 7 of #30DaysOfSql

## Pharmacy Analytics(Part 1) | ([Question Link](https://platform.stratascratch.com/coding/10308-salaries-differences?tabname=question&code_type=3)) | StrataScratch

## 📌 Write a query that calculates the difference between the highest salaries found in the marketing and engineering departments. Output just the absolute difference in salaries.

### Tables: 
### db_employee - id, first_name, last_name, salary, department_id,
### db_dep - id, department


## Solution:
```
with marketing_sal as
     (
     select dept.department, max(emp.salary) as max_marketing_sal
     from db_employee emp 
     join db_dept dept
     on emp.department_id = dept.id 
     where dept.department= 'marketing'
     group by dept.department),
     
     engineering_sal as
    (
     select dept.department, max(emp.salary) as max_eng_sal
     from db_employee emp 
     join db_dept dept
     on emp.department_id = dept.id 
     where dept.department= 'engineering'
     group by dept.department
    
    )

select max_marketing_sal - max_eng_sal   from marketing_sal,engineering_sal
```

