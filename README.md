# 🚗 Vehicle Rental System Dashboard

A comprehensive project featuring a live interactive frontend web dashboard alongside production-ready **Relational Database Management System (RDBMS)** scripts. This project demonstrates core database architectures, operational CRUD queries, stored procedures, and event-driven triggers.

## 🔗 Project Assets & Live Links
Live Interactive Web App:** [Launch Live Application](https://vandana457.github.io/Vehicle_Rental_System/)
Source Code Repository:** [GitHub Repository](https://github.com/vandana457/Vehicle_Rental_System)


## 💻 MySQL Command Prompt Execution Proof
As requested by our professor, the complete database schema, data modifications, and constraints have been executed natively inside the **MySQL Command Line Client**. 

Below is the verified screenshot of the tables and query executions running on the terminal server:

![MySQL Command Prompt Proof](mysql_proof.png)

---

📊 Relational Database Schema Design
The system manages and validates data relational integrity matching the following table schemas:
Vehicle** (`vehicle_id` [PK], model, type, rental_price_per_day, status)
Rental** (`rental_id` [PK], vehicle_id [FK], start_date, end_date, total_amount)
Payment** (`payment_id` [PK], rental_id [FK], amount, payment_date)
Maintenance** (`maintenance_id` [PK], vehicle_id [FK], description, status)

---

 Implemented Database Requirements & Features

 1. Core CRUD Operations (Vehicles Management)
*CREATE (Insert):** Add new vehicle records dynamically with uniquely generated primary keys.
*READ (Select):** View data streams formatted into a clean, structural grid table UI.
*UPDATE:** Modify a vehicle's fields or operational states instantly.
*DELETE:** Safely remove target entities from the active data scope.

 2. Stored Procedure Simulation (`sp_CalculateTotalRental`)
*Trigger Mechanism:** Executed via the manual "Execute Procedure" button.
*Logic:** Mimics a procedural database engine function. It fetches a transaction record, applies a mandatory **15% state luxury/processing tax** to the base rate, and updates the payment row state seamlessly.


 3. Automated Database Trigger (`trg_Vehicle_Maintenance`)
*Trigger Mechanism:** Event-driven action fired by a DML status change.
*Logic:** Fires automatically when a user marks an "Available" vehicle for "Maintenance". Without any human input, an event hook intercepts the update and instantly injects a fresh audit tracking record into the `Maintenance` table logs.


 How to Run the Project Locally

1. Running the Web UI Interface
* Simply double-click the `index.html` file to open it instantly inside any modern web browser.

 2. Running the SQL Queries in MySQL Command Prompt
1. Open your terminal/command prompt and connect to your server: `mysql -u root -p`
2. Create and switch to your project database:
```sql
   CREATE DATABASE vehicle_rental_db;
   USE vehicle_rental_db;
