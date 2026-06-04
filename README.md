# NPOS — Business Operating Platform

NPOS is a business operating platform designed for food and retail businesses.

The platform centralizes sales operations, inventory management, purchasing, finance, employee management, asset tracking, and marketplace integrations into a unified ecosystem.

Rather than functioning solely as a Point of Sale system, NPOS serves as an operational backbone for managing day-to-day business activities across multiple stores and branches.

---

## Overview

NPOS was built to solve a common problem faced by growing businesses:

Operational data is often scattered across multiple disconnected systems.

Sales are recorded in one application, inventory is managed in spreadsheets, financial records are tracked separately, and employee data is stored elsewhere.

NPOS brings these business functions together into a single platform.

---

## Core Business Domains

### Sales Management

* Point of Sale
* Order Processing
* Customer Management
* Product Management
* Voucher Management
* Promotions
* Bundle Products
* Product Options

### Inventory Management

* Ingredient Management
* Stock Tracking
* Stock Movement History
* Stock Opname
* Bulk Opname
* Waste Tracking
* Recipe Management

### Purchasing Management

* Purchase Orders
* Supplier Purchasing
* Product Returns

### Financial Management

* Financial Accounts
* Cash Transactions
* Internal Transfers
* Loan Management
* Expense Management
* Bills & Liabilities

### Human Resource Management

* Employee Management
* Attendance Tracking
* Employee Face Registration

### Asset Management

* Asset Registration
* Asset Payments
* Asset Depreciation Tracking

### Platform Management

* Multi-Store Management
* Multi-Branch Management
* User & Role Management
* Access Control

### External Platform Integration

- Designed integration layer for third-party ordering platforms
- Integration was deprioritized due to API access policy changes
- Architecture remains extensible for future integrations

---

## System Architecture

The platform consists of multiple applications working together.

### Mobile POS

Used by cashiers and store operators.

Responsibilities:

* Product browsing
* Cart management
* Checkout
* Order processing
* Receipt printing

Technology:

* Flutter

### Backend API

Acts as the central business layer.

Responsibilities:

* Authentication
* Business Rules
* Inventory Processing
* Financial Processing
* Reporting
* Marketplace Integration

Technology:

* Node.js
* Express.js
* MySQL

### Admin Console

Used by administrators and business owners.

Responsibilities:

* Dashboard Reporting
* Product Management
* Inventory Monitoring
* Financial Monitoring
* Employee Management

Technology:

* React.js
* TypeScript

---

## Multi-Tenant Architecture

NPOS is designed to support multiple stores and branches.

Store
└── Branches
├── Products
├── Orders
├── Inventory
├── Employees
└── Financial Records

This architecture enables businesses to manage multiple operational locations while maintaining centralized oversight.

---

## Key Technical Challenges

### Unified Business Platform

Building a system capable of handling operational workflows across multiple business domains.

### Inventory Accuracy

Maintaining inventory consistency through stock movement tracking and automated updates from operational activities.

### Financial Visibility

Providing consolidated reporting across sales, expenses, loans, transfers, and operational costs.

### Scalability

Designing a data model capable of supporting multiple stores, branches, users, and operational records.

---

## Infrastructure

* Ubuntu Server
* NGINX
* Systemd
* CI/CD Pipeline
* VPS Deployment
* MySQL Database

---

## My Role

I designed and developed the platform architecture, backend services, frontend applications, database structure, deployment workflow, and operational modules.

Responsibilities included:

* System Architecture
* Database Design
* Backend Development
* Frontend Development
* Mobile Development
* DevOps & Deployment
* Reporting Architecture
* Business Process Design

---

## Project Status

Private Production Project

Source code is private.

Architecture, documentation, and screenshots are provided for portfolio purposes.


```md
## Architecture Diagram

See the system architecture here:

[View System Architecture](./diagrams/system-architecture.md)