> Prof. Alexandre Calaça

### Consider the tables used at [Consid](https://www.programiz.com/sql/online-compiler/)


1-Basic Join Query with Customer Orders and Shipping Status  
- Description: Write a query that retrieves each customer's first name, last name, ordered item, order amount, and shipping status by joining the Customers, Orders, and Shippings tables.  
- Expected Columns: first_name, last_name, item, amount, status.

```
SELECT first_name, last_name, item, amount, status FROM Customers
JOIN Orders ON Customers.customer_id = Orders.customer_id
JOIN Shippings ON Customers.customer_id = Shippings.customer
```

---

2-Renaming Columns and Joining Three Tables  
- Description: Write a query that retrieves each customer's name, country, the product they ordered, the quantity of the product, and the shipping status.   Use column aliases to rename the fields in the final output.  
- Expected Columns: "Name", country, "Product", "Quantity", status.

```
SELECT first_name as "Name", country, item as "Product", amount as "Quantity", status FROM Customers
JOIN Orders ON Customers.customer_id = Orders.customer_id
JOIN Shippings ON Customers.customer_id = Shippings.customer
```

---

3-Filtering Results with a WHERE Clause  
- Description: Write a query that retrieves each customer's first name, last name, age, the item they ordered, the amount, and shipping status. Only include customers who have ordered items costing more than 350.  
- Expected Columns: "First name", "last Name", age, item, amount, status.
  
```
SELECT first_name as "First name", last_name as 'last Name', age, item, amount, status FROM Customers
JOIN Orders ON Customers.customer_id = Orders.customer_id
JOIN Shippings ON Customers.customer_id = Shippings.customer
WHERE amount > 350
```
---

4-Ordering Results After Filtering  
- Description: Write a query that retrieves customer details (first name, last name, age), their ordered items, the amount spent, and the shipping status. Filter the results to only include orders with an amount greater than or equal to 350, and sort the results by the customer’s first name.  
- Expected Columns: first_name, last_name, age, item, amount, status.

```
SELECT Customers.first_name, Customers.last_name, Customers.age, Orders.item, Orders.amount, Shippings.status FROM Customers
JOIN Orders ON Customers.customer_id = Orders.customer_id
JOIN Shippings ON Customers.customer_id = Shippings.customer
WHERE amount >= 350 ORDER BY first_name
```

---

5-Group By with Aggregated Amounts  
- Description: Write a query that groups customers based on their customer ID and sums the total amount they have spent across all orders. Return the first name, last name, total amount spent, and shipping status for each customer.  
- Expected Columns: first_name, last_name, "Total amount", status.
```
SELECT first_name, last_name, SUM(amount) as "Total amount", status
FROM Customers 
JOIN Orders ON Customers.customer_id = Orders.customer_id
JOIN Shippings ON Customers.customer_id = Shippings.customer
GROUP BY Customers.customer_id
```

---

6-Calculate Average Amount Spent per Customer by Country
- Description: Write a query that calculates the average amount spent on orders for each customer, grouped by both the customer’s country and first name. Also return the shipping status for each customer.
- Expected Columns: first_name, country, AVG(Orders.amount), status.

```
SELECT first_name, country, AVG(Orders.amount), Shippings.status
FROM Customers
JOIN Orders ON Customers.customer_id = Orders.customer_id
JOIN Shippings ON Customers.customer_id = Shippings.customer
GROUP BY country, first_name
```

---

7-Filtering Groups with HAVING and Ordering Results
- Description: Write a query that groups customers by their ID and shipping status. For each customer, calculate the total amount spent and return only customers who have spent more than 500. Sort the results by the customer’s first name.
- Expected Columns: "First name", "last name", "Amount", status.

```
SELECT c.first_name as "First name", last_name as "last name", SUM(o.amount) as "Amount", s.status FROM Customers c 
JOIN Orders o ON c.customer_id = o.customer_id
JOIN Shippings s ON c.customer_id = s.customer
GROUP BY c.customer_id, s.status
HAVING SUM(o.amount) > 500
ORDER BY c.first_name
```

---

8-Using HAVING to Filter Specific Items
- Description: Write a query that groups customers by their customer ID and the item they ordered. Return customers who have ordered a "Keyboard" and have spent more than 299 on it. The result should include customer details, the item ordered, and the total amount spent on that item.
- Expected Columns: customer_id, first_name, last_name, item, SUM(o.amount).

```
SELECT c.customer_id, c.first_name, c.last_name, o.item, SUM(o.amount)
FROM Customers c
JOIN Orders o ON c.customer_id = o.customer_id
JOIN Shippings s ON c.customer_id = s.customer
GROUP BY c.customer_id, o.item
HAVING SUM(o.amount) > 299 AND item = "Keyboard"
```

---

9-Counting Distinct Items and Filtering with HAVING
- Description: Write a query that counts how many distinct items each customer has ordered and sums the total amount they have spent. Only include customers whose orders have been delivered, who have spent more than 500, and who have ordered at least one distinct item.
- Expected Columns: customer_id, "Number of items", "Total amount", status.

```
SELECT c.customer_id, COUNT(DISTINCT o.item) as "Number of items", SUM(o.amount) as "Total amount", status FROM Customers c
JOIN Orders o ON c.customer_id = o.customer_id
JOIN Shippings s ON c.customer_id = s.customer
WHERE status = "Delivered"
GROUP BY c.customer_id
HAVING SUM(o.amount) > 500 AND COUNT(DISTINCT o.item) >= 1
```

