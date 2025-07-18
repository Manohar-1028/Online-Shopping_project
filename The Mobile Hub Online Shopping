CREATE DATABASE ONLINESHOPPING;
USE ONLINESHOPPING;
create table Customers(customer_id int primary key,name varchar(50),email varchar(100),city varchar(50));
 create table Products(product_id int primary key, product_name varchar(100),price decimal(10,2),stock int);
create table Orders(order_id int primary key,order_date date,total_amount decimal(10,2),
    customer_id int,foreign key(customer_id) references Customers(customer_id));
create table Order_Details(order_detail_id int primary key,
 order_id int,foreign key (order_id) references Orders(order_id),
 product_id int,foreign key (product_id) references Products(product_id), 
 quantity int);
 insert into Customers value(1,'Balaji','balaji56@gmail.com','Triplicane'),(2,'Sivaji','sivaji159@gmail.com','Chepuak'),(3,'Nivash','nivash856@gmail.com','Villupuram'),
 (4,'Anbu','anbu8795@gmail.com','Kallakurchi'),(5,'Indrajith','indrajith@gmail.com','Tenkasi'),(6,'Vinoth','@gmail.com','Tenkasi'),(7,'Babu','baburath7868@gmail.com','Tirunelveli'),
 (8,'Dhanush','dhanush7824@gmail.com','Sankarapuram'),(9,'Pandi','pandi8526@gmail.com','Viriyur'),(10,'Saravanan','saro245@gmail.com','Ulundhurpet');
  insert into products value(1001,'Vivo t2',22000,70),(1002,'Samsung S21',24000,150),(1003,'Realme 12',13999,166),(1004,'Appo reno12',27999,205),(1005,'Poco M5',11500,80),
  (1007,'Redmi 12c',14000,50),(1008,'Iphone 15pro',70000,120),(1009,'Infinix 9g',17500,86),(1010,'Asus Rog',49999,25),(1011,'IQ Z9',21999,46),(1012,'CMF',35000,56),
  (1013,'Google Pixel',65999,82),(1014,'Nothing 5g',24999,42),(1015,'Oneplus 7',17999,65);
 insert into Orders value(23,'2025-06-25',98890,1),(24,'2025-06-26',106000,2),(25,'2025-06-27',87000,3),(26,'2025-06-28',98890,4),(27,'2025-06-29',78000,5),(28,'2025-06-30',107900,6),
 (29,'2025-07-01',57999,7),(30,'2025-07-02',50000,8),(31,'2025-07-03',65000,9),(32,'2025-07-04',79000,10),(33,'2025-07-05',56000,8),(34,'2025-07-06',67000,9),
 (35,'2025-07-07',4600,7),(36,'2025-07-08',15500,5),(37,'2025-07-09',70000,1);
select*from orders;
insert into Order_Details value(001,23,1001,15),(002,24,1002,24),(003,25,1003,12),(004,26,1004,49),(005,27,1005,42),(006,28,1007,31),(007,29,1008,17),
(008,30,1009,80),(009,31,1010,69),(010,32,1011,18),(011,33,1012,45),(012,34,1013,33),(013,35,1014,76),(014,36,1015,37);   
select*from order_details;
select*from customers;
select name,city
from Customers;
select product_name,price
from products
where price>15000;
select orders.order_id,Customers.name As Customer_Name,orders.total_amount
from orders
join customers
on orders.customer_id=Customers.customer_id;
select order_id,count(*) as total_products
from order_details
group by order_id;
select sum(total_amount)as tottal_sales
from orders;
select customers.name,orders.total_amount
from orders
join customers on orders.customer_id=customers.customer_id
order by total_amount desc
limit 1;
select stock from products
where stock<38;
select order_details.order_id, products.product_name, order_details.quantity
from Order_Details
join Products on order_details.product_id = products.product_id
where order_details.order_id = 28;
select customers.name,count(orders.order_id)as total_orders
from customers
join orders on customers.customer_id=orders.customer_id
group by customers.name;
select products.product_name,sum(order_details.quantity)as total_ordered
from order_details
join products on order_details.product_id=products.product_id
group by products.Product_name
order by total_ordered desc
limit 5;
