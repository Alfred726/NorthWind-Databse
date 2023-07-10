### What is the total sales revenue for each shipper?
````sql
with total as(select "CompanyName", "Quantity", "UnitPrice", "Discount" 
from shippers 
join orders 
on "ShipVia" = "ShipperID"
join order_details 
on orders."OrderID" = order_details."OrderID" )

select "CompanyName", sum("Quantity" * "UnitPrice"*(1 - "Discount")) as total_rev
from total
group by 1
````

**Results**
CompanyName|total_rev|
----------|--------|
Federal Shipping  |   383406|
Speedy Express   |   348840|
United Package  |     533548|

### What are the top-selling products by quantity or revenue?
````sql
with total as(select "CompanyName", "Quantity", "UnitPrice", "Discount" 
from shippers 
join orders 
on "ShipVia" = "ShipperID"
join order_details 
on orders."OrderID" = order_details."OrderID" )

select "CompanyName", sum("Quantity" * "UnitPrice"*(1 - "Discount")) as total_rev
from total
group by 1
````

**Results**
ProductName|total_products|
----------|--------|
Côte de Blaye  |   153897|
Thüringer Rostbratwurst   |   84783|
Raclette Courdavault  |     76684|
Tarte au sucre   |   50737|
Camembert Pierrot  |     49877|	

### How does the discount affect sales revenue?
````sql
with total as(select "CompanyName", "Quantity", "UnitPrice", "Discount" 
from shippers 
join orders 
on "ShipVia" = "ShipperID"
join order_details 
on orders."OrderID" = order_details."OrderID" )

select  floor(sum("Quantity" * "UnitPrice")) as total_rev, floor(sum("Quantity" * "UnitPrice" * (1 - "Discount"))) as total_disc_rev
from total
````

**Results**
Total revenue|Total Discounted Revenue|
----------|--------|
1354458  |   1265793|
##### It can be seen that total revenue without discount is higher than total revenue with discount, hence discount affects total revenue in a negative way.

### How many orders were placed by each customer?
````sql
select "CustomerID", count(*) OrderCount
from orders
group by 1 
order by 2 desc
limit 5
````

**Results**
CustomerID|ordercount|
----------|--------|
SAVEA  |   31|
ERNSH   |   30|
QUICK  |     28|
HUNGO   |   19|
FOLKO  |     19|

### Which employee handled the most orders?
````sql
select concat("FirstName", ' ', "LastName") fullname, count(orders."OrderID") total_orders
from employees
join orders
on employees."EmployeeID" = orders."EmployeeID"
group by 1
order by 2 desc
limit 1
````

**Results**
fullname|total_orders|
----------|--------|
Margaret Peacock  |   156|

### What is the average time between order placement and shipment?
````sql
SELECT AVG("ShippedDate" - "OrderDate") AS AverageTime
FROM Orders
where "ShippedDate" is not null
````

**Results**
averagetime|
----------|
8.49  |


### How many orders were shipped to each country?
````sql
select "ShipCountry", Count(*) country_orders
from orders
group by 1
order by 2 desc
limit 5
````
**Results**
ShipCountry|Country_orders|
----------|--------|
Germany  |   122|
USA   |   122|
Brazil  |     83|
France   |   77|
UK  |     56|

### Find the average time between consecutive orders for each customer
````sql
with t1 as(SELECT "CustomerID", "OrderDate",
LAG("OrderDate") OVER (PARTITION BY "CustomerID" ORDER BY "OrderDate") AS prev_order_date
FROM Orders)
select "CustomerID", floor(AVG("OrderDate" - "prev_order_date")) avg_time
from t1
group by 1
````
**Results**
CustomerID|avg_time|
----------|--------|
ALFKI  |   45|
ANATR   |   177|
ANTON  |     71|
AROUT   |   42|
BERGS  |     33|

