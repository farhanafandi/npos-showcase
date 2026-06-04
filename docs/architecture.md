# NPOS Architecture

## Introduction

NPOS is a business operating platform designed to centralize operational workflows for food and retail businesses.

The system combines Point of Sale, Inventory Management, Purchasing, Financial Tracking, Employee Management, Asset Management, and Marketplace Integration into a unified platform.

The architecture is designed around a multi-tenant structure, allowing businesses to manage multiple stores and branches while maintaining centralized visibility and control.

---

# Architectural Principles

The platform was designed around several key principles:

### Single Source of Truth

Operational data should exist in one place and be shared across all modules.

### Multi-Branch Support

Every business location should operate independently while remaining connected to a centralized system.

### Domain Separation

Business concerns are separated into dedicated operational domains.

### Scalability

The platform should be capable of supporting multiple stores, branches, users, and high transaction volumes.

### API-First Design

All applications communicate through centralized backend services.

---

# System Components

## Mobile POS Application

Used by cashiers and store operators.

Responsibilities:

* Product browsing
* Cart management
* Order creation
* Payment processing
* Receipt printing

Technology:

* Flutter

---

## Backend Services

Acts as the central business layer.

Responsibilities:

* Authentication
* Authorization
* Order Processing
* Inventory Processing
* Financial Processing
* Reporting
* Marketplace Integration

Technology:

* Node.js
* Express.js
* MySQL

---

## Admin Console

Used by business owners and administrators.

Responsibilities:

* Product Management
* Inventory Management
* Financial Monitoring
* Employee Management
* Reporting Dashboard
* System Configuration

Technology:

* React.js
* TypeScript

---

# High-Level Architecture

```text
                     +-------------------+
                     |  Admin Console    |
                     |      React.js     |
                     +---------+---------+
                               |
                               v

+----------------+    +-------------------+    +----------------+
| Mobile POS App | -> |   Backend API     | <- | Marketplace    |
|    Flutter     |    | Node.js / Express |    | Integrations   |
+----------------+    +---------+---------+    +----------------+
                                |
                                v

                     +-------------------+
                     |      MySQL        |
                     |     Database      |
                     +-------------------+
```

---

# Domain Architecture

The platform is organized into multiple business domains.

## Sales Domain

Responsible for revenue-generating activities.

Core Entities:

* Orders
* Products
* Product Categories
* Product Options
* Bundles
* Customers
* Promotions
* Vouchers

Responsibilities:

* Product catalog management
* Sales processing
* Discount application
* Customer transactions

---

## Inventory Domain

Responsible for stock control and material tracking.

Core Entities:

* Ingredients
* Ingredient Stocks
* Ingredient Stock Flows
* Stock Opnames
* Bulk Opnames
* Wastes
* Product Recipes

Responsibilities:

* Stock tracking
* Inventory adjustments
* Recipe costing
* Waste monitoring

---

## Purchasing Domain

Responsible for procurement activities.

Core Entities:

* Purchasings
* Returns

Responsibilities:

* Supplier purchasing
* Cost tracking
* Return processing

---

## Financial Domain

Responsible for financial visibility and cash flow management.

Core Entities:

* Finance Accounts
* Finance Transfers
* Finance Loans
* Finance Cash Transactions
* Bills
* Expenses

Responsibilities:

* Cash flow tracking
* Loan management
* Expense tracking
* Financial reporting

---

## Human Resource Domain

Responsible for workforce management.

Core Entities:

* Employees
* Employee Attendances
* Employee Faces

Responsibilities:

* Employee records
* Attendance tracking
* Workforce monitoring

---

## Asset Management Domain

Responsible for long-term asset tracking.

Core Entities:

* Assets
* Asset Payments
* Asset Depreciation Logs

Responsibilities:

* Asset registration
* Depreciation calculation
* Asset lifecycle monitoring

---

# Multi-Tenant Design

The platform supports multiple business entities through Store and Branch separation.

```text
Store
│
├── Branch A
│   ├── Orders
│   ├── Inventory
│   ├── Employees
│   └── Finance
│
├── Branch B
│   ├── Orders
│   ├── Inventory
│   ├── Employees
│   └── Finance
│
└── Branch C
```

Most operational entities are scoped by:

* store_id
* branch_id

This design enables operational isolation while maintaining centralized reporting.

---

# Reporting Architecture

Reporting data is generated from transactional records.

Metrics include:

* Total Revenue
* Total Orders
* Net Income
* Total Expenses
* Gross Margin
* Inventory Valuation

Aggregation logic is performed on the backend to reduce client-side processing and improve dashboard performance.

---

# Security Architecture

Security measures include:

* JWT Authentication
* Role-Based Access Control
* Protected API Routes
* Session Management
* Audit Logging

The system maintains separate role structures for administrative users, merchant users, and POS users.

---

# Infrastructure

Production environment:

* Ubuntu Server
* NGINX Reverse Proxy
* Systemd Services
* CI/CD Pipeline
* MySQL Database

Deployment process:

Developer
→ Git Repository
→ CI/CD Pipeline
→ Production Server

---

# Technical Challenges

## Multi-Domain Platform

Combining sales, inventory, finance, employee management, and asset management into a unified ecosystem.

## Inventory Consistency

Maintaining stock accuracy through transactional stock movement tracking.

## Financial Visibility

Providing centralized reporting across operational and financial activities.

## External Integration Domain

Responsible for future third-party ordering and platform integrations.

Core Entities:

- Online Stores
- Access Tokens

Responsibilities:

- Store external platform configuration
- Prepare integration structure for third-party ordering channels
- Support future integrations when API access is available

Note:

Online food platform integration was deprioritized because API access became restricted to enterprise-level partners.

## Multi-Branch Operations

Supporting independent branch operations while preserving centralized management capabilities.
