### What is the total sales revenue for each shipper?
```sql
with total as(select "CompanyName", "Quantity", "UnitPrice", "Discount" 
from shippers 
join orders 
on "ShipVia" = "ShipperID"
join order_details 
on orders."OrderID" = order_details."OrderID" )

select "CompanyName", sum("Quantity" * "UnitPrice"*(1 - "Discount")) as total_rev
from total
group by 1```