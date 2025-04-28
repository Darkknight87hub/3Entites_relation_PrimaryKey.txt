# 3Entites_relation_PrimaryKey.txt

CREATE TABLE Customer (
    customer_id INT PRIMARY KEY,
    name VARCHAR(100) ,
    email VARCHAR(100) ,
    join_date DATE
);
INSERT INTO Customer (customer_id, name, email, join_date)
VALUES (1, 'ZZ1', 'zz1@gmail.com', '2025-01-10');
INSERT INTO Customer (customer_id, name, email, join_date)
VALUES (2, 'zz2', 'zz2@gmail.com', '2025-02-15');
INSERT INTO Customer (customer_id, name, email, join_date)
VALUES (3, 'zz3', 'zz3@gmail.com', '2025-03-20');
CREATE TABLE Product (
    product_id INT PRIMARY KEY,
    name VARCHAR(100),
    price FLOAT,
    stock INT
);
INSERT INTO Product (product_id, name, price, stock)
VALUES (101, 'Laptop', 75000.50, 10);
INSERT INTO Product (product_id, name, price, stock)
VALUES (102, 'Wireless Mouse', 1500.00, 50);
INSERT INTO Product (product_id, name, price, stock)
VALUES (103, 'Keyboard', 2000.00, 30);
CREATE TABLE OrderTable (
    order_id INT PRIMARY KEY,
    customer_id INT,
    product_id INT,
    quantity INT,
    order_date DATE,
    FOREIGN KEY (customer_id) REFERENCES Customer(customer_id),
    FOREIGN KEY (product_id) REFERENCES Product(product_id)
);
INSERT INTO OrderTable (order_id, customer_id, product_id, quantity, order_date)
VALUES (1001, 1, 101, 1, '2025-04-26');
INSERT INTO OrderTable (order_id, customer_id, product_id, quantity, order_date)
VALUES (1002, 2, 102, 2, '2025-04-27');
INSERT INTO OrderTable (order_id, customer_id, product_id, quantity, order_date)
VALUES (1003, 3, 103, 1, '2025-04-28');
