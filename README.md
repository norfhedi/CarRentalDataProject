# Car Rental Management System Database 🚗💨

A relational database project designed for a nationwide car rental agency to manage fleet inventory, agency branches, customer records, employee processing, and active rental transactions.

---

## 📌 Project Overview

This project models the database requirements for a vehicle rental business. It covers the full lifecycle of database creation—from conceptual modeling (ER Diagram) and relational schema design to SQL implementation (DDL) and operational analytics queries (DML).

### Key Features
* **Fleet Tracking:** Assign vehicles to origin branches and track mileage, vehicle make, model, and year.
* **Rental Operations:** Record rental duration, total cost, fuel level on return, and vehicle damage notes.
* **Customer & Employee Management:** Maintain unique driver's licenses, contact information, and employee job roles.
* **Branch Locations:** Organize operations across multiple physical agency branches.

---

## 📐 ER Diagram & Relational Schema

### Entity Relationships
* **Branch OWNS Car:** 1-to-N (One branch owns multiple cars)
* **Branch PICKED UP AT Rental:** 1-to-N (One branch handles pickup for multiple rentals)
* **Customer RENTS Rental:** 1-to-N (One customer can create multiple rental bookings)
* **Employee PROCESSES Rental:** 1-to-N (One employee can process multiple rental agreements)
* **Car INVOLVED IN Rental:** 1-to-N (One car can be rented multiple times)

### Relational Schema

```text
Branch   (BranchID [PK], Name, LocationCity, LocationAddress)
Car      (Vin [PK], Make, Model, Year, Mileage, BranchID [FK])
Customer (LicenseNb [PK], Name, Email, Phone)
Employee (EmployeeID [PK], Name, Job_Title)
Rental   (RentalID [PK], Rental_Date, Return_Date, Fuel_Qty, Total_Cost, Notes, 
          Vin [FK], LicenseNb [FK], BranchID [FK], EmployeeID [FK])
