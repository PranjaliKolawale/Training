# PostgreSQL
Postgresql is an open-source relational database management system (RDBMS) that stores and manages data in structured tables using SQL.<br>
- Designed to manage structured data with high reliability and cosistency.
- Supports advanced SQL features, transactions, indexes, and stored procedures.
- Handles relational, JSON, array, and custom data types efficiently.
- Used by banking, e-commerce, healthcare, and enterprise applications to manage large volumes of data securely.  

# Data Types of PostgreSQL
| Category | Data Types | Description |
|----------|------------|-------------|
| Numeric Types | Integer, BIG INT, DECIMAL | Store numeric values |
| Character Types | VARCHAR, TEXT | Store text and strings |
| Date and Time Types | DATE, TIMESTAMP | Store date and time values |
| Boolean Type | Boolean | Store TRUE, FALSE or NULL |
| JSON Types | JSON, JSONB | Store JSON documents |


### Working PostgreSQL
- Stores data in tables using a row-based structure.
- Uses a relational model to manage and organize data.
- Records transactions in write-ahead logs (WAL) for durability and recovery.
- Employs Multi-Version concurrency control (MVCC) to handle concurrent transactions.
- Ensures data cosistency, reliability and high performance.

### Why choose PostgreSQL over other SQL Databases.
1. Open source and Free: PostgreSQL is completely free to use and has a strong developer community.
2. Advanced SQL Support: Supports complex queries, joins, subqueries, views stored procedures and triggers.
3. Acid Compliance: Ensure reliable and secure transactions with data integrity.
4. JSON Support: Can store and query JSON data efficiently, making it suitable for odern applications.
5. Extensible: User can create custom functions, data types and extensions.
6. High Performance: Optimized for handling large datasets and complex workloads.
7. Multi-Language Support: Works with popular programming languages such as Python, Java, C/C++, C#, Node.js, Go, Ruby, Perl and Tcl.

### Applications
1. Enterprise Application: Used in large business system requiring realiability.
2. Data Analytics and Warehousing: Stores and processes large volumes of data for analysis.
3. Financial Systems: Supports Banking and Financial applications with strong transaction management.
4. Geographic Information Systems (GIS): Handles spatial and location-based data using PostGIS.
5. Web Applications: Powers dynamic websites and web services.

# Basic SQL operations in PostgreSQL
### 1. Create the table
```
CREATE TABLE Currency (
    CurrencyCode CHAR(3) NOT NULL,
    Name VARCHAR(100) NOT NULL,
    ModifiedDate TIMESTAMP NOT NULL DEFAULT NOW()
);
```

### 2. Insert the data
Adds a new record to the table.
```
INSERT INTO Currency (CurrencyCode, Name, ModifiedDate) VALUES ('AED', 'Emirati Dirham', '2019-04-30 00:00:00');
```

### 3. Query Data
Retrieves records from the table.
```
SELECT * FROM Currency
```
### PostgresSQL - Database
Creating a database in PostgreSQL allows users to store, organize and manage related data in a separate database environment.

- Supports multiple databases on one server.
- Contains tables, views and other database objects.

1. Create Database
```
CREATE DATABASE mydatabase;
```

2. Restore Database
```
pg_restore -U postgres -d dvdrental C:\Users\sample_database\dvdrental.tar
``` 

### PostgresSQL Alter Database
PostgreSQL ALTER DATABASE command modifies the properties of an existing database, such as its name, owner, configuration settings or connection limits. It helps administrators manage and update database settings without recreating the database.

- Modifies database properties and settings.
- Supports administrative tasks such as renaming databases and changing ownership.

1. Rename Database
```
ALTER DATABASE database_name
RENAME TO new_database_name;
```

2. Change Database Owner
```
ALTER DATABASE database_name
OWNER TO new_owner;
```

3. Change the Default Tablespace
```
ALTER DATABASE database_name
SET TABLESPACE tablespace_name;
```

