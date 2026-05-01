# SQL-Task-3
# CodTech SQL Intenship Task-3 solutions
About Task-

![Image](https://github.com/user-attachments/assets/fa8d5667-cc8e-4aed-9e95-dd0eaa4d7ed6)

The objective of this task was to migrate data from a MySQL database to a PostgreSQL database, ensuring that the data remains intact and accurate throughout the process. The task involved exporting the structure and data from the MySQL world database, preparing a target PostgreSQL database (world_pg), and importing the data after addressing compatibility differences between the two database systems.

Through this task, I learned how to work with different database tools (MySQL Workbench and pgAdmin), understand syntax differences, handle SQL conversion challenges, and validate data integrity using row comparisons. The deliverables included migration scripts and a summary report documenting each step of the process.

# PERFORMED & SUBMITTED BY:

-- TASK PERFORMED BY: DEBADATTA ROUT

-- Intern ID : CT04DN790

-- DOMAIN: SQL

-- DURATION: 4 WEEKS

-- MENTOR: Neela Santhosh

# Task Description

As part of my 4-week internship at Codtech IT Solutions under the mentorship of Neela Santhosh, I was assigned a hands-on project in the domain of SQL. 
## 🎯 Task Objective
Migrate data from a MySQL database (`world`) to PostgreSQL (`world_pg`) while ensuring data integrity and learning the step-by-step process of cross-database migration.

# 📦 Internship Task: MySQL → PostgreSQL Data Migration 
📌 What is Data Migration?

Data migration is the process of transferring data between different storage systems, formats, or database technologies — such as from MySQL to PostgreSQL.

It involves:

Extracting data from the source system

Transforming it as needed to match the destination format or structure

Loading it into the target system (commonly known as ETL)

Data migration is essential when:

Upgrading systems

Switching database technologies

Consolidating data across platforms

Moving from on-premise to cloud environments

A successful data migration ensures:

Data accuracy (no loss or corruption)

Integrity (relationships and constraints are preserved)

Compatibility (data conforms to the rules of the new system)

In this project, migrating data from MySQL (source) to PostgreSQL (target) required addressing syntax differences, adjusting structure, and validating data to ensure a smooth transition.

## 🧭 Step-by-Step Process
# MySQL Workbench
### ✅ Step 1: Setting Up MySQL Workbench
**Tool Used**: MySQL Workbench

![Image](https://github.com/user-attachments/assets/307c94b4-ace1-4241-a7ee-e1491b53f8c7)

- Installed MySQL Workbench to manage MySQL databases.
- Connected to `Local instance MYSQL80` on port 3306.
- Confirmed server is running via Windows Services or Command Prompt using:
  ```
  net start mysql80
  ```
![Image](https://github.com/user-attachments/assets/ffa1a4a1-f2bc-48db-91d1-8d811e1d68c1)
![Image](https://github.com/user-attachments/assets/57eb61db-718d-4f6a-ad67-95cdf96355b2)

### ✅ Step 2: Export MySQL Database
**Objective**: Extract schema and data from the `world` database.
![Image](https://github.com/user-attachments/assets/f8c5ea0c-afcb-4d36-b8dd-8d4b13420334)
- Went to **Server > Data Export** in MySQL Workbench.
- Selected the `world` schema and chose:
  - "Export to Self-Contained File"
  - "Dump Structure and Data"
- Saved the exported file as `world.sql`.
  
![Image](https://github.com/user-attachments/assets/bf5d8b2b-cd79-4a9e-ba7b-397af523a1b1)
![Image](https://github.com/user-attachments/assets/864872be-326a-48bb-aaac-03fd0e26593e)
![Image](https://github.com/user-attachments/assets/e68a5407-e3d1-45cf-a63b-3b7afaa91d94)
![Image](https://github.com/user-attachments/assets/40946940-040a-4f17-a4fe-99ed47240183)
![Image](https://github.com/user-attachments/assets/5f01eb27-1e15-4b0a-b8cd-2f49100f86f7)
![Image](https://github.com/user-attachments/assets/1e838efb-b4ec-4942-8c7e-73d7364526e8)
![Image](https://github.com/user-attachments/assets/eabda6e8-1f7b-4efd-86a4-6f09b5eb2888)
![Image](https://github.com/user-attachments/assets/195d645d-1482-45d5-926b-dd0ff2e46e8d)
![Image](https://github.com/user-attachments/assets/d735c917-9aa8-4903-a9aa-30d89ce931c5)

✅ Export completed successfully with confirmation message.

---
# PostgreSQL
### ✅ Step 3: Install and Configure PostgreSQL
**Tool Used**: PostgreSQL with pgAdmin
![Image](https://github.com/user-attachments/assets/95123665-9f81-4311-814f-d92c425b5827)
- Installed PostgreSQL (default port 5432).
- Used pgAdmin for GUI access.
- Created a new server connection to `localhost` with username `postgres`.

![Image](https://github.com/user-attachments/assets/6632c99b-d165-44ea-8a1c-539345bbeefe)
---

### ✅ Step 4: Create Target PostgreSQL Database
**Database Created**: `world_pg`

- Right-clicked on "Databases" in pgAdmin → "Create" → "Database"
- Entered name: `world_pg`
- Clicked Save.

![Image](https://github.com/user-attachments/assets/9a1b7af9-e615-4396-b2d0-79b1f5bda7ee)
![Image](https://github.com/user-attachments/assets/02ee3666-c48a-4ca7-a904-70a78488b25e)
![Image](https://github.com/user-attachments/assets/62281b86-3f79-4913-a58b-cde6d1e163ff)
![Image](https://github.com/user-attachments/assets/21e1d051-db9e-4972-9a19-315337002b0a)

---

### ✅ Step 5: Importing MySQL SQL into PostgreSQL
**Problem Faced**:
- MySQL and PostgreSQL use different SQL dialects.
- PostgreSQL does not support MySQL-specific commands like:
  - `LOCK TABLES`, `SET NAMES`, backticks (`\``), and `/*! ... */`
 
![Image](https://github.com/user-attachments/assets/aec4ef15-028c-42ed-b942-bd01d8d41d79)
![Image](https://github.com/user-attachments/assets/1084acdd-8f2b-48b1-8f49-51930aca4d70)
![Image](https://github.com/user-attachments/assets/d1c53230-5dfe-4932-b996-646556d9bf76)
![Image](https://github.com/user-attachments/assets/8f7e3631-fdd1-49a8-837e-fda060e27f31)

**Solution Considered**:
- Use online tools like [SQLines](https://sqlines.com/online) or [EverSQL](https://sql-translator.eversql.com/) to convert MySQL syntax to PostgreSQL syntax.

---

### 🧹 Optional (Not Performed): SQL Cleaning
**Alternative**:
- Manually clean the SQL file to remove unsupported MySQL syntax.
- Create equivalent PostgreSQL table structure.
- Insert data using standard `INSERT INTO` commands.

---

### ✅ Data Integrity Consideration
**Best Practice**:
- Verify data by comparing row counts in both MySQL and PostgreSQL using:
  ```sql
  SELECT COUNT(*) FROM city;
  ```

---

## 📁 Files and Deliverables
- `world.sql`: Exported MySQL dump file
- `world_pg`: PostgreSQL target database (created)
- Cleaned `.sql` file (optional if manual cleaning/conversion is done)

---

## 🧠 Learnings and Key Takeaways
- MySQL and PostgreSQL, though both relational databases, require syntax-level adjustments for smooth migration.
- GUI tools like MySQL Workbench and pgAdmin simplify database operations.
- Data migration isn't just about copying data — it involves compatibility, structure validation, and integrity checks.

---

## 🔚 Conclusion
This step-by-step process helped in understanding not just how to migrate data, but also why each step is essential. With tools, methodical steps, and a few troubleshooting learnings, this task gave practical exposure to real-world database operations.



