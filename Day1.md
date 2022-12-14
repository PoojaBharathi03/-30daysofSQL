# Day1ofSQL

## Data Science Skills [Question Link](https://datalemur.com/questions/matching-skills) - The question is taken from Datalemur platform by Nick Singh.

#### Given a table of candidates and their skills, you're tasked with finding the candidates best suited for an open Data Science job. You want to find candidates who are proficient in Python, Tableau, and PostgreSQL.

#### Write a query to list the candidates who possess all of the required skills for the job. Sort the the output by candidate ID in ascending order.

#### candidates Table:

|  Column Name  |  Type         |
| ------------- | ------------- |
|  candidate_id	|   integer     |
| skill	        |    varcharl   |

### Solution:
```
SELECT candidate_id 
FROM candidates
WHERE skill IN ('Python','Tableau' ,'PostgreSQL') 
GROUP BY candidate_id
HAVING count(skill) = 3
Order BY candidate_id;
```
