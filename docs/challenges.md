# Technical Challenges

## Overview

NPOS was designed as more than a simple Point of Sale application.

The main challenge was building a business operating platform that connects sales, inventory, finance, purchasing, employees, assets, and branch operations into one system.

---

## 1. Multi-Domain System Design

### Challenge

The system needed to support multiple business areas:

* Sales
* Inventory
* Purchasing
* Finance
* Employees
* Assets
* Reporting

Each domain has different data structures and business rules.

### Solution

The system was separated into domain-based modules, allowing each business area to evolve independently while still sharing the same store and branch structure.

### Result

The platform can support wider business operations without being limited to cashier transactions only.

---

## 2. Multi-Branch Data Separation

### Challenge

A business may operate more than one branch, and each branch needs independent operational data.

For example:

* Orders
* Stock
* Employees
* Expenses
* Assets

### Solution

Most operational records are scoped using:

* `store_id`
* `branch_id`

### Result

Each branch can operate independently, while the owner can still monitor the business from a centralized system.

---

## 3. Inventory Accuracy

### Challenge

Inventory cannot simply be updated by changing a stock number directly.

Stock may change because of:

* Purchasing
* Sales
* Waste
* Stock opname
* Production
* Manual adjustment

### Solution

The system uses stock movement records to track inventory changes.

This makes stock changes easier to audit and trace.

### Result

Inventory becomes more transparent because each stock change has a source and history.

---

## 4. Product Costing

### Challenge

Food businesses need to understand product cost, not only sales revenue.

A product may consist of multiple ingredients, each with different costs.

### Solution

Recipes and ingredient data are used to calculate production cost.

### Result

The system can support better margin visibility and pricing decisions.

---

## 5. Financial Visibility

### Challenge

Sales revenue alone does not represent business health.

A business also needs to track:

* Expenses
* Bills
* Loans
* Transfers
* Cash movements
* Asset payments

### Solution

The system includes finance-related modules to track cash flow and operational costs.

### Result

The business can monitor income, expenses, and financial activities from one platform.

---

## 6. Reporting Performance

### Challenge

Dashboard data can become slow if all calculations are handled on the frontend.

### Solution

The backend handles reporting aggregation and exposes summarized data to the admin console.

### Result

The dashboard becomes easier to maintain and more scalable.

---

## 7. Local Printing Integration

### Challenge

POS systems often need to print receipts or kitchen tickets using local thermal printers.

Browser-based printing can be inconsistent depending on printer drivers and operating systems.

### Solution

A local printer service was introduced to bridge the backend/POS system with the local printer environment.

### Result

The system can support receipt and operational printing workflows more reliably.

---

## 8. External Platform Integration Constraints

### Challenge

Online food platform integration was initially planned, but API access became restricted to enterprise-level partners.

### Solution

The integration was deprioritized, but the architecture keeps an extensible structure for future third-party platform integrations.

### Result

The system remains flexible without claiming unsupported active integrations.

---

## 9. Deployment and Operations

### Challenge

The system needed to run in a production-like environment with reliable deployment and service management.

### Solution

The application was deployed using:

* Ubuntu Server
* NGINX
* Systemd
* CI/CD pipeline
* MySQL

### Result

The project demonstrates not only application development, but also deployment and operational ownership.
