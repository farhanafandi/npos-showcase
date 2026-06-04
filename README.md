# NPOS — Point of Sale & Business Operation System

NPOS is a Point of Sale and business operation system designed for small to medium-sized food businesses.

The system helps manage daily sales, orders, inventory, branch operations, reporting, and printing workflows across multiple platforms.

## Overview

NPOS was designed as a multi-platform ecosystem consisting of:

- Mobile POS App
- Backend API
- Admin Console
- Inventory Management
- Order Management
- Reporting Dashboard
- Receipt & Kitchen Printing

## Tech Stack

### Mobile POS
- Flutter
- REST API Integration
- Local cart and checkout flow
- Printer integration

### Backend
- Node.js
- Express.js
- MySQL
- JWT Authentication
- Modular API architecture

### Admin Console
- React.js
- TypeScript
- Dashboard analytics
- Inventory and order management

### Infrastructure
- Ubuntu Server
- NGINX
- CI/CD Pipeline
- Systemd
- VPS Deployment

## Key Features

- Product and menu management
- Cart and checkout flow
- Sales order processing
- Inventory stock tracking
- Branch-based operations
- Dashboard reporting
- Receipt printing
- Multi-platform architecture

## Architecture

```mermaid
flowchart TD
    A[Mobile POS App - Flutter] --> B[Backend API - Node.js Express]
    C[Admin Console - React] --> B
    B --> D[(MySQL Database)]
    B --> E[Printer Service]
    B --> F[Reporting Module]
