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

## Business Problem

Small food businesses often manage sales, inventory, reporting, and operations manually or through disconnected tools.

NPOS was built to centralize these operations into one system, allowing the business to manage transactions, products, stock movement, and reporting more efficiently.

## My Role

I designed and developed the system architecture, backend API, frontend console, mobile POS flow, database structure, deployment workflow, and printing integration.

## Challenges Solved
- Designing a multi-platform POS ecosystem
- Handling cart, checkout, and order submission flow
- Structuring inventory and branch-based stock
- Building dashboard reporting from transactional data
- Integrating local receipt printing
- Deploying backend services on Ubuntu Server 

## Status

This project is currently used as a showcase project to demonstrate product engineering, full-stack development, and system architecture experience.

Source code is private, but architecture, screenshots, and technical documentation are provided for portfolio purposes.