> Lesson notes - August 28th, 2024 Topic: Aggregate functions and SQL operators  
> Topics: Review of `Operators` and `Aggregate functions`  
Other activities: Coding challenges with [Leetcode](https://leetcode.com/studyplan/top-sql-50/)  

---
### Commands

Retrieves all columns and records from the Customers table.
```
SELECT * FROM Customers;
```

Retrieves only the first_name and last_name columns for all records in the Customers table.
```
SELECT first_name, last_name FROM Customers;
```

Calculates the average age of all customers and labels the result as "Média idade."
```
SELECT AVG(age) AS "Média idade" FROM Customers;
```

Counts the total number of records in the Customers table and labels the result as "Quantidade de registros."
```
SELECT COUNT(*) AS "Quantidade de registros" FROM Customers;
```

Finds the minimum age among all customers and labels the result as "Idade mínima."
```
SELECT MIN(age) AS "Idade mínima" FROM Customers;
```

Retrieves all columns for records where the customer's age is less than 25.
```
SELECT * FROM Customers WHERE age < 25;
```

Retrieves all columns for records where the customer's age is between 25 and 31, inclusive.
```
SELECT * FROM Customers WHERE age BETWEEN 25 AND 31;
```

Retrieves all columns for records where the customer is not from the USA.
```
SELECT * FROM Customers WHERE country != "USA";
```

Retrieves all columns for records where the customer is not from the USA. (Note: != and <> are equivalent in SQL.)
```
SELECT * FROM Customers WHERE country <> "USA";
```

Retrieves all columns for records where the customer is from the USA.
```
SELECT * FROM Customers WHERE country = "USA";
```

Retrieves all columns for records where the customer is from the USA. (Note: The == operator is not standard SQL; use = instead.)
```
SELECT * FROM Customers WHERE country == "USA";
```


Retrieves all columns for records where the customer is not from the UK.
```
SELECT * FROM Customers WHERE NOT country = "UK";
```

Retrieves all columns for records where the customer's first name starts with the letter 'J'.
```
SELECT * FROM Customers WHERE first_name LIKE 'J%';
```

Retrieves all columns for records where the customer's first name does not start with the letter 'J'.
```
SELECT * FROM Customers WHERE NOT first_name LIKE 'J%';
```

Deletes the record from the Customers table where the customer_id is 4.
```
DELETE FROM Customers WHERE customer_id = 4;
```

Updates the first_name to 'Alice' for the record where the customer_id is 5.
```
UPDATE Customers SET first_name = 'Alice' WHERE customer_id = 5;
```

Inserts a new record into the Customers table with the customer_id 4, first_name 'Janet', and last_name 'Davis'.
```
INSERT INTO Customers (customer_id, first_name, last_name) VALUES (4, 'Janet', 'Davis');
```


Retrieves all columns from the Customers table and orders the records by customer_id in descending order.
```
SELECT * FROM Customers ORDER BY customer_id DESC;
```

Retrieves the name column for records where the referee_id is not 2 or where referee_id is NULL.
```
SELECT name FROM Customer WHERE referee_id != 2 OR referee_id IS NULL;
```

Retrieves the name, population, and area columns from the World table for records where the area is greater than 3,000,000 or the population is greater than 25,000,000.
```
SELECT name, population, area FROM World WHERE area > 3000000 OR population > 25000000;
```

Retrieves unique author_id values (labeled as id) from the Views table where the author_id is the same as the viewer_id and the article_id is not NULL. The results are ordered by author_id.
```
SELECT DISTINCT author_id AS id FROM Views WHERE author_id = viewer_id AND article_id IS NOT NULL ORDER BY author_id;
```

Retrieves the tweet_id from the tweets table where the length of the content is greater than 15 characters. (length() is used in some SQL dialects like SQLite.)
```
SELECT tweet_id FROM tweets WHERE length(content) > 15;
```

Retrieves the tweet_id from the Tweets table where the content has more than 15 characters. (char_length() is commonly used in PostgreSQL and some other SQL dialects.)
```
SELECT tweet_id FROM Tweets WHERE char_length(content) > 15;
```


### Exercises of the class
[Find customer referee](https://leetcode.com/problems/find-customer-referee/?envType=study-plan-v2&envId=top-sql-50)  
[Big countries](https://leetcode.com/problems/big-countries/description/?envType=study-plan-v2&envId=top-sql-50)  
[Invalid tweets](https://leetcode.com/problems/invalid-tweets/?envType=study-plan-v2&envId=top-sql-50)
[Article views](https://leetcode.com/problems/article-views-i/description/?envType=study-plan-v2&envId=top-sql-50)

### Interactive SQL
https://www.programiz.com/sql/online-compiler/

### Study references

