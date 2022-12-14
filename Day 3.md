# Day 3 of #30daysOfSql
## Cities With Completed Trades | ([Question Link](https://datalemur.com/questions/completed-trades))

### :pushpin: You are given the tables below containing information on Robinhood trades and users. Write a query to list the top three cities that have the most completed trade orders in descending order.

### Output the city and number of orders.

## Solution:

```
select distinct city,count( order_id)as num_of_orders
from users u 
join trades t
on u.user_id = t.user_id
where status = 'Completed'
group by city
order by num_of_orders desc, city desc


```
