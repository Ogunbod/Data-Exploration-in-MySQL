# Data-Exploration-in-MySQL
Sales Data Management System

### Description
This project involves creating a MySQL database for a Sales Data Management System. The system should store information about sales transactions, customers, products, and sales representatives. Each sales transaction includes details such as transaction ID, transaction date, customer ID, product ID, quantity sold, and total amount. Customer information comprises customer ID, name, email, and address. Product details include product ID, name, category, and price. Sales representatives have details like representative ID, name, and contact information.

### Tasks:
Design the database schema for these entities.
Write SQL queries to perform the following actions:
- Adding a new sales transaction to the system.
- Updating the product associated with a sales transaction.
- Recording customer details for a sales transaction.
- Finding the total number of sales transactions for each product category.
- Retrieving the names of customers who made purchases in a specific month.
- Calculating the average transaction amount for a given sales representative.


## Project
``` create database Sales_Data_Management_System;
use Sales_Data_Management_System;
create table Customers (
Customer_ID int primary key not null,
Customer_Name  varchar (45) not null,
Email  varchar (45) not null,
Address  varchar (45) not null);
insert into Customers values 
    (1001, 'John Doe', 'john@example.com', '123 Main St, City'),
    (1002, 'Jane Smith', 'jane@example.com', '456 Elm St, Town'),
    (1003, 'Michael Johnson', 'michael@example.com', '789 Oak St, Village'),
    (1004, 'Emily Brown', 'emily@example.com', '101 Pine St, Hamlet'),
    (1005, 'David Lee', 'david@example.com', '202 Maple St, Suburb'),
    (1006, 'Sarah Garcia', 'sarah@example.com', '303 Birch St, Rural'),
    (1007, 'Chris Martinez', 'chris@example.com', '404 Cedar St, Countryside'),
    (1008, 'Amanda Robinson', 'amanda@example.com', '505 Walnut St, Metropolis'),
    (1009, 'James Clark', 'james@example.com', '606 Spruce St, City'),
    (1010, 'Jessica Hall', 'jessica@example.com', '707 Oak St, Town'),
    (1011, 'Daniel White', 'daniel@example.com', '808 Elm St, Village'),
    (1012, 'Rachel Perez', 'rachel@example.com', '909 Pine St, Hamlet'),
    (1013, 'Kevin Taylor', 'kevin@example.com', '111 Maple St, Suburb'),
    (1014, 'Lauren Martinez', 'lauren@example.com', '222 Birch St, Rural'),
    (1015, 'Mark Hernandez', 'mark@example.com', '333 Cedar St, Countryside'),
    (1016, 'Rebecca Young', 'rebecca@example.com', '444 Walnut St, Metropolis'),
    (1017, 'Stephanie King', 'stephanie@example.com', '555 Spruce St, City'),
    (1018, 'Andrew Scott', 'andrew@example.com', '666 Oak St, Town'),
    (1019, 'Nicole Green', 'nicole@example.com', '777 Elm St, Village'),
    (1020, 'Brandon Hall', 'brandon@example.com', '888 Pine St, Hamlet');


create table Products (
Product_ID int primary key not null,
Product_Name  varchar (255) not null,
Category  varchar (255) not null,
Price int not null);
insert into Products values

    (2001, 'T-shirt', 'Apparel', 20.00),
    (2002, 'Jeans', 'Apparel', 40.00),
    (2003, 'Sneakers', 'Footwear', 60.00),
    (2004, 'Jacket', 'Outerwear', 80.00),
    (2005, 'Dress', 'Apparel', 50.00),
    (2006, 'Sandals', 'Footwear', 30.00),
    (2007, 'Sweatshirt', 'Apparel', 35.00),
    (2008, 'Shorts', 'Apparel', 25.00),
    (2009, 'Boots', 'Footwear', 70.00),
    (2010, 'Coat', 'Outerwear', 100.00),
    (2011, 'Blouse', 'Apparel', 45.00),
    (2012, 'Flats', 'Footwear', 40.00),
    (2013, 'Hoodie', 'Apparel', 55.00),
    (2014, 'Skirt', 'Apparel', 30.00),
    (2015, 'Socks', 'Accessories', 10.00),
    (2016, 'Scarf', 'Accessories', 20.00),
    (2017, 'Hat', 'Accessories', 15.00),
    (2018, 'Gloves', 'Accessories', 25.00),
    (2019, 'Leggings', 'Apparel', 35.00),
    (2020, 'Pants', 'Apparel', 45.00);

create table Sales_Transaction (
Transaction_ID int primary key not null,
Transaction_Date date not null,
Customer_ID int, foreign key (Customer_ID) references Customers (Customer_ID),
Product_ID int, foreign key (Product_ID) references Products (Product_ID),
Quantity_Sold int not null,
Total_Amount int not null);

INSERT INTO Sales_Transaction VALUES
    (1, '2024-03-01', 1001, 2001, 3, 45.00),
    (2, '2024-03-02', 1002, 2002, 2, 30.00),
    (3, '2024-03-03', 1003, 2003, 1, 15.00),
    (4, '2024-03-04', 1004, 2004, 4, 60.00),
    (5, '2024-03-05', 1005, 2005, 2, 30.00),
    (6, '2024-03-06', 1006, 2006, 1, 20.00),
    (7, '2024-03-07', 1007, 2007, 3, 45.00),
    (8, '2024-03-08', 1008, 2008, 2, 30.00),
    (9, '2024-03-09', 1009, 2009, 1, 15.00),
    (10, '2024-03-10', 1010, 2010, 4, 60.00),
    (11, '2024-03-11', 1011, 2011, 2, 30.00),
    (12, '2024-03-12', 1012, 2012, 1, 20.00),
    (13, '2024-03-13', 1013, 2013, 3, 45.00),
    (14, '2024-03-14', 1014, 2014, 2, 30.00),
    (15, '2024-03-15', 1015, 2015, 1, 15.00),
    (16, '2024-03-16', 1016, 2016, 4, 60.00),
    (17, '2024-03-17', 1017, 2017, 2, 30.00),
    (18, '2024-03-18', 1018, 2018, 1, 20.00),
    (19, '2024-03-19', 1019, 2019, 3, 45.00),
    (20, '2024-03-20', 1020, 2020, 2, 30.00);


create table Sales_Representatives (
Representative_ID int primary key not null,
Name  varchar (255) not null,
Contact_Information  varchar (255) not null);
insert into Sales_Representatives values
    (3001, 'Alice Johnson', 'alice@example.com, (123) 456-7890'),
    (3002, 'Bob Smith', 'bob@example.com, (234) 567-8901'),
    (3003, 'Charlie Brown', 'charlie@example.com, (345) 678-9012'),
    (3004, 'Diana Lee', 'diana@example.com, (456) 789-0123'),
    (3005, 'Ethan Taylor', 'ethan@example.com, (567) 890-1234'),
    (3006, 'Fiona Martinez', 'fiona@example.com, (678) 901-2345'),
    (3007, 'Gregory Rodriguez', 'gregory@example.com, (789) 012-3456'),
    (3008, 'Hannah Garcia', 'hannah@example.com, (890) 123-4567'),
    (3009, 'Ian Hernandez', 'ian@example.com, (901) 234-5678'),
    (3010, 'Jessica Nguyen', 'jessica@example.com, (012) 345-6789'),
    (3011, 'Kevin Kim', 'kevin@example.com, (123) 456-7890'),
    (3012, 'Linda Patel', 'linda@example.com, (234) 567-8901'),
    (3013, 'Michael Lopez', 'michael@example.com, (345) 678-9012'),
    (3014, 'Nancy Wang', 'nancy@example.com, (456) 789-0123'),
    (3015, 'Olivia Chan', 'olivia@example.com, (567) 890-1234'),
    (3016, 'Patrick Wu', 'patrick@example.com, (678) 901-2345'),
    (3017, 'Rachel Smith', 'rachel@example.com, (789) 012-3456'),
    (3018, 'Samuel Rodriguez', 'samuel@example.com, (890) 123-4567'),
    (3019, 'Tina Brown', 'tina@example.com, (901) 234-5678'),
    (3020, 'Victor Nguyen', 'victor@example.com, (012) 345-6789');
    
    select * from Sales_Transaction;
    
    #Updating the product associated with a sales transaction:
    UPDATE Sales_Transaction
SET Product_ID = 2020
WHERE Transaction_ID = 20;

 #Recording customer details for a sales transaction:

INSERT INTO Customers (Customer_ID, Customer_Name, Email, Address)
VALUES ('1021', 'Joseph Ochia', 'ochia45@gmail.com', 'ikotun Lagos');

#total number of sales transaction for each product category
SELECT p.Category, COUNT(st.Transaction_ID) AS TotalTransactions
FROM Sales_Transaction st
JOIN Products p ON st.Product_ID = p.Product_ID
GROUP BY p.Category;

#specific month
SELECT DISTINCT c.Name
FROM Customers c
JOIN Sales_Transaction st ON c.Customer_ID = st.Customer_ID
WHERE MONTH(st.Transaction_Date) = 2024-03-09;

SELECT AVG(st.Total_Amount) AS AverageTransactionAmount
FROM Sales_Transaction st
JOIN Customers c ON st.Customer_ID = c.Customer_ID
WHERE c.Representative_ID = 3020; ```
