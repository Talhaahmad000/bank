# 🏦 Bank Management System (SQL Database)

A structured **Bank Management Database** designed using SQL (MySQL/MariaDB).
This project models core banking operations including customers, accounts, branches, and transactions with proper relationships and constraints.

---

## 🚀 Project Overview

This database simulates a real-world banking system by organizing data into relational tables and enforcing data integrity using **primary keys** and **foreign keys**.

---

## 🛠️ Technologies Used

* MySQL / MariaDB
* SQL (DDL & DML)
* phpMyAdmin

---

## 📂 Database Structure

### 🧾 Tables Included:

#### 1. `customer`

Stores customer personal information.

* `cust_id` (PK)
* `cust_name`
* `DOB`
* `GENDER`
* `MOB_NO`
* `CUST_ADDRESS`
* `BRANCH_CODE` (FK)

---

#### 2. `branch`

Stores bank branch details.

* `BANK_NAME`
* `BRANCH_NAME`
* `BRANCH_CODE` (PK)
* `BRANCH_ADDRESS`

---

#### 3. `account`

Stores customer account details.

* `ACCOUNT_NO` (PK)
* `ACCOUNT_TYPE`
* `BALANCE`
* `cust_id` (FK → customer)

---

#### 4. `transaction`

Stores all transactions.

* `Trans_id` (PK)
* `Trans_TYP`
* `Amount`
* `Trans_time`
* `ACCOUNT_NO` (FK → account)

---

## 🔗 Relationships

* One **branch** → Many **customers**
* One **customer** → Many **accounts**
* One **account** → Many **transactions**

---

## 🔐 Constraints Used

* Primary Keys for unique identification
* Foreign Keys to maintain relationships:

  * `account.cust_id → customer.cust_id`
  * `customer.BRANCH_CODE → branch.BRANCH_CODE`
  * `transaction.ACCOUNT_NO → account.ACCOUNT_NO`

---

## ▶️ How to Use

1. Open **phpMyAdmin** or MySQL client
2. Create a new database:

```sql
CREATE DATABASE bank;
USE bank;
```

3. Import the SQL file OR paste the script and run it.

---

## 🧠 What I Learned

* Designing relational databases
* Creating tables with constraints
* Implementing foreign key relationships
* Understanding normalization basics
* Managing real-world entities in SQL
* Writing structured SQL queries
* Debugging schema errors

---

## 💡 Future Improvements

* Add stored procedures (deposit/withdraw)
* Implement triggers for automatic updates
* Add user authentication system
* Improve data validation (constraints)
* Add indexing for performance optimization
* Create front-end integration (Python/Java/PHP)

---

## 📊 Example Queries

### Get all customers:

```sql
SELECT * FROM customer;
```

### Get all accounts with customer details:

```sql
SELECT * FROM account
JOIN customer ON account.cust_id = customer.cust_id;
```

### Get transactions of a specific account:

```sql
SELECT * FROM transaction
WHERE ACCOUNT_NO = 101;
```

---

## ⚠️ Notes

* Ensure table names are consistent (`transaction` vs `transation`)
* Foreign keys require matching data types
* Run tables in correct order (branch → customer → account → transaction)

---

## 📜 License

This project is open-source and free to use.
