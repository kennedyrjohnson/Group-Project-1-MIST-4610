# Car Dealership Management System

# Team Members:
1. Alexandra DiClemente, @akd27602
2. Chris Johnson, @cjohns417
3. Mckenna Isenberg, @mckennaisen
4. Kennedy Johnson, @kennedyrjohnson
5. Charlie Matthews, @2004matthews

# Project Overview

The Car Dealership Management System is designed to manage all aspects of a car dealership, including car sales, services, warranties, and customer interactions. This system aims to streamline dealership operations, enhance customer satisfaction, and provide valuable insights through reporting and analytics.

Objectives
1. Sales Management
Track car sales, including customer details and salesperson information.
Record details of transactions, allowing easy monitoring of sales performance.
2. Service Management
Maintain service records for cars, including types of services performed and associated costs.
Track service histories to ensure efficient service and customer satisfaction.
3. Warranty Management
Manage warranty details for each car sold, including warranty start and end dates.
Easily view warranty coverage for vehicles and monitor warranty expirations.
4. Customer Management
Store and manage customer information, including contact details, purchase history, and preferences.
Enhance dealership's marketing efforts and provide better service through personalized interactions.
5. Reporting and Analytics
Generate insights into sales performance, service costs, and warranty coverage.
Provide detailed reports on car sales, services, and warranties to help inform business decisions and improve operations.
Features
User-friendly interface for managing car sales, services, and warranties.
Secure data storage and management of sensitive customer and transaction information.
Real-time reporting to monitor dealership performance and optimize operations.

# Project Scenario Description:
The database we chose to model is a car dealership. The purpose of this database is to manage the interactions between customers, salespeople, cars, and services offered by a car dealership. The dealership can track the cars available in inventory by storing details like mileage and VIN. The dealership sells various car makes and models to customers, with each sale sold by unique salespeople. The database stores customer details such as their purchase history and salesperson their transaction was with. Each sale must link to a customer and the corresponding salesperson. In addition to sales, repair services are tracked in the database. The database stores service details such as the specific car the service was linked to, service type, and cost. Our system enables us to better manage customers, sales, and car services to ensure the dealership operates efficiently.

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

![Screenshot 2024-10-21 162922](https://github.com/user-attachments/assets/ec63bc46-6cd4-4cf1-be1d-b5273d83885e)



# Simple Query #1
![Screenshot 2024-10-21 160602](https://github.com/user-attachments/assets/f947c81d-fdee-416a-a5b9-d7c9d4407104)

How many cars did we sell? Here, we are counting the total number of cars sold by counting the 'SaleID' column in the 'Sale' table. The output will give us a single value representing the total number of sales transactions. This type of data is critical for reporting purposes, as it provides a quick and clear insight into overall sales performance. It could be used in sales forecasts or to measure success during specific periods.


# Simple Query #2
![Screenshot 2024-10-21 161122](https://github.com/user-attachments/assets/5d53cb26-2efe-4732-a2c0-4f98cdf8e1e5)

What is the average cost of services performed? This query calculates the average cost of services performed by taking the 'ServiceCost' field from the 'Service' table. The result will give us the average service price, which is valuable for understanding the pricing trends within the business. This can inform pricing strategies, help identify if services are priced competitively, or if they should be adjusted to match market demand.


# Simple Query #3
![Screenshot 2024-10-21 161533](https://github.com/user-attachments/assets/14686383-8189-4933-b424-645a87abea02)

How many customers are in our database? This query counts the total number of customers in the database, including those who have purchased a vehicle and those who have utilized our vehicle service.


# Simple Query #4
![Screenshot 2024-10-21 161736](https://github.com/user-attachments/assets/1f97d9ed-3e2d-4a90-be5f-780116266c9f)

Show me the count of cars by their manufacturing year? This query shows the count of cars manufactured in each year by grouping them based on their 'Year' of manufacturing. For each distinct year, the query counts the number of cars using 'CarID' and displays it as 'CarCount.' The output table helps us understand the distribution of cars across different manufacturing years. This is particularly useful for tracking production trends over time, identifying which years had higher or lower car production, or even analyzing patterns that could inform supply chain or inventory decisions.


# Complex Query #5
![Screenshot 2024-10-21 161921](https://github.com/user-attachments/assets/8fdc5988-1796-4054-a83c-e97a7ccfcb55)

Can you show the total sales amount for each salesperson, along with the number of cars they've sold? Here we are able to look at the person selling the car, how much they made in sales, and how many cars they sold. We can use this information to make managerial decisions such as bonuses for the employees who have sold the most cars. 


# Complex Query #6
![Screenshot 2024-10-21 162154](https://github.com/user-attachments/assets/4b8b858a-77ad-4069-968c-5a33830d24de)

Report each customer and the cars they've purchased including the sales price, make, and model. This query is used to determine customer names and the details of the car or cars that they purchased. This is done by joining the customer and sale table to give in depth details about the sale itself, and which customer made the purchase. This can be used to get a better understanding of what certain customers have done in the past for potential future sales opportunities.


# Complex Query #7
![Screenshot 2024-10-21 162340](https://github.com/user-attachments/assets/3e06862a-9c24-425e-b400-b302f6626a4d)

List the cars along with their warranty details, including start and end dates, and warranty types. The query aims to provide a detailed list of cars, including their warranty information such as start and end dates and the type of warranty. This information can assist in customer service, inventory management, and sales strategies.


# Complex Query #8
![Screenshot 2024-10-21 162516](https://github.com/user-attachments/assets/0dd1a40b-ec41-44aa-a7de-12760fa2e220)

How many services have been completed by each salesperson, and what is the total service cost attributed to each? This query shows us each salesperson’s contributions along with the service cost attributed by them. This is useful for tracking performance and revenue generated, which can be important for making compensation decisions regarding employees and identifying high performing individuals on the back end side of the business. 


# Complex Query #9
![Screenshot 2024-10-21 162708](https://github.com/user-attachments/assets/8ebded49-36fc-4629-996f-b1a20f682904)

Which cars have been sold that have an active warranty? This is useful information for the dealership so they can monitor when warranties will expire and how well salespeople are doing on selling warranties to customers.  


# Complex Query #10
![Screenshot 2024-10-21 162812](https://github.com/user-attachments/assets/a79d918b-904c-4128-8adc-7c4ae1657474)

What is the average sale price of cars sold by each salesperson? This query calculates the average sale price of cars sold by each salesperson, providing insights into individual sales performance. This information can help management evaluate the effectiveness of sales strategies and identify top-performing salespeople.




# Database Information:

Name of the database: ha_chj41761

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Q1();

