# Day 2 of SQL

## Page With No Likes from Datalemur platform by nick singh([Question Link](https://datalemur.com/questions/sql-page-with-no-likes))


:pushpin: Facebook
Assume you are given the tables below about Facebook pages and page likes. Write a query to return the page IDs of all the Facebook pages that don't have any likes. The output should be in ascending order.

### Table1 pages:

| Column_Name | Type |
| --- | --- |
| page_id | integers |
| page_name | varchar |

### Table2 --> page_likes

| Column_Name | Type |
| --- | --- |
| user_id | integers |
| page_id | integer |
| liked_date | datetime |


## Solution:
```
SELECT pages.page_id 
FROM pages 
LEFT JOIN page_likes pg
ON pages.page_id = pg.page_id
WHERE liked_date is NULL
ORDER BY pages.page_id;


```
