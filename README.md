# project
---
## 🏪 Inventory Management System (MySQL)

A relational database system designed to manage inventory, suppliers, product categories, and sales data. Built entirely using **MySQL**, this project demonstrates normalized table design, foreign key constraints, and query operations.

---

### 📁 Database Name

```
inventory_db
```

---

### 🗃️ Tables Included

#### 1. `Suppliers`

Stores supplier information.

| Column          | Type         | Description            |
| --------------- | ------------ | ---------------------- |
| supplier\_id    | INT (PK)     | Unique ID              |
| supplier\_name  | VARCHAR(100) | Name of the supplier   |
| contact\_number | VARCHAR(15)  | Supplier phone number  |
| email           | VARCHAR(100) | Supplier email address |

---

#### 2. `Categories`

Stores product categories.

| Column         | Type        | Description          |
| -------------- | ----------- | -------------------- |
| category\_id   | INT (PK)    | Unique ID            |
| category\_name | VARCHAR(50) | Name of the category |

---

#### 3. `Products`

Main product table with links to `Suppliers` and `Categories`.

| Column              | Type           | Description            |
| ------------------- | -------------- | ---------------------- |
| product\_id         | INT (PK)       | Unique ID              |
| product\_name       | VARCHAR(100)   | Name of the product    |
| quantity\_in\_stock | INT            | Current stock quantity |
| price               | DECIMAL(10, 2) | Product price          |
| supplier\_id        | INT (FK)       | Linked to `Suppliers`  |
| category\_id        | INT (FK)       | Linked to `Categories` |

---

#### 4. `Sales`

Tracks product sales and inventory changes.

| Column         | Type      | Description           |
| -------------- | --------- | --------------------- |
| sale\_id       | INT (PK)  | Unique sale ID        |
| product\_id    | INT (FK)  | Product sold          |
| quantity\_sold | INT       | Number of items sold  |
| sale\_date     | TIMESTAMP | Date/time of the sale |

---

### 📥 Sample Data Included

* 2 **Suppliers**
* 3 **Categories**
* 3 **Products**
* 2 **Sales records**

---

### 📊 Example Query

Returns product stock details, price, category, and supplier:

```sql
SELECT 
  p.product_name, 
  p.quantity_in_stock, 
  p.price, 
  c.category_name, 
  s.supplier_name
FROM Products p
JOIN Categories c ON p.category_id = c.category_id
JOIN Suppliers s ON p.supplier_id = s.supplier_id;
```

---

### 💡 Key Concepts Demonstrated

* Relational schema with multiple tables
* Foreign key constraints
* Data normalization
* Basic and advanced SQL queries
* Inventory tracking using sales data

---

