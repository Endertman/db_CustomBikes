# CustomBikes S.A. Database
This repository contains the CustomBikes S.A. database design, which was developed to manage the business logic of a customizable bicycle manufacturing company. The database is structured to efficiently handle customer orders, bicycle customization, component management, technician assignment, payment tracking, and post-sale warranty management.

## Features
Flexible Customization: The database supports a wide range of bicycle customization options, from frame type and wheels to specific components and materials.
Order Management: Efficiently track orders from initial component selection to final delivery, ensuring timely completion.
Technician Assignment: Orders can be assigned to one or more technicians, ensuring that the assembly process is well-managed.
Discount System: Supports both component-specific and order-wide discounts through the use of promotional codes.
Warranty Tracking: Comprehensive management of warranties, including details of coverage, start and end dates, and warranty conditions.
Data Analysis: Generate reports on popular components, technician performance, and order history, providing valuable insights for strategic decision-making.
Database Structure
## Entities:
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
