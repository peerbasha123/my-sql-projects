# my-sql-projects
A SQL-only project focused on analyzing sales data using Oracle SQL
-- 1. List all customers
SELECT * FROM customers;

-- 2. Get all products in the 'Electronics' category
SELECT * FROM products
WHERE category = 'Electronics';

-- 3. Find orders placed after Jan 1, 2024
SELECT * FROM orders
WHERE order_date > TO_DATE('2024-01-01', 'YYYY-MM-DD');

-- 4. List all orders from customers in 'India'
SELECT o.*
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id
WHERE c.country = 'India';

-- 5. Show product names and prices for items ordered in order_id = 1
SELECT p.product_name, oi.quantity, oi.item_price
FROM order_items oi
JOIN products p ON oi.product_id = p.product_id
WHERE oi.order_id = 1;
