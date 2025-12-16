-- DAY 1 - Basic Database Operations

-- Create a new database and switch to it
CREATE DATABASE test_db;
USE test_db;

-- Create a simple table with id and name
CREATE TABLE sample_table (
    id INT PRIMARY KEY NOT NULL,
    name VARCHAR(50) NOT NULL
);

-- Display all tables in the database
SHOW TABLES;

-- Remove the sample table
DROP TABLE sample_table;

-- Create students table
CREATE TABLE students (
    id INT,
    name VARCHAR(50),
    age INT
);

-- Insert student records
INSERT INTO students (id, name, age) VALUES
(1, 'Adebayo', 21),
(2, 'Oluwaseun', 22),
(3, 'Damilola', 20),
(4, 'Kehinde', 23),
(5, 'Taiwo', 19),
(6, 'Bolanle', 24),
(7, 'Yemi', 22),
(8, 'Funke', 21),
(9, 'Sadiq', 25),
(10, 'Ibrahim', 20),
(11, 'Ridwan', 23),
(12, 'Zainab', 19),
(13, 'Abdulrahman', 24),
(14, 'Tosin', 21),
(15, 'Aishat', 22);

-- Retrieve all students
SELECT * FROM students;

-- Retrieve students ordered by age
SELECT * 
FROM students
WHERE age > 0
ORDER BY age ASC;


-- DAY 2 - – Database Schema & Relationships

-- Create school database
CREATE DATABASE school_db;
USE school_db;

-- Create students table
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);

SELECT * FROM students

-- Create courses table
CREATE TABLE courses (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(50),
    credits INT
);

SELECT * FROM courses

-- Create enrollments table with foreign keys
CREATE TABLE enrollments (
    enrollment_id INT PRIMARY KEY,
    student_id INT,
    course_id INT,
    grade CHAR(2),
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (course_id) REFERENCES courses(course_id)
);

SELECT * FROM enrollments

-- Insert students
INSERT INTO students VALUES
(1, 'Adekunle', 20),
(2, 'Sola', 22),
(3, 'Yusuf', 21),
(4, 'Bashir', 23),
(5, 'Kafayat', 19),
(6, 'Habeeb', 24),
(7, 'Maryam', 22),
(8, 'Rasheed', 21),
(9, 'Lateef', 23),
(10, 'Anuoluwapo', 20),
(11, 'Zainab', 19),
(12, 'Ridwan', 24),
(13, 'Mubarak', 22),
(14, 'Titi', 21),
(15, 'Sadiya', 20);

-- Insert courses
INSERT INTO courses VALUES
(1, 'Database Systems', 3),
(2, 'Software Engineering', 4),
(3, 'Web Application Dev', 3),
(4, 'Operating Systems', 4),
(5, 'Data Analytics', 3);

-- Insert enrollments
INSERT INTO enrollments VALUES
(1, 1, 1, 'A'),
(2, 2, 2, 'B'),
(3, 3, 3, 'A'),
(4, 4, 4, 'C'),
(5, 5, 5, 'B');


-- DAY 3 - Operators, Filtering & Sorting

-- Create e-commerce database
CREATE DATABASE e_commerce;
USE e_commerce;

-- Create products table
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(50),
    price DECIMAL(10,2)
);

-- Insert product records
INSERT INTO products VALUES
(1, 'Shea Butter Cream', 3500),
(2, 'Herbal Soap', 1800),
(3, 'Black Soap', 2600),
(4, 'Body Oil', 4200),
(5, 'Face Scrub', 1500);

-- Apply 8% discount to products above 2000
SELECT 
    product_name,
    price,
    price * 0.92 AS discount_price
FROM products
WHERE price > 2000;

-- Create employees table
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(50),
    department VARCHAR(50),
    hire_date DATE
);

-- Insert employee records
INSERT INTO employees VALUES
(1, 'Olawale', 'Sales', '2022-02-10'),
(2, 'Khadijah', 'HR', '2021-06-15'),
(3, 'Suleiman', 'Sales', '2023-01-20'),
(4, 'Aminat', 'Finance', '2020-11-01');

-- Retrieve Sales employees ordered by hire date
SELECT employee_name, department, hire_date
FROM employees
WHERE department = 'Sales'
ORDER BY hire_date;

-- DAY 4 - Logical Operators & Joins

-- Update employee contact details
ALTER TABLE employees
ADD phone_number VARCHAR(15),
ADD state VARCHAR(50);

UPDATE employees SET phone_number='08011112222', state='Lagos' WHERE employee_id=1;
UPDATE employees SET phone_number='08033334444', state='Oyo' WHERE employee_id=2;
UPDATE employees SET phone_number='08055556666', state='Abuja' WHERE employee_id=3;
UPDATE employees SET phone_number='08077778888', state='Osun' WHERE employee_id=4;

-- Create customers table
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    customer_name VARCHAR(50)
);

-- Create orders table
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT,
    order_date DATE,
    amount DECIMAL(10,2),
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
);

-- Insert customers
INSERT INTO customers VALUES
(1, 'Ishola'),
(2, 'Adetola'),
(3, 'Sikiru');

-- Insert orders
INSERT INTO orders VALUES
(1, 1, '2023-05-12', 1200),
(2, 2, '2023-11-07', 3000),
(3, 3, '2023-11-09', 4500);

-- INNER JOIN
SELECT o.order_id, c.customer_name, o.order_date, o.amount
FROM orders o
INNER JOIN customers c
ON o.customer_id = c.customer_id;

-- LEFT JOIN
SELECT c.customer_name, o.order_id, o.amount
FROM customers c
LEFT JOIN orders o
ON c.customer_id = o.customer_id;

-- DAY 5 - DAY 5 – Grouping & Views

-- Create sales table
CREATE TABLE sales (
    sale_id INT PRIMARY KEY,
    salesperson VARCHAR(50),
    amount DECIMAL(10,2)
);

-- Insert sales data
INSERT INTO sales VALUES
(1, 'Ade', 800),
(2, 'Ade', 600),
(3, 'Bisi', 1200),
(4, 'Bisi', 900),
(5, 'Kunle', 1500);

-- Group and filter sales above 1000
SELECT salesperson, SUM(amount) AS total_sales
FROM sales
GROUP BY salesperson
HAVING SUM(amount) > 1000;

-- Create a view for high-performing salespersons
CREATE VIEW top_salespersons AS
SELECT salesperson, SUM(amount) AS total_sales
FROM sales
GROUP BY salesperson
HAVING SUM(amount) > 1000;

SELECT * FROM top_salespersons;

