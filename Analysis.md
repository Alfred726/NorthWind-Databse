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
Federal Shipping  |   383405.4678346074|
Speedy Express   |   348839.93685880076|
United Package  |     533547.6339599558|

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
Côte de Blaye  |   153897.1748863291|
Thüringer Rostbratwurst   |   84783.77159642408|
Raclette Courdavault  |     76683.74989898875|
Tarte au sucre   |   50737.09416846588|
Camembert Pierrot  |     49877.31995112449|	




