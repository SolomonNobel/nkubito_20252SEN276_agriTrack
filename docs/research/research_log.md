Project Proposal: Cooperative Crop Input and Harvest Tracker

Student Name: NKUBITO Solomon Nobel  
Student ID: 20252SEN276  
Institution: Adventist University of Central Africa (AUCA)  
Instructor: Lecturer Eric Maniraguha  

---

1. Problem Statement & Solution

Rural agricultural cooperatives struggle with manual tracking inefficiencies when distributing subsidized inputs, monitoring crop harvests, and managing financial records. This project builds an Oracle database system to automate smallholder farmer records, input distributions, and seasonal harvest tracking. Furthermore, it incorporates automated PL/SQL business rules and an interactive analytics dashboard to provide real-time visibility into regional crop performance and inventory levels.

2. Core Keywords
* Agricultural Cooperatives
* Oracle PL/SQL
* Analytics Dashboard

3. Dataset Description
* Data Source: Kaggle Agricultural Datasets / Open-source Cooperative Records
* Key Entities & Attributes:
  * Farmers: Farmer_ID, National_ID, Full_Name, District, Cooperative_ID, Phone
  * Inputs: Input_ID, Input_Name, Category (Seed/Fertilizer), Unit_Price, Stock_Quantity
  * Distributions: Distribution_ID, Farmer_ID, Input_ID, Quantity_Allocated, Distribution_Date
  * Harvests: Harvest_ID, Farmer_ID, Crop_Type, Yield_KG, Harvest_Date, Quality_Grade
  * Transactions: Transaction_ID, Farmer_ID, Amount_Paid, Transaction_Date, Status

4. Oracle PL/SQL Technical Plan
* Normalization: Schema normalized to Third Normal Form (3NF) to maintain data integrity.
* Constraints: Primary keys, foreign keys, CHECK constraints (e.g., positive yield/quantity), and UNIQUE constraints (National ID).
* Triggers:
  1. Quota Verification Trigger: Automatically checks if an input request exceeds the maximum quota allowed per farmer before inserting into DISTRIBUTIONS.
  2. Inventory Update Trigger: Automatically decrements Stock_Quantity in INPUTS upon distribution confirmation.
* Stored Procedures & Functions: Procedures for batch harvest logging and functions for calculating seasonal payout totals per farmer.

5. Innovation Layer
An interactive Analytics Dashboard connected to the Oracle database layer (or exported analytical views) to deliver:
* Real-time metrics on seasonal fertilizer vs. seed usage across districts.
* Total harvest yield aggregation grouped by crop type and region.
* Stock alert thresholds for cooperative input inventory levels.
