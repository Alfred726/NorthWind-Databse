# NorthWind-Databse
## Introduction
In this analysis, we will delve into the Northwind dataset, which consists of multiple tables capturing information related to shippers, orders, employees, products, customers, territories, and more. By leveraging SQL queries and data analysis techniques, we aim to uncover insights, identify patterns, and derive meaningful conclusions from the data. This analysis will provide us with a deeper understanding of our business operations, customer behaviors, sales trends, and other valuable aspects

### Dataset Used

#### Shippers:
ShipperID: Unique identifier for each shipper.
CompanyName: The name of the shipping company.
Phone: Contact phone number for the shipper.

#### OrderDetails:
OrderID: Unique identifier for each order.
ProductID: Unique identifier for each product.
UnitPrice: The price of a single unit of the product.
Quantity: The quantity of the product ordered.
Discount: The discount applied to the product.

#### Orders:
OrderID: Unique identifier for each order.
CustomerID: Unique identifier for each customer.
EmployeeID: Unique identifier for each employee.
OrderDate: The date when the order was placed.
RequiredDate: The date by which the order is required.
ShippedDate: The date when the order was shipped.
ShipVia: The shipping method or company.
Freight: The shipping cost.
ShipName: The name of the recipient.
ShipAddress: The shipping address.
ShipCity: The shipping city.
ShipRegion: The shipping region.
ShipPostalCode: The postal code of the shipping address.

#### Employees:
EmployeeID: Unique identifier for each employee.
LastName: Last name of the employee.
FirstName: First name of the employee.
Title: Job title of the employee.
TitleOfCourtesy: Honorific title of the employee.
BirthDate: The birthdate of the employee.
HireDate: The date when the employee was hired.
Address: The employee's address.
City: The city where the employee resides.
Region: The region or state where the employee resides.
PostalCode: The postal code of the employee's address.
Country: The country where the employee resides.
HomePhone: The employee's contact phone number.
Extension: The extension number for the employee.
Photo: The photo or image of the employee.
Notes: Any additional notes or comments about the employee.
ReportsTo: The ID of the employee's supervisor.
PhotoPath: The file path or URL to the employee's photo.

#### Products:
ProductID: Unique identifier for each product.
ProductName: The name of the product.
SupplierID: Unique identifier for each supplier.
CategoryID: Unique identifier for each category.
QuantityPerUnit: The quantity of the product per unit.
UnitPrice: The price of a single unit of the product.
UnitsInStock: The number of units currently in stock.
UnitsOnOrder: The number of units currently on order.
RecorderLevel: The minimum stock level at which the product should be reordered.
Discontinued: Indicates whether the product has been discontinued.
ShipCountry: The country associated with shipping the product.

#### Customers:
CustomerID: Unique identifier for each customer.
CompanyName: The name of the customer's company.
ContactName: The name of the primary contact person.
ContactTitle: The title or position of the primary contact person.
Address: The customer's address.
City: The city where the customer is located.
Region: The region or state where the customer is located.
PostalCode: The postal code of the customer's location.
Country: The country where the customer is located.
Phone: The customer's contact phone number.
Fax: The customer's fax number.

#### EmployeeTerritories:
EmployeeID: Unique identifier for each employee.
TerritoryID: Unique identifier for each territory.

#### Categories:
CategoryID: Unique identifier for each category.
CategoryName: The name of the category.
Description: A description of the category.
Picture: The picture or image associated with the category.

#### Suppliers:
SupplierID: Unique identifier for each supplier.
CompanyName: The name of the supplier's company.
ContactName: The name of the contact person at the supplier's company.
ContactTitle: The title or position of the contact person.
Address: The supplier's address.
City: The city where the supplier is located.
Region: The region or state where the supplier is located.
PostalCode: The postal code of the supplier's location.
Country: The country where the supplier is located.
Phone: The supplier's contact phone number.
Fax: The supplier's fax number.
HomePage: The URL of the supplier's website.

#### CustomerCustomerDemo:
CustomerID: Unique identifier for each customer.
CustomerTypeID: Unique identifier for each customer type.

#### CustomerDemographics:
CustomerTypeID: Unique identifier for each customer type.
CustomerDesc: Description of the customer type.

#### Region:
RegionID: Unique identifier for each region.
RegionDescription: Description of the region.

#### Territories:
TerritoryID: Unique identifier for each territory.
TerritoryDescription: Description of the territory.
RegionID: The ID of the region to which the territory belongs.

### Entity Relation Diagram
![Photo](C:\Users\ALPHRED\Desktop\Northwind\NorthWind-Databse\Northwind)