4. Set the Connection Limit
```
ALTER DATABASE database_name
CONNECTION LIMIT limit;
```

### PostgreSQL Data Types
##### 1. Numeric Type
| Name | Description |
|------|-------------|
| smallint | 2-byte integer |
| integer | 4-byte integer |
| bigint | 8-byte integer |
| decimal(p,s) | Exact numeric value with precision and scale |
| numeric(p,s) | Exact numeric value with precision and scale |
| real | 4-byte floating-point number |
| double precision | 8-byte floating-point number |
| serial | Auto-incrementing integer |
| bigserial | Auto-incrementing large integer |

##### 2. Monetary Type
| Name | Description |
|------|-------------|
| money | Fixed-point type used for storing currency values. |

##### 3. Character Types
| Name | Description |
|------|-------------|
| char(n) | Fixed-length character type. |
| varchar(n) | Variable-length character type with a maximum length of n. |
| text | Variable-length character type with no specific length limit. |

##### 4. Binary Types
| Name | Description |
|------|-------------|
| bytea | Stores binary data as a byte array. |

##### 5. Date/Time Types
| Name | Description |
|------|-------------|
| date | Stores calendar dates. |
| time | Stores time of day. |
| timestamp | Stores date and time without time zone. |
| timestamptz | Stores date and time with time zone. |
| interval | Represents a span of time. |

##### 6. Boolean Types
| Name | Description |
|------|-------------|
| boolean | Stores true, false or NULL values. |

##### 7. Enumerated Types
| Name | Description |
|------|-------------|
| enum | User-defined type with a fixed set of values. |

##### 8. Geometric Types
| Name | Description |
|------|-------------|
| point | Represents a point in 2D space. |
| line | Represents an infinite line. |
| lseg | Represents a line segment. |
| box | Represents a rectangular box. |
| path | Represents an open or closed path. |
| polygon | Represents a polygon. |
| circle | Represents a circle with center and radius. |

##### 9. Other Data Types
| Name | Description |
|------|-------------|
| UUID | Stores 128-bit universally unique identifiers. |
| JSON | Stores JSON data as text. |
| JSONB | Stores JSON data in binary-optimized format. |
| INET | Stores IPv4 or IPv6 addresses. |
| CIDR | Stores network blocks. |
| MACADDR | Stores MAC addresses. |
| TSVECTOR | Stores full-text search documents. |

### PostgreSQL - SELECT
The SELECT statement in PostgreSQL is used to retrieve data from one or more tables. It allows you to fetch specific columns or all columns.

- Supports filtering with the WHERE clause.
- Can be combined with ORDER BY, GROUP BY, HAVING and LIMIT.
```
CREATE TABLE books (
    book_id INTEGER PRIMARY KEY,
    book_title VARCHAR(100),
    category VARCHAR(50),
    price INTEGER
);

INSERT INTO books (book_id, book_title, category, price)
VALUES
(101, 'Python Basics', 'Programming', 650),
(102, 'SQL Essentials', 'Database', 550),
(103, 'Data Structures', 'Programming', 700),
(104, 'Digital Marketing', 'Marketing', 500),
(105, 'Machine Learning', 'AI', 900);
```
1. Retrieve all columns
```
SELECT * FROM books;
```

2. Retrieve Specific Columns
```
SELECT book_title, price FROM books;
```

3. Retrieve Data Using WHERE Clause
```
SELECT book_title, price FROM books WHERE price > 600;
```

4. Retrieve Data Using ORDER BY
```
SELECT * FROM books ORDER BY price DESC;
```
### PostgreSQL - ORDER BY Clause
```
CREATE TABLE Product (
    ProductID SERIAL PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    ProductNumber VARCHAR(25) NOT NULL,
    Color VARCHAR(15),
    StandardCost NUMERIC NOT NULL,
    ListPrice NUMERIC NOT NULL,
    Size VARCHAR(5),
    Weight DECIMAL(8,2),
    DaysToManufacture INTEGER NOT NULL
);
```
1. Sort Data in ascending order
```
SELECT ProductID, Name, ListPrice
FROM Production.Product
ORDER BY ListPrice ASC;
```

