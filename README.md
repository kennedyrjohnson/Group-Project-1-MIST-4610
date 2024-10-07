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
    Customer: stores customer information
        - CustomerID (PK), name, phone, and email
    Saleperson: stores details about salesman working at the dealership
        - SalesmanID (PK), name, phone, and email
    Car: stores information about available cars at the dealership 
        - CarID (PK), make, model, year, milage, VIN, and salesmanID (FK)
    Sale: stores details about car sale transactions
        - SaleID (PK), saleDate, salePrice, customerID (FK), salesmanID (FK), and carID (FK)
    Service: stores details about services performed on a car either before or after it has been sold
        - ServiceID (PK), serviceDate, serviceType, serviceCost, salesmanID (FK), and carID (FK)
    Dealership: shows where the car sales occur
        - Dealership_ID (PK), Dealership_city (PK), Dealership_state (PK)
    Warranty: represents the warranty information associated with each car
        - Warranty_ID (PK), Start_Date, End_Date, Warranty_Type, CarID (FK), SalesmanID (FK)

Relationships:
    One-to-One: Sale to Car
    One-to-Many: Sale to Car, Customer to Sale, Car to Service, Salesperson to Dealership, Dealership to Sale
    Many-to-One: Sale to Salesperson, Car to Warranty, Service to Salesperson

<img width="519" alt="thumbnail_image" src="https://github.com/user-attachments/assets/83afa553-c69c-4ef4-a376-f932fb3fa071">

