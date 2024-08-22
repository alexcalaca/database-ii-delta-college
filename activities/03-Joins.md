### SQL exercises
#### Topic: Joins

> Prof. Alexandre Calaça  
> github.com/alexcalaca.com    
> Blog: dev.to/alexcalaca

---


For the following exercises:

```
CREATE TABLE Products (
    ProductID SERIAL PRIMARY KEY,
    ProductName VARCHAR(255) NOT NULL,
    CategoryID INT NOT NULL,
    Unit VARCHAR(255) NOT NULL,
    Price DECIMAL(10, 2) NOT NULL
);

INSERT INTO Products (ProductName, CategoryID, Unit, Price) VALUES
('Chais', 1, '10 boxes x 20 bags', 18.00),
('Chang', 1, '24 - 12 oz bottles', 19.00),
('Aniseed Syrup', 2, '12 - 550 ml bottles', 10.00),
('Chef Anton''s Cajun Seasoning', 2, '48 - 6 oz jars', 22.00),
('Chef Anton''s Gumbo Mix', 2, '36 boxes', 21.35),
('Grandma''s Boysenberry Spread', 2, '12 - 8 oz jars', 25.00),
('Uncle Bob''s Organic Dried Pears', 7, '12 - 1 lb pkgs.', 30.00),
('Northwoods Cranberry Sauce', 2, '12 - 12 oz jars', 40.00),
('Mishi Kobe Niku', 6, '18 - 500 g pkgs.', 97.00),
('Ikura', 8, '12 - 200 ml jars', 31.00);

CREATE TABLE Categories (
    CategoryID SERIAL PRIMARY KEY,
    CategoryName VARCHAR(255) NOT NULL,
    Description TEXT
);

INSERT INTO Categories (CategoryName, Description) VALUES
('Beverages', 'Soft drinks, coffees, teas, beers, and ales'),
('Condiments', 'Sweet and savory sauces, relishes, spreads, and seasonings'),
('Confections', 'Desserts, candies, and sweet breads'),
('Dairy Products', 'Cheeses'),
('Grains/Cereals', 'Breads, crackers, pasta, and cereal'),
('Meat/Poultry', 'Prepared meats'),
('Produce', 'Dried fruit and bean curd'),
('Seafood', 'Seaweed and fish'),
('Snacks', 'Cookies, chips, and nuts'),
('Baking Goods', 'Flours, sugars, and chocolate');
```

---

1. Insert a new product into the Products table with the following details:

```
ProductName: 'Tofu'
CategoryID: 7
Unit: '24 - 250 g pkgs.'
Price: 23.50
```

2. Update the price of the product 'Chang' to `21.00` in the Products table.

```

```


3. Calculate the total price of all products in the Products table.


```

```

4. Select all fields from the Categories table.


```

```

5. Count the total number of products in the Products table.


```

```

6. Select only the ProductName and Price fields from the Products table.
```

```

7. Count the number of products in each category and display the CategoryID and the count.

```

```

8. Select all fields from the Products and Categories tables where the CategoryID matches in both tables.

```

```

9. Delete the record for the product named 'Aniseed Syrup' from the Products table.

```

```

10. Select all fields from the Products table and any matching fields from the Categories table, showing all products even if they don't have a matching category.

```

```

11. Update the Unit of the product `Mishi Kobe Niku` to `20 - 500 g pkgs.` in the Products table.


```

```

12. Select all fields from the Categories table and any matching fields from the Products table, showing all categories even if they don't have matching products.

```

```

 