2. Sort Data in Descending Order
```
SELECT ProductID, Name, ListPrice
FROM Production.Product
ORDER BY ListPrice DESC;
```

3. Sort by Multiple Columns
```
SELECT ProductID, Name, Color, ListPrice
FROM Production.Product
ORDER BY Color ASC, ListPrice DESC;
```

4. Use ORDER BY with a WHERE Clause
```
SELECT ProductID, Name, Color, ListPrice
FROM Production.Product
WHERE Color = 'Black'
ORDER BY ListPrice ASC;
```

5. Use ORDER BY with LIMIT
```
SELECT ProductID, Name, ListPrice
FROM Production.Product
ORDER BY ListPrice DESC
LIMIT 5;
```

### PostgreSQL - WHERE Clause
The WHERE clause in PostgreSQL is used to filter rows based on a specified condition. It returns only the records that satisfy the condition, making it easier to retrieve specific data from a table.

- Can be used with SELECT, UPDATE and DELETE statements.
- Supports comparison, logical and special operators.
- Allows multiple conditions using AND, OR and NOT.

1. Using WHERE with a Comparison Operator
```
SELECT * FROM production.product
WHERE ListPrice > 1000;
```

2. Using WHERE with a String Condition
```
SELECT * FROM production.product
WHERE Color = 'Black';
```

3. Using WHERE with Multiple Conditions
```
SELECT * FROM production.product
WHERE Color = 'Black'
AND ListPrice > 500;
```

4. Using WHERE with UPDATE
```
UPDATE production.product
SET ListPrice = 1500
WHERE ProductID = 1;
```

### PostgreSQL - FETCH Clause 
The PostgreSQL FETCH clause is an essential feature for controlling and managing the number of rows returned in our SQL queries. It provides a standardized approach for limiting results, similar to the LIMIT clause but with more flexibility and compatibility across different database systems.

1. Fetching the First 10 Rows
```
SELECT * FROM Product
ORDER BY ProductID ASC
LIMIT 10;
```

2. Fetching Rows with OFFSET
```
SELECT * FROM Product
OFFSET 5;
```

### PostgreSQL - IN operator
The IN operator in PostgreSQL is used to check whether a value matches any value in a specified list. It provides a simple way to compare a column against multiple values without using multiple OR conditions.

- Can be used with SELECT, UPDATE and DELETE statements.
- Can also be used with a subquery.

1. Using the PostgreSQL IN Operator with a List of Numbers
```
SELECT * FROM production.product
WHERE ProductID IN (1, 3, 5);
```

2. Using IN with NOT
```
SELECT * FROM production.product
WHERE ListPrice NOT IN (20, 80, 1200);
```

### PostgreSQL - HAVING clause
The HAVING clause in PostgreSQL filters grouped records after the GROUP BY clause is applied. It is used to filter groups based on aggregate conditions.

- Filters grouped records based on aggregate conditions.
- Supports aggregate functions such as COUNT(), SUM(), AVG(), MIN() and MAX().

1. HAVING with COUNT()
```
SELECT Color, COUNT(*) AS total_products
FROM Product
GROUP BY Color
HAVING COUNT(*) > 1;
```

2. HAVING with SUM()
```
SELECT Color, SUM(ListPrice) AS total_price
FROM Product
GROUP BY Color
HAVING SUM(ListPrice) > 1000;
```

3. HAVING with AVG()
```
SELECT Color, AVG(ListPrice) AS average_price
FROM Product
GROUP BY Color
HAVING AVG(ListPrice) > 100;
```

