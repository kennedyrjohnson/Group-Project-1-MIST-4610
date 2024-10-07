# Group-Project-1-MIST-4610
Car Dealership Management System, Group 6

# Team Members:
1. Alexandra DiClemente, @akd27602
2. Chris Johnson,
3. Mckenna Isenberg,
4. Kennedy Johnson,
5. Charlie Matthews,

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






