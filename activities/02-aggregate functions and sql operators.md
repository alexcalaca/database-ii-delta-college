### SQL exercises
#### Topic: Aggregate functions and SQL operators
> Prof. Alexandre Calaça  
> github.com/alexcalaca.com    
> Blog: dev.to/alexcalaca

---


For the following exercises, create a table named `Products`:
```
CREATE TABLE Products (
    id SERIAL PRIMARY KEY,         -- Automatic primary key
    product_name VARCHAR(100) NOT NULL,  -- Product name, must not be null
    description TEXT,             -- Optional description
    price NUMERIC(10, 2) NOT NULL, -- Price, must not be null, with two decimal places
    inserted_at DATE,              -- Date attribute to track creation date
    is_available BOOLEAN          -- Boolean attribute to indicate availability
);
```

---

1. Find the Average Price of Available Products  
Goal: Calculate the average price of all products that are currently available

```

```

2. Identify the Most Expensive and Least Expensive Products  
Goal: Find the maximum and minimum prices of products, and display the corresponding product names.

```

```


3. Count the Number of Products Inserted in the Last 30 Days  
Goal: Count how many products have been inserted in the last 30 days from today's date.

```

```

4. Sum the Prices of Products That Fall Within a Specific Price Range  
Goal: Calculate the total price of products that have a price between 50 and 200.

```

```

5. List Products with Specific Characteristics Using SQL Operators  
Goal: Retrieve the names of products that are available, priced above 100, and do not contain the word "Basic" in their name.

```

```