4. HAVING with WHERE
```
SELECT Color, COUNT(*) AS total_products
FROM production.product
WHERE ListPrice > 20
AND Color = 'Black'
GROUP BY Color
HAVING COUNT(*) > 1;
```

5. HAVING with Multiple Conditions
```
SELECT Color,
       COUNT(*) AS total_products,
       AVG(ListPrice) AS average_price
FROM production.product
GROUP BY Color
HAVING COUNT(*) > 1
AND AVG(ListPrice) > 100;
```

### PostgreSQL - GROUP BY clause
PostgreSQL GROUP BY clause divides rows into categories based on one or more column values, making it easier to calculate summary information for each category.

- Creates separate result sets for each category.
- Works with aggregate functions like COUNT(), SUM(), AVG(), MIN() and MAX().

1. Group Rows Without an Aggregate Function
```
SELECT CountryRegionCode
FROM Sales.SalesTerritory
GROUP BY CountryRegionCode;
```

2. Calculate Total Sales for Each Region
```
SELECT
    st.Name AS region,
    SUM(so.TotalDue) AS total_sales
FROM Sales.SalesOrderHeader so
JOIN Sales.SalesTerritory st
    ON so.TerritoryID = st.TerritoryID
GROUP BY st.Name
ORDER BY total_sales DESC;
```

3. Count the Number of Sales by Each Sales Person
```
SELECT
    SalesPersonID,
    COUNT(*) AS total_sales
FROM Sales.SalesOrderHeader
WHERE SalesPersonID IS NOT NULL
GROUP BY SalesPersonID
ORDER BY total_sales DESC;
```

4. Group by Multiple Columns
```
SELECT
    TerritoryID,
    Status,
    COUNT(*) AS total_orders,
    SUM(TotalDue) AS total_sales
FROM Sales.SalesOrderHeader
GROUP BY TerritoryID, Status
ORDER BY TerritoryID, Status;
```

### PostgreSQL - LIKE operator
The PostgreSQL LIKE operator searches for a specified pattern in a text value. It is commonly used with wildcard characters to perform flexible string matching in SQL queries.

- Matches text based on a specified pattern.
- Supports wildcard characters (% and _) for flexible searches.

1. Find Names Starting with 'Jen'
```
SELECT ProductID, Name, Color, ListPrice
FROM production.product
WHERE Name LIKE 'M%';
```

2. Find Product Names Containing 'Bike'
```
SELECT ProductID, Name, Color, ListPrice
FROM production.product
WHERE Name LIKE '%Bike%';
```

3. Use Both % and _ Wildcards
```
SELECT ProductID, Name, Color, ListPrice
FROM production.product
WHERE Name LIKE 'M___';
```

4. Find Product Names That Do Not Start with 'M'
```
SELECT ProductID, Name, Color, ListPrice
FROM production.product
WHERE Name NOT LIKE 'M%';
```

### PostgreSQL - BETWEEN operator
The BETWEEN operator in PostgreSQL is used to filter rows where a column value falls within a specified range. The range is inclusive, meaning both the starting and ending values are included in the result.

- Can be used with numeric, text and date values.
- Can be combined with clauses such as WHERE, ORDER BY and LIMIT.

1. Use BETWEEN with Numeric Values
```
SELECT ProductID, Name, ListPrice
FROM Product
WHERE ListPrice BETWEEN 100 AND 1000;
```

2. Use NOT BETWEEN
```
SELECT ProductID, Name, ListPrice
FROM Product
WHERE ListPrice NOT BETWEEN 100 AND 1000;
```

3. Use BETWEEN with Text Values
```
SELECT ProductID, Name, Color
FROM production.product
WHERE Name BETWEEN 'A' AND 'M';
```

4. Use BETWEEN with ORDER BY
```
SELECT ProductID, Name, ListPrice
FROM production.product
WHERE ListPrice BETWEEN 100 AND 1000
ORDER BY ListPrice DESC;
```

### PostgreSQL - CREATE TABLE
The CREATE TABLE statement in PostgreSQL is used to create a new table in a database by defining its structure.

