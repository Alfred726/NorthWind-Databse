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

#### Results
| CompanyName | total_rev |
|---------|---------|
| Federal Shipping  | 383405.4678346074  | 
| Speedy Express  | 348839.93685880076  | 
| United Package  | 533547.6339599558  | 


