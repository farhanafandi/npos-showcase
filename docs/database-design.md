# Database Design

## Overview

NPOS uses a relational database design to support operational workflows across sales, inventory, purchasing, finance, employees, assets, and multi-branch business management.

The database is designed to keep business data centralized while allowing each branch to operate independently.

---

## Multi-Tenant Structure

Most operational tables are scoped using:

* `store_id`
* `branch_id`

This allows the system to separate data between stores and branches while still supporting centralized management and reporting.

```text
Store
└── Branch
    ├── Orders
    ├── Products
    ├── Inventory
    ├── Employees
    ├── Expenses
    └── Assets
```

---

## Main Entity Groups

### Store & Branch Management

Main tables:

* `stores`
* `branches`

Purpose:

* Manage business ownership
* Support multiple branches
* Separate operational data per location

---

### Account & Access Control

Main tables:

* `account_admins`
* `account_merchants`
* `account_pos`
* `role_admins`
* `role_merchants`
* `token_admins`
* `token_merchants`
* `token_pos`

Purpose:

* Separate admin, merchant, and POS users
* Support role-based access control
* Manage authentication sessions and tokens

---

### Sales & Product Management

Main tables:

* `orders`
* `products`
* `product_categories`
* `product_options`
* `bundles`
* `customers`
* `vouchers`
* `promotions`
* `log_vouchers`

Purpose:

* Process sales transactions
* Manage product catalogs
* Support product options and bundles
* Handle discounts, vouchers, and promotions

---

### Inventory Management

Main tables:

* `ingredients`
* `ingredient_stocks`
* `ingredient_stock_flows`
* `stock_opnames`
* `bulk_opnames`
* `wastes`
* `product_recipies`
* `processed_ingredient_recipies`
* `processed_ingredient_productions`

Purpose:

* Track ingredient stock
* Record stock movement
* Support stock opname
* Track production cost
* Monitor waste

---

### Purchasing Management

Main tables:

* `purchasings`
* `return`

Purpose:

* Record purchasing activities
* Track purchase orders
* Support return workflows

---

### Finance Management

Main tables:

* `finance_accounts`
* `finance_cash_transactions`
* `finance_transfers`
* `finance_loans`
* `finance_settings`
* `bills`
* `expenses`

Purpose:

* Track cash movement
* Manage financial accounts
* Record expenses
* Track loans and bills
* Support business financial reporting

---

### Employee Management

Main tables:

* `employees`
* `employee_attendances`
* `employee_faces`

Purpose:

* Store employee data
* Track attendance
* Support face-based attendance records

---

### Asset Management

Main tables:

* `assets`
* `asset_payments`
* `asset_depreciation_logs`

Purpose:

* Track business assets
* Record asset payments
* Manage depreciation logs

---

## Key Design Decisions

### Branch-Level Data Separation

Operational records are connected to a specific branch, allowing each branch to manage independent sales, stock, employees, and financial records.

### Centralized Reporting

Although operational data is separated by branch, the system can aggregate data at store level for reporting.

### Transactional Stock Movement

Inventory changes are tracked through stock flow records instead of simply updating stock values directly.

This improves auditability and helps trace stock changes from purchasing, sales, production, adjustment, or waste.

### Domain-Oriented Schema

Tables are grouped based on business domains to keep the data model easier to reason about.

---

## Future Improvements

Potential improvements:

* Normalize several JSON-based fields into relational child tables
* Add database indexing strategy for reporting queries
* Introduce audit trail tables for critical business operations
* Add event-based stock movement processing
* Separate reporting database for analytics-heavy workloads