- Defines column names and their data types.
- Supports constraints to maintain data integrity
- Organizes data in a structured format for storing records.

1. CREATE TABLE
```
CREATE TABLE Department (
    DepartmentID SERIAL NOT NULL,
    Name VARCHAR(50) NOT NULL,
    GroupName VARCHAR(50) NOT NULL,
    ModifiedDate TIMESTAMP NOT NULL DEFAULT NOW()
);
```

### PostgreSQL - SELECT INTO
The PostgreSQL SELECT INTO statement allows users to create a new table directly from the result set of a query. This command is ideal for duplicating or organizing data from an existing table into a new one for further analysis. SELECT INTO does not return data to the client but saves it in a new table, allowing for streamlined data handling and improved query performance.

1. Creating a Permanant table
```
SELECT *
INTO department_permanent
FROM Department;
```

2. Creating a Temporary Table
```
SELECT *
INTO TEMP TABLE department_temp
FROM Department;
```

### PostgreSQL - ALTER TABLE
The ALTER TABLE statement in PostgreSQL is used to modify the structure of an existing table without deleting the existing data.

Modifies table structure by adding, modifying, dropping, or renaming columns and tables.
Adds or removes constraints such as PRIMARY KEY, FOREIGN KEY, UNIQUE and CHECK.

1. Add a new column
```
ALTER TABLE Department
ADD COLUMN Description VARCHAR(100);
```

2. Rename a Column
```
ALTER TABLE Department
RENAME COLUMN description TO department_description;
```

3. Change the Data Type of a Column
```
ALTER TABLE Department
ALTER COLUMN groupname TYPE VARCHAR(100);
```

4. Rename the Table
```
ALTER TABLE Department
RENAME TO department_details;
```

5. Add a CHECK Constraint
```
ALTER TABLE humanresources.department_details
ADD CONSTRAINT check_department_id
CHECK (departmentid > 0);
```

6. Drop a Column
```
ALTER TABLE Department_details
DROP COLUMN department_description;
```

7. Truncate a Table
```
TRUNCATE TABLE Department;
```

8. COPY TABLE with data
```
CREATE TABLE department_copy AS
SELECT *
FROM Department;
```

9. Copy table structure only
```
CREATE TABLE department_structure AS
SELECT *
FROM Department
WITH NO DATA;
```

10. Copy data into an existing table
```
INSERT INTO department_copy
SELECT *
FROM Department;
```

### PostgreSQL - INSERT
```
CREATE TABLE ProductCategory (
    ProductCategoryID SERIAL PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    rowguid UUID DEFAULT gen_random_uuid(),
    ModifiedDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```
1. Insert a Single Row
```
INSERT INTO ProductCategory (Name)
VALUES ('Electronics');
```

2. Insert Multiple Rows
```
INSERT INTO ProductCategory (Name)
VALUES
    ('Furniture'),
    ('Clothing'),
    ('Accessories'),
    ('Stationery');
```
3. Insert Values into Selected Columns
```
INSERT INTO ProductCategory (ProductCategoryID, Name)
VALUES (10, 'Sports');
```

4. Insert Multiple Values in various rows
```
INSERT INTO ProductCategory (Name)
VALUES
    ('Electronics'),
    ('Furniture'),
    ('Clothing'),
    ('Accessories');
```

5. Inserting Multiple Rows Without Specifying Column Names
```
INSERT INTO ProductCategory
VALUES
    (1, 'Electronics', DEFAULT, DEFAULT),
    (2, 'Furniture', DEFAULT, DEFAULT),
    (3, 'Clothing', DEFAULT, DEFAULT),
    (4, 'Accessories', DEFAULT, DEFAULT);
```

##### PostgreSQL UPDATE Statement
The PostgreSQL UPDATE statement is used to modify existing data in a table by changing the values of one or more columns.

