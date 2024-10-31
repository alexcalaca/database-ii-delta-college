> Prof. Alexandre Calaça

Consider the tables of this link: https://www.programiz.com/sql/online-compiler/

---

1-Description: Retrieve all customer records where the first name begins with the letter "J."
```
SELECT * FROM Customers WHERE first_name LIKE "J%";
```
---

2-Description: Retrieve all customer records where the last name ends with the letter "n."
```
SELECT * FROM Customers WHERE last_name LIKE '%n'
```

---

3-Description: Find countries where the average age of customers is greater than 25, specifically for customers whose first name begins with "J." Display customer IDs, country, first name, and the calculated average age.

```
SELECT customer_id as 'Customer id', country, first_name as 'First name', AVG(age) as 'Average'
FROM Customers GROUP BY country
HAVING AVG(age) > 25 AND first_name LIKE 'J%'
```

---

4-Retrieve customers who have placed more than one order, have an average order amount greater than 500, and whose last name ends with "a." Display customer ID, last name, average order amount, and order count.
```
SELECT c.customer_id, c.last_name, AVG(o.amount), COUNT(o.order_id) FROM Customers c
JOIN Orders o ON c.customer_id = o.customer_id
GROUP BY c.customer_ida
HAVING COUNT(o.order_id) >= 0 AND AVG(o.amount) > 0 AND c.last_name LIKE '%a'
```
---

5-Insert a new customer record with specified details (customer ID, first name, last name, age, and country).
```
INSERT INTO Customers (customer_id, first_name, last_name, age, country) VALUES (7, 'Heitor', 'Henrique', 22, 'USA')
```
---

6-Retrieve customers with an average order amount exceeding 500 and a last name ending in "A." Display customer ID, last name, total number of orders, and average order amount.
```
SELECT c.customer_id, c.last_name as 'Last name', COUNT(o.order_id) as 'Number of orders', AVG(o.amount) as 'Amount average' FROM Customers c JOIN Orders o ON
c.customer_id = o.customer_id
GROUP BY c.customer_id
HAVING AVG(o.amount) > 500 AND c.last_name LIKE '%A'
```

---

7-Find customers whose total order amount falls between 450 and 10,000 and whose first name includes "an." Display customer ID, first name, and total order amount.
```
SELECT c.customer_id as 'Customer id', c.first_name as 'First name', SUM(o.amount) as 'Total order amount' FROM Customers c JOIN Orders o
ON c.customer_id = o.customer_id
GROUP BY c.customer_id
HAVING SUM(o.amount) BETWEEN 450 AND 10000 AND c.first_name LIKE '%an%'
```

---

8-Retrieve all customer records where the first name is exactly five characters long.
```
SELECT * FROM Customers WHERE first_name LIKE '_____'
```

---

9- Retrieve all customer records where the third letter of the first name is "h."
```
SELECT * FROM Customers WHERE first_name LIKE '__h%'
```

---

10-Retrieve each customer's details (ID, name, country, item ordered, order amount, and shipping status) for customers with an "o" as the second letter of their first name.
```
SELECT c.customer_id, c.first_name, c.last_name, c.country, o.item, o.amount, s.status FROM
Customers C JOIN Orders o ON c.customer_id = o.customer_id
JOIN Shippings s ON c.customer_id = s.customer
WHERE c.first_name LIKE '_o%'
```

---

11-Summarize total spending and shipping status for each customer whose first name starts with "J." Display customer ID, full name, total amount spent, and shipping status.
```
SELECT Customers.customer_id as 'Customer id', Customers.first_name as 'First name', Customers.last_name as 'Last name', SUM(Orders.amount) as 'Total amount', Shippings.status as 'Shipping status' FROM Customers 
JOIN Orders ON Customers.customer_id = Orders.customer_id
JOIN Shippings ON Customers.customer_id = Shippings.customer
GROUP BY Customers.customer_id HAVING Customers.first_name LIKE 'J%'
```

---

12-Calculate the average order amount per customer grouped by country and first name for customers with "n" as the fourth letter of their first name. Display country, full name, customer ID, average amount, and shipping status.
```
SELECT c.country as 'Country', c.first_name as 'First name', c.customer_id as 'Customer id', c.last_name as 'Last name', AVG(o.amount) as 'Total amount', s.status FROM Customers c
JOIN Orders o ON c.customer_id = o.customer_id 
JOIN Shippings s ON c.customer_id = s.customer
GROUP BY c.country, c.first_name
HAVING c.first_name LIKE '___n'
```
