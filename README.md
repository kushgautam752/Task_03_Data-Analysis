# 🛒 Retail Orders Database – Querying Fundamentals  

## 📌 Project Overview  
This project is part of my **SQL learning journey** where I worked with a **mock retail dataset** to practice SQL fundamentals.  
The dataset simulates a retail business with customers, products, orders, and order items.  

The goal was to apply **basic SQL operations** like `SELECT`, `WHERE`, `ORDER BY`, `GROUP BY`, and `JOIN` to extract meaningful insights.  

---

## 📂 Dataset Structure  
The dataset contains 4 CSV files:  

1. **customers.csv** – Customer details (ID, name, email, city, state)  
2. **products.csv** – Product details (ID, name, category, price)  
3. **orders.csv** – Order details (ID, customer, order date, total amount)  
4. **order_items.csv** – Items in each order (ID, order, product, quantity, price)  

---

## 🛠️ SQL Schema (PostgreSQL)  

```sql
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    city VARCHAR(50),
    state VARCHAR(50)
);

CREATE TABLE products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(100),
    category VARCHAR(50),
    price DECIMAL(10,2)
);

CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT REFERENCES customers(customer_id),
    order_date DATE,
    total_amount DECIMAL(12,2)
);

CREATE TABLE order_items (
    order_item_id INT PRIMARY KEY,
    order_id INT REFERENCES orders(order_id),
    product_id INT REFERENCES products(product_id),
    quantity INT,
    price DECIMAL(10,2)
);

🧑‍💻 Tools Used

PostgreSQL

SQL (SELECT, WHERE, ORDER BY, GROUP BY, JOIN, DATE functions)
