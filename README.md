# 🍽️ Restaurant Information System

A complete relational database system for managing a multi-cuisine restaurant, built with PostgreSQL 18.

---

## 📋 Project Overview

This database was designed and implemented as part of the **Database Management Systems I (ITEC343)** course at **Cyprus International University**. It simulates a real-world restaurant environment with full data management capabilities including meals, orders, payments, reservations and customer ratings.

---

## 🗄️ Database Structure

The system contains **14 tables:**

| Table | Description |
|-------|-------------|
| category | Meal categories |
| meal | Restaurant menu items |
| ingredient | All ingredients used in meals |
| meal_ingre | Links meals to their ingredients |
| supplier | Ingredient suppliers |
| supplier_ingredient | Links suppliers to ingredients |
| tables | Restaurant tables |
| employee | Restaurant staff |
| customer | Customer details |
| orders | Customer orders |
| order_item | Meals within each order |
| payment | Order payments |
| reservation | Table reservations |
| rate | Customer meal ratings |

---

## 🔗 Relational Model

```
category (category_id PK, name)

ingredient (ing_no PK, name, amount, unit)

supplier (supplier_id PK, name, phone, address, email, created_at)

supplier_ingredient (supplier_id PK FK → supplier, ing_no PK FK → ingredient)

tables (table_id PK, capacity, location, status)

employee (employee_id PK, name, role, phone, address, salary, hire_date)

customer (customer_id PK, name, phone, address, email, country, join_date)

meal (meal_id PK, name, price, time, category_id FK → category)

meal_ingre (meal_id PK FK → meal, ing_no PK FK → ingredient)

orders (order_id PK, date, time, tip, customer_id FK → customer, 
        employee_id FK → employee, table_id FK → tables)

order_item (order_item_id PK, quantity, order_id FK → orders, meal_id FK → meal)

payment (payment_id PK, payment_date, method, amount, order_id FK → orders)

reservation (reservation_id PK, date, time, status, 
             customer_id FK → customer, table_id FK → tables)

rate (rate_id PK, rating, comment, customer_id FK → customer, meal_id FK → meal)
```

---

## 🌍 Cuisines Available

- 🇨🇳 Chinese
- 🇮🇹 Italian
- 🇲🇽 Mexican
- 🇹🇷 Turkish
- 🇿🇼 Zimbabwean (Ndebele dishes)

---

## 📊 Database Stats

- 14 tables
- 40 meals across 5 cuisines
- 81 ingredients
- 30 customers from 15+ countries
- 10 employees
- 30 orders with payments and tips
- 15 management queries for data analysis

---

## 🛠️ Technologies Used

- PostgreSQL 18
- pgAdmin 4

---

## 📁 Repository Structure

```
restaurant-database-system/
├── restaurant_db.sql       # Complete database script (DDL + DML)
├── queries.sql             # 15 management queries
├── ER_diagram.png          # Entity Relationship Diagram
└── README.md               # Project documentation
```

---

## 🚀 How to Run

1. Install PostgreSQL 18 from [postgresql.org](https://www.postgresql.org/download)
2. Open pgAdmin 4
3. Create a new database called `restaurant_db`
4. Open Query Tool
5. Open `restaurant_db.sql` and run it
6. Open `queries.sql` to run management queries

---

## 👨‍💻 Author

**Ashley Mondela**
- 2nd Year Information Technologies Student
- Cyprus International University
- ISC2 Certified in Cybersecurity (CC)
- [LinkedIn](https://www.linkedin.com/in/ashley-mondela-b2a5a4218/)
