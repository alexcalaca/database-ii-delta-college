> Prof. Alexandre Calaça
> 10th class of Database II - Delta College

Considering the following tables here https://www.programiz.com/sql/online-compiler/

---

## Exercises
1. Problem: Calculate the average age of customers for each country.
```
SELECT country, AVG(age) AS 'Average'
FROM Customers GROUP BY country;
```
---

2. Problem: Find countries where the average age of customers is greater than 25.

```
SELECT country, AVG(age) AS 'Average'
FROM Customers GROUP BY country
HAVING AVG(age) > 25
```
---

3. Problem: Find countries where the maximum age of customers is less than 25.
```
Select country, MAX(age) as "Maximum"
from Customers group by country
having MAX(age) < 25
```
---

4. Problem: List countries where the oldest customer is younger than 25.
```
SELECT country as 'Country', MAX(age) as 'Maximum'
FROM Customers
GROUP BY country
HAVING MAX(AGE) < 25
```
---

5. Problem: Find the ages where more than two customers share the same age.
```
SELECT age as 'Age', COUNT(customer_id) as 'Quantity'
FROM Customers GROUP BY age
HAVING COUNT(customer_id) > 2
```
---

6. Problem: Find customers who have placed fewer than 3 orders and whose total order amount is less than 400.
```
SELECT customer_id as 'Customer', COUNT(order_id) as 'Number of orders', SUM(amount) as 'Total amount' FROM Orders
GROUP BY customer_id
HAVING COUNT(order_id) < 3 AND sum(amount) < 400
```
---

7. Problem: Find customers who have placed more than one order and whose average order amount is greater than 500.
```
--We want to find customers who have placed more than one order and where the average amount of their orders is greater than 500.

SELECT customer_id, COUNT(order_id) as 'Number of orders', AVG(amount) as 'Average amount' FROM Orders
GROUP BY customer_id
HAVING COUNT(order_id) > 1 AND AVG(amount) > 500
```
---


8. Problem: Find customers who ordered at least 2 different items and whose total order amount is greater than 300.
```
SELECT customer_id as 'Customer', COUNT(DISTINCT item) as 'Item', SUM(amount) as 'Total amount' FROM Orders
GROUP BY customer_id
HAVING COUNT(DISTINCT item) >= 2 AND SUM(amount) > 300
```
---

9. Problem: Find customers whose total order amount falls between 450 and 13000.
```
SELECT Customers.customer_id, first_name, last_name, SUM(amount) as 'Total amount' FROM Customers
JOIN Orders ON Orders.customer_id = Customers.customer_id
GROUP BY Customers.customer_id
HAVING SUM(amount) BETWEEN 450 AND 13000
```
---

10. Problem: Find customers who have placed more than one order and spent more than 300 in total.
```
SELECT c.customer_id, c.first_name, c.last_name, COUNT(o.order_id) AS order_count, SUM(o.amount) AS total_amount
FROM Customers c
JOIN Orders o ON c.customer_id = o.customer_id
GROUP BY c.customer_id, c.first_name, c.last_name
HAVING COUNT(o.order_id) > 1 AND SUM(o.amount) > 300;
```

