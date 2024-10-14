# Group-Project-1-MIST-4610
Car Dealership Management System, Group 6

# Team Members:
1. Alexandra DiClemente, @akd27602
2. Chris Johnson, @cjohns417
3. Mckenna Isenberg, @mckennaisen
4. Kennedy Johnson,
5. Charlie Matthews, @2004matthews

# Project Scenario Description:
The database we chose to model is a car dealership. The purpose of this database is to manage the interactions between customers, salespeople, cars, and services offered by a car dealership. The dealership can track the cars available in inventory by storing details like mileage and VIN. The dealership sells various car makes and models to customers, with each sale sold by unique salespeople. The database stores customer details such as their purchase history and salesperson their transaction was with. Each sale must link to a customer and the corresponding salesperson. In addition to sales, repair services are tracked in the database. The database stores service details such as the specific car the service was linked to, service type, and cost. Our system enables us to better manage customers, sales, and car services to ensure the dealership operates efficiently. The Car Dealership Management System is designed to manage car sales, services, warranties, and customer interactions within a car dealership. This system will provide a structured approach to track transactions, monitor service histories, and maintain warranty information, ultimately enhancing operational efficiency and customer satisfaction. Sales management objectives include: track the sales of cars, including customer details and salesperson information. Service management objectives include: maintain records of services performed on cars, including service types and costs. Warranty management objectives include: manage warranty details for each car sold, including start and end dates. Customer management objectives include: store and manage customer information, allowing for better service and marketing. Reporting and analytics objectives include: provide insights into sales performance, service costs, and warranty coverage.
# Data Model:
Entities:
1. Customer: stores customer information includes CustomerID (PK), name, phone, and email
2. Saleperson: stores details about salesman working at the dealership includes SalesmanID (PK), name, phone, and email
3. Car: stores information about available cars at the dealership includes CarID (PK), make, model, year, milage, VIN, and salesmanID (FK)
4. Sale: stores details about car sale transactions includes saleID (PK), saleDate, salePrice, customerID (FK), salesmanID (FK), and carID (FK)
5. Service: stores details about services performed on a car either before or after it has been sold includes ServiceID (PK), serviceDate, serviceType, serviceCost, salesmanID (FK), and carID (FK)
6. Dealership: shows where the car sales occur includes Dealership_ID (PK), Dealership_city (PK), Dealership_state (PK)
7. Warranty: represents the warranty information associated with each car includes Warranty_ID (PK), Start_Date, End_Date, Warranty_Type, CarID (FK), SalesmanID (FK)

Relationships:
- One-to-One
    - Sale to Car (each sale is linked to a single car per transaction)
- One-to-Many
    - Sale to Car (each sale can have more than a single car sold)
    - Customer to Sale (each customer can engage in multiple sales)
    - Car to Service (each car can receive many services)
    - Salesperson to Dealership (each salesperson can be assoiated with more than one dealerships)
    - Dealership to Sale (each dealership has multiple sales)
- Many-to-One
    - Sale to Salesperson (each sale can only be made by one salesperson)
    - Car to Warranty (each car can have one warranty purchased)
    - Service to Salesperson (each service can only be made by one salesperson)

<img width="519" alt="thumbnail_image" src="https://github.com/user-attachments/assets/83afa553-c69c-4ef4-a376-f932fb3fa071">

# Data Dictionary:
Customer Table:
![Screenshot 2024-10-06 213041](https://github.com/user-attachments/assets/668c1899-a5ac-466a-9fc4-33de0ab8c83e)



Salesperson Table:

![Screenshot 2024-10-06 213123](https://github.com/user-attachments/assets/972995d6-378a-4316-9447-4aa5b94da046)



Sale Table:

![Screenshot 2024-10-06 213157](https://github.com/user-attachments/assets/1ac9cd0d-bb54-48c0-a7fb-74ef99514cbf)



Car Table:

![Screenshot 2024-10-06 213221](https://github.com/user-attachments/assets/05fc96a5-f315-4c7d-9e4e-e4126ec25318)




Dealership Table:

![Screenshot 2024-10-06 213241](https://github.com/user-attachments/assets/d96d754f-e062-41a9-8287-f0d398986ec1)




Warranty Table:

![Screenshot 2024-10-06 213323](https://github.com/user-attachments/assets/d66659ce-55ff-45e4-a27f-3bb6e225f6e1)




Service Table:

![Screenshot 2024-10-06 213347](https://github.com/user-attachments/assets/4b7259a1-fdc8-4fb8-88c2-6ec0410c2907)




# Queries:
![Screenshot 2024-10-14 150429](https://github.com/user-attachments/assets/3e9833f3-994e-4214-90b8-06e615525bc5)

1. ![Screenshot 2024-10-14 153113](https://github.com/user-attachments/assets/2be61948-41d5-45ee-a057-7a7a27da738c)
   
In this query, we are retrieving data from two tables: 'Sale' and 'Customer.' We're joining these tables on the 'CustomerID' column, which is shared between both tables. The result is a combined dataset that provides a detailed view of each sale along with the corresponding customer information. This is useful in scenarios where you need to analyze sales alongside customer demographics, such as identifying which types of customers are generating the most revenue.



3. ![Screenshot 2024-10-14 153531](https://github.com/user-attachments/assets/7cd98025-37d2-45fa-a6f3-6593f2e567e3)
   
Here, we are counting the total number of cars sold by counting the 'SaleID' column in the 'Sale' table. The output will give us a single value representing the total number of sales transactions. This type of data is critical for reporting purposes, as it provides a quick and clear insight into overall sales performance. It could be used in sales forecasts or to measure success during specific periods.


5. ![Screenshot 2024-10-14 153656](https://github.com/user-attachments/assets/abc3b8da-cab7-43cc-a774-89e0a986f7c8)
   
This query calculates the average cost of services performed by taking the 'ServiceCost' field from the 'Service' table. The result will give us the average service price, which is valuable for understanding the pricing trends within the business. This can inform pricing strategies, help identify if services are priced competitively, or if they should be adjusted to match market demand.



7. ![Screenshot 2024-10-14 154109](https://github.com/user-attachments/assets/2fe18f92-2c39-44bd-9d23-06619794c085)
   
This query shows the count of cars manufactured in each year by grouping them based on their 'Year' of manufacturing. For each distinct year, the query counts the number of cars using 'CarID' and displays it as 'CarCount.' The output table helps us understand the distribution of cars across different manufacturing years. This is particularly useful for tracking production trends over time, identifying which years had higher or lower car production, or even analyzing patterns that could inform supply chain or inventory decisions.








