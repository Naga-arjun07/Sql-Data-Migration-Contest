# SQL Data Migration Contest – Customer Migration

This repository contains the solution for the **Data Migration Contest (Customer Data Migration)** using **Microsoft SQL Server (T-SQL)**.

## 📌 Problem Statement
The company is moving its customer and personal details into a new consolidated system.  
We need to migrate customer data into a new table `CustomerMigration` in the **AdventureWorks** database.

## ⚙️ Features Implemented
- Created `CustomerMigration` table with constraints
- Applied transformations:
  - FullName = FirstName + LastName
  - LoginName = Extracted before '@' in Email
  - CustomerJoinedDate = ModifiedDate from Person.Person
  - YearsOfExperience = difference in years between Joined Date and today
- Enforced constraints: Primary Key, Unique LoginName & Email
- Default value for `CreatedDate`
- Non-clustered index on `LoginName`
- Transaction handling with rollback on error
- Stored Procedure for reusable migration

## 🚀 Usage
1. Clone this repo
2. Open **SQL Server Management Studio (SSMS)**
3. Connect to your `AdventureWorks` database
4. Run the scripts in order:
   - `scripts/01_create_table.sql`
   - `scripts/02_stored_procedure.sql`
   - `scripts/03_execute_migration.sql`
5. Verify data:
   ```sql
   SELECT * FROM CustomerMigration;
