# Day 4 of #30daysOfSql
## Duplicate Job Listings | ([Question Link](https://datalemur.com/questions/duplicate-job-listings))

### :pushpin: Assume you are given the table below that shows job postings for all companies on the LinkedIn platform. Write a query to get the number of companies that have posted duplicate job listings.

### Clarification: Duplicate job listings refer to two jobs at the same company with the same title and description.

## Solution:

```
with cte_table as(
      
      SELECT company_id,title, description, count(job_id) as job_count 
      FROM job_listings
      group by company_id, title, description)
      
select count(distinct company_id) as duplicate_companies
from cte_table
where job_count > 1;


```
