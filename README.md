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

# Basic SQL operations in PostgreSQL
### 1. Create the table
```
CREATE TABLE products (product_id INT PRIMARY KEY, product_name VARCHAR(100), price NUMERIC);
```

### 2. Insert the data
Adds a new record to the table.
```
INSERT INTO products (product_id, product_name, price) VALUES (1, 'Laptop', 999.99)
```

### 3. Query Data
Retrieves records from the table.
```
SELECT * FROM products
```

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