- The WHERE clause specifies which rows should be updated.
- Without the WHERE clause, all rows in the table are updated.
- Multiple columns can be updated in a single statement.

1. Update a Single Column
```
UPDATE ProductCategory
SET Name = 'Home Appliances'
WHERE ProductCategoryID = 1;
```

2. Update Multiple Columns
```
UPDATE ProductCategory
SET Name = 'Electronic Devices',
    ModifiedDate = CURRENT_TIMESTAMP
WHERE ProductCategoryID = 2;
```

3. Update Multiple Rows
```
UPDATE ProductCategory
SET Name = 'General Products'
WHERE ProductCategoryID IN (3, 4);
```

4. Omitting the WHERE Clause
```
UPDATE ProductCategory
SET ModifiedDate = CURRENT_TIMESTAMP;
```

##### PostgreSQL DELETE 
The DELETE statement in PostgreSQL is used to remove one or more rows from a table. The WHERE clause specifies which rows should be deleted. If the WHERE clause is omitted, all rows in the table are deleted, while the table structure remains unchanged.

1. Delete a single row
```
DELETE FROM ProductCategory
WHERE ProductCategoryID = 1;
```

2. Delete Multiple Rows
```
DELETE FROM ProductCategory
WHERE ProductCategoryID IN (2, 3);
```

3. Delete All Rows
```
DELETE FROM ProductCategory;
```

##### PostgreSQL - Upsert
The PostgreSQL UPSERT operation is used to insert a new row into a table or update an existing row if a conflict occurs. It is implemented using the INSERT ... ON CONFLICT clause, which helps prevent duplicate records and simplifies insert-or-update operations.

- Prevent duplicate records based on PRIMARY KEY or UNIQUE constraints.
- Simplify data synchronization and bulk data operations.

1. Update an Existing Row Using UPSERT
```
INSERT INTO ProductCategory (ProductCategoryID, Name)
VALUES (1, 'Smartphones')
ON CONFLICT (ProductCategoryID)
DO UPDATE
SET Name = EXCLUDED.Name;
```

2. Insert a New Row Using UPSERT
```
INSERT INTO ProductCategory (ProductCategoryID, Name)
VALUES (10, 'Gaming')
ON CONFLICT (ProductCategoryID)
DO UPDATE
SET Name = EXCLUDED.Name;
```

3. Skip Insert Using ON CONFLICT DO NOTHING
```
INSERT INTO ProductCategory (ProductCategoryID, Name)
VALUES (1, 'Electronics')
ON CONFLICT (ProductCategoryID)
DO NOTHING;
```

4. UPSERT Using ON CONFLICT ON CONSTRAINT
```
INSERT INTO ProductCategory (ProductCategoryID, Name)
VALUES (1, 'Home Appliances')
ON CONFLICT ON CONSTRAINT productcategory_pkey
DO UPDATE
SET Name = EXCLUDED.Name;
```

5. UPSERT Using WHERE
```
INSERT INTO ProductCategory (ProductCategoryID, Name)
VALUES (1, 'Smart Devices')
ON CONFLICT (ProductCategoryID)
DO UPDATE
SET Name = EXCLUDED.Name
WHERE ProductCategory.Name <> EXCLUDED.Name;
```

### PostgreSQL - Transactions
A PostgreSQL transaction groups one or more SQL statements (such as INSERT, UPDATE, DELETE and SELECT) into a single unit of work. It ensures that either all operations are completed successfully or none of them are applied, helping maintain data consistency and integrity.

- Execute multiple SQL statements as a single unit.
- Commit all changes only after successful execution and roll back changes if an error occurs.
- Ensure reliable and consistent database operations.

##### ACID Properties
Atomicity: Ensures that all operations in a transaction are completed successfully or none of them are applied.
Consistency: Ensures that the database moves from one valid state to another while following all constraints and rules.
Isolation: Ensures that concurrent transactions do not interfere with each other.
Durability: Ensures that committed changes are permanently stored, even if the database system crashes.

