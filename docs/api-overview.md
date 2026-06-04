# API Overview

## Introduction

NPOS uses a centralized REST API architecture.

All client applications communicate through the backend API to ensure consistent business rules, data integrity, and security.

Clients include:

* Mobile POS Application
* Admin Console
* Future Integrations

---

# API Design Principles

### Single Source of Truth

All business operations are processed by the backend.

Client applications are responsible for presentation and user interaction.

### Stateless Requests

Authentication is handled through access tokens.

Each request contains the required authentication context.

### Domain-Oriented Structure

Endpoints are grouped based on business domains.

---

# Authentication

## Login

```http
POST /auth/login
```

Purpose:

Authenticate users and issue access tokens.

---

## Refresh Session

```http
POST /auth/refresh
```

Purpose:

Renew access tokens.

---

# Product Management

## Get Products

```http
GET /products
```

Purpose:

Retrieve product catalog.

---

## Create Product

```http
POST /products
```

Purpose:

Create new products.

---

## Update Product

```http
PUT /products/:id
```

Purpose:

Update product information.

---

## Delete Product

```http
DELETE /products/:id
```

Purpose:

Remove products from the catalog.

---

# Order Management

## Create Order

```http
POST /orders
```

Purpose:

Create a sales transaction.

Typical flow:

1. Validate products
2. Validate stock
3. Calculate totals
4. Store transaction
5. Generate stock movement
6. Return order result

---

## Get Orders

```http
GET /orders
```

Purpose:

Retrieve order history.

---

## Get Order Detail

```http
GET /orders/:id
```

Purpose:

Retrieve order details.

---

# Inventory Management

## Get Stock

```http
GET /inventory
```

Purpose:

Retrieve inventory information.

---

## Stock Opname

```http
POST /stock-opname
```

Purpose:

Perform inventory adjustment.

---

## Stock Movement History

```http
GET /inventory/flows
```

Purpose:

Track inventory movement.

---

# Purchasing Management

## Create Purchasing

```http
POST /purchasings
```

Purpose:

Record purchasing activity.

---

## Get Purchasing History

```http
GET /purchasings
```

Purpose:

Retrieve purchasing records.

---

# Finance Management

## Get Accounts

```http
GET /finance/accounts
```

Purpose:

Retrieve financial accounts.

---

## Create Expense

```http
POST /expenses
```

Purpose:

Record operational expenses.

---

## Create Transfer

```http
POST /finance/transfers
```

Purpose:

Move funds between accounts.

---

# Employee Management

## Get Employees

```http
GET /employees
```

Purpose:

Retrieve employee records.

---

## Attendance

```http
POST /attendance
```

Purpose:

Record employee attendance.

---

# Reporting

## Dashboard Summary

```http
GET /dashboard
```

Purpose:

Retrieve aggregated business metrics.

Typical metrics:

* Revenue
* Orders
* Expenses
* Net Income
* Margin

---

# Security

The API applies:

* JWT Authentication
* Role-Based Access Control
* Request Validation
* Permission Checking

---

# Error Handling

Standard response structure:

```json
{
  "success": false,
  "message": "Validation failed",
  "errors": {}
}
```

Successful response:

```json
{
  "success": true,
  "message": "Request completed",
  "data": {}
}
```

---

# Future Improvements

Potential enhancements:

* API versioning
* OpenAPI / Swagger documentation
* Rate limiting
* Event-driven architecture
* Public integration APIs
