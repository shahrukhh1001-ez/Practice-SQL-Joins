Create database Eats;
Use eats;

CREATE TABLE Items (

    Item_ID INT PRIMARY KEY,

    Item_Name VARCHAR(50),

    Category VARCHAR(30),

    Price DECIMAL(10,2)

);

 

INSERT INTO Items VALUES

(101, 'Pizza', 'Food', 250),

(102, 'Burger', 'Food', 150),

(103, 'Pasta', 'Food', 200),

(104, 'Coffee', 'Beverage', 100),

(105, 'Sandwich', 'Food', 180),

(106, 'Juice', 'Beverage', 120);

 

CREATE TABLE Orders (

    Order_ID INT PRIMARY KEY,

    Customer_Name VARCHAR(50),

    Item_ID INT,

    Quantity INT,

    FOREIGN KEY (Item_ID) REFERENCES Items(Item_ID)

);

 

INSERT INTO Orders VALUES

(1, 'Ajay', 101, 2),

(2, 'Priya', 102, 3),

(3, 'Rahul', 101, 1),

(4, 'Neha', 104, 2),

(5, 'Amit', 102, 1),

(6, 'Kavita', 103, 3),

(7, 'Rohit', 101, 1),

(8, 'Anjali', 103, 2);

Select * from Orders;
Select * from Items;


Select Customer_name,Item_name from orders left join Items on Items.Item_id=Orders.Item_ID;

Select Order_ID,Customer_name,Item_name from orders left join Items on Items.Item_id=Orders.Item_ID;

Select Customer_name,Item_name,Price from orders Right join Items on Items.Item_id=Orders.Item_ID AND Price>150;

Select * from Orders 
Right join Items on Items.Item_id=Orders.Item_ID
Order by Customer_name;


Select * from Orders 
Left join Items on Items.Item_id=Orders.Item_ID
Order by Price Desc;


Select Customer_name,Item_name,Quantity from Orders 
Inner join Items on Items.Item_id=Orders.Item_ID AND Quantity >=2;

Select Customer_name, Category from Orders 
inner join Items on Items.Item_id=Orders.Item_ID AND category="Beverage";

Select Customer_name,Item_name,Price from Orders 
inner join Items on Items.Item_id=Orders.Item_ID AND price between 100 AND 200;

Select * from Orders 
left join Items on Items.Item_id=Orders.Item_ID 
order by Quantity Desc;

Select Customer_name,Item_name from Orders 
inner join Items on Items.Item_id=Orders.Item_ID AND Item_name="Pizza" or Item_name="Pasta";



