# Day 5 of #30daysOfSql
## Average Review Ratings | ([Question Link](https://datalemur.com/questions/sql-avg-review-ratings))

### :pushpin:  The output should include the month in numerical value, product id, and average star rating rounded to two decimal places. Sort the output based on month followed by the product id.

## Solution:

```
SELECT EXTRACT(month from submit_date) as mnth,
       product_id as product,
       ROUND(AVG(stars),2) as avg_stars 
FROM reviews 
group by product_id, EXTRACT(month from submit_date)
ORDER BY EXTRACT(month from submit_date), product_id


```