##### PostgreSQL Transaction Control Commands
1. BEGIN Command
```
BEGIN;
-- or
BEGIN TRANSACTION;
```

2. COMMIT Command
```
COMMIT;
```

3. ROLLBACK Command
```
ROLLBACK;
```

4. SAVEPOINT Command
```
SAVEPOINT savepoint_name;
```

5. ROLLBACK TO SAVEPOINT
```
ROLLBACK TO SAVEPOINT savepoint_name;
```

6. RELEASE SAVEPOINT
```
RELEASE SAVEPOINT savepoint_name;
```

##### Types of PostgreSQL Transactions
Read Transactions: Retrieve data using SELECT statements.
Write Transactions: Modify data using INSERT, UPDATE or DELETE.
Implicit Transactions: PostgreSQL automatically treats each SQL statement as a transaction when no explicit transaction is started.
Explicit Transactions: Transactions manually controlled using BEGIN, COMMIT and ROLLBACK.

##### Best Practices
- Keep transactions as short as possible to reduce locking.
- Commit transactions only after verifying all operations.
- Use ROLLBACK to recover from errors.
- Use SAVEPOINT when partial rollback is required.
- Avoid long-running transactions to improve concurrency and performance.


##### PostgreSQL Commit Command
In PostgreSQL, the COMMIT command is used to finalize a transaction by saving all changes made during that transaction to the database. It ensures that any modifications to the database, such as inserts, updates, or deletes, are permanently stored. As shown in the given below syntax of PostgreSQL COMMIT, all three variations achieve the same goal. They save the changes made during the current transaction to the database. Unlike other database languages in PostgreSQL, we commit the transaction in 3 different forms which are mentioned above.

1. Inserting Data with COMMIT
```
BEGIN;

INSERT INTO BankStatements (customer_id, full_name, balance)
VALUES (4, 'Priya Chetri', 500);

COMMIT;
```

2. Updating Data with COMMIT
```
BEGIN;

UPDATE BankStatements
SET balance = balance - 500
WHERE customer_id = 1;

UPDATE BankStatements
SET balance = balance + 500
WHERE customer_id = 2;

COMMIT;
```

### PostgreSQL - Primary Key
The PRIMARY KEY constraint in PostgreSQL uniquely identifies each record in a table. Every table can have only one primary key, which can consist of one or more columns.

- Prevent duplicate values in the primary key column.
- Disallow NULL values in the primary key.
- Improve query performance by automatically creating a unique index.

1. Primary key during table creation
```
CREATE TABLE Products (
    ProductID SERIAL PRIMARY KEY,
    ProductName VARCHAR(100) NOT NULL,
    Category VARCHAR(50),
    Price NUMERIC(10,2),
    StockQuantity INTEGER
);
```

##### Types of Primary Key
Simple Primary Key: A primary key that consists of a single column.
Composite Primary Key: A primary key that consists of two or more columns.

2. Verify the PRIMARY KEY Constraint
```
INSERT INTO Product (ProductID, Name)
VALUES (1, 'Test Product');
```

3. Add a PRIMARY KEY to an Existing Table
```
ALTER TABLE Product
ADD PRIMARY KEY (ProductID);
```

4. Create a Table with a Composite PRIMARY KEY
```
CREATE TABLE BusinessEntityAddress_Copy (
    BusinessEntityID INTEGER,
    AddressID INTEGER,
    AddressTypeID INTEGER,
    rowguid UUID,
    ModifiedDate TIMESTAMP,
    PRIMARY KEY (BusinessEntityID, AddressID, AddressTypeID)
);
```

### PostgreSQL - Foreign Key
A FOREIGN KEY constraint in PostgreSQL is used to establish a relationship between two tables by ensuring that values in the child table match existing values in the parent table. It helps maintain referential integrity by preventing invalid references between related tables.

