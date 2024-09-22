CustomBikes S.A. Database
This repository contains the CustomBikes S.A. database design, which was developed to manage the business logic of a customizable bicycle manufacturing company. The database is structured to efficiently handle customer orders, bicycle customization, component management, technician assignment, payment tracking, and post-sale warranty management.

Features
Flexible Customization: The database supports a wide range of bicycle customization options, from frame type and wheels to specific components and materials.
Order Management: Efficiently track orders from initial component selection to final delivery, ensuring timely completion.
Technician Assignment: Orders can be assigned to one or more technicians, ensuring that the assembly process is well-managed.
Discount System: Supports both component-specific and order-wide discounts through the use of promotional codes.
Warranty Tracking: Comprehensive management of warranties, including details of coverage, start and end dates, and warranty conditions.
Data Analysis: Generate reports on popular components, technician performance, and order history, providing valuable insights for strategic decision-making.
Database Structure
Entities:
Persona (supertipo):
General entity for individuals associated with the system, including Client and Technician.
Client (subtype):
Information about customers who place orders.
Technician (subtype):
Information about technicians responsible for assembling bicycles.
Order:
Tracks details of customer orders, assigned technicians, and expected delivery times.
Bicycle:
Stores information about each custom bicycle linked to an order.
Components:
Manages the parts used for building bicycles (frame, wheels, gears, etc.).
Warranty:
Handles the details of warranties for each completed bicycle order.
Transaction:
Tracks payment information, including payment status and amount paid.
Discounts:
Manages promotional discounts that can be applied at the component or order level.
Relationships:
1:1 relationship between Order and Client.
M
relationship between Order and Technician through an intermediary table technician_order.
M
relationship between Order and Components via the quotation_component table.
1:1 relationship between Bicycle and Warranty.
Normalization
The database has been normalized to the Third Normal Form (3NF) to ensure data integrity and eliminate redundancy. Key attributes shared between clients and technicians have been abstracted into the Persona entity to reduce duplication of data.

Setup
To set up the database on your local machine, follow these steps:

Clone this repository:

bash
Copiar código
git clone https://github.com/your-username/custombikes-db.git
Import the provided SQL script into your preferred database management system (e.g., MySQL, PostgreSQL, SQLite):

bash
Copiar código
mysql -u your_username -p your_database < custombikes.sql
Modify the connection settings to match your environment.

Usage
The database can be queried and managed using standard SQL. Below are some example queries to get started:

List all active warranties:

sql
Copiar código
SELECT * FROM Warranty WHERE status = 'active';
Get all orders from a specific customer:

sql
Copiar código
SELECT * FROM Order WHERE client_id = '12345678';
Get a list of technicians assigned to a specific order:

sql
Copiar código
SELECT t.name 
FROM Technician t
JOIN technician_order to ON t.rut_id = to.id_technician
WHERE to.id_order = '456';
Contributing
If you wish to contribute to this project, please follow these steps:

Fork the repository.
Create a new branch for your feature or bugfix:
bash
Copiar código
git checkout -b feature-name
Commit your changes:
bash
Copiar código
git commit -m "Add feature description"
Push to your branch:
bash
Copiar código
git push origin feature-name
Open a pull request.
License
This project is licensed under the MIT License - see the LICENSE file for details.