- Prevent orphan records and invalid data relationships.
- Use actions such as CASCADE, SET NULL and RESTRICT when updating or deleting related records.

Parent Tables
Table 1:
```
CREATE TABLE FK_Practice.BusinessEntity (
    BusinessEntityID INT PRIMARY KEY,
    EntityName VARCHAR(100) NOT NULL
);
```

Table 2:
```
CREATE TABLE FK_Practice.Address (
    AddressID INT PRIMARY KEY,
    City VARCHAR(50) NOT NULL,
    State VARCHAR(50),
    PostalCode VARCHAR(10)
);
```

Table 3:
```
CREATE TABLE FK_Practice.AddressType (
    AddressTypeID INT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL
);
```

Child Table
Table 1:
```
CREATE TABLE FK_Practice.BusinessEntityAddress (
    BusinessEntityID INT NOT NULL,
    AddressID INT NOT NULL,
    AddressTypeID INT NOT NULL,
    ModifiedDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,

    PRIMARY KEY (BusinessEntityID, AddressID, AddressTypeID)
);
```
1. Add Foreign Key – BusinessEntityID
```
ALTER TABLE FK_Practice.BusinessEntityAddress
ADD CONSTRAINT FK_BusinessEntity
FOREIGN KEY (BusinessEntityID)
REFERENCES FK_Practice.BusinessEntity (BusinessEntityID);
``

2. Add Foreign Key – AddressID
```
ALTER TABLE FK_Practice.BusinessEntityAddress
ADD CONSTRAINT FK_Address
FOREIGN KEY (AddressID)
REFERENCES FK_Practice.Address (AddressID);
```

3. Add Foreign Key – AddressTypeID
```
ALTER TABLE FK_Practice.BusinessEntityAddress
ADD CONSTRAINT FK_AddressType
FOREIGN KEY (AddressTypeID)
REFERENCES FK_Practice.AddressType (AddressTypeID);
```

4. Verify Foreign Keys
```
SELECT
    conname AS constraint_name,
    conrelid::regclass AS table_name,
    confrelid::regclass AS referenced_table
FROM pg_constraint
WHERE contype = 'f'
AND connamespace = 'fk_practice'::regnamespace;
```

5. Test the Foreign Key constraint
```
INSERT INTO FK_Practice.BusinessEntityAddress
(BusinessEntityID, AddressID, AddressTypeID)
VALUES (99, 101, 2);
```

### PostgreSQL - CHECK Constraint
The CHECK constraint in PostgreSQL is used to enforce a condition on the values stored in a column or a group of columns. It ensures that only values satisfying the specified condition can be inserted or updated in the table. The CHECK constraint allows users to:

- Prevent invalid data from being inserted or updated.
- Maintain data integrity in the database.
- Apply validation rules at the column or table level.

```
ALTER TABLE FK_Practice.BusinessEntity
ADD CONSTRAINT chk_entityname
CHECK (LENGTH(EntityName) >= 3);
```

### PostgreSQL - UNIQUE Constraint
The UNIQUE constraint in PostgreSQL ensures that all values in a column or a group of columns are unique across the table. Unlike a PRIMARY KEY, a table can have multiple UNIQUE constraints and a UNIQUE column can contain NULL values (unless it is also defined as NOT NULL).

- Prevent duplicate values in one or more columns.
- Maintain data uniqueness and consistency.
- Create unique constraints during table creation or using ALTER TABLE.

```
ALTER TABLE FK_Practice.AddressType
ADD CONSTRAINT uq_addresstype_name
UNIQUE (Name);
```

### PostgreSQL - NOT NULL Constraint
The NOT NULL constraint in PostgreSQL ensures that a column always contains a value and cannot store NULL.

- Enforce mandatory fields in a table.
- Improve data consistency and integrity.

```
ALTER TABLE FK_Practice.BusinessEntity
ALTER COLUMN EntityName SET NOT NULL; 
```
















