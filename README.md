# Payment Gateway with Multi-Method Processing & Hosted Checkout

This project is a production-style payment gateway simulation inspired by platforms like Razorpay and Stripe, built to demonstrate how real-world payment systems handle secure transactions from start to finish. It allows merchants to create orders using authenticated APIs and enables customers to complete payments through a hosted checkout page supporting both UPI and card methods. The system includes proper validation such as VPA format checks, Luhn algorithm for card numbers, card network detection, expiry validation, and a structured payment lifecycle (processing → success/failed). With Dockerized deployment, PostgreSQL database design, automatic test merchant seeding, and a real-time dashboard for tracking transactions and analytics, this project showcases practical experience in building secure, scalable fintech systems and handling sensitive transaction workflows in a structured and professional way.

------------------------------------------------------------------------

## Project Overview

This project simulates a real-world payment gateway supporting:

-   UPI Payments
-   Card Payments
-   Merchant Authentication
-   Hosted Checkout
-   Merchant Dashboard
-   PostgreSQL Database
-   Dockerized Deployment

It demonstrates how modern gateways manage orders, payments, validation,
dashboards, and hosted checkout flows in a clean and modular
architecture.

------------------------------------------------------------------------

## High-Level Architecture

Merchant Dashboard (React - Port 3000) ↓ Payment API (Node.js +
Express - Port 8000) ↓ PostgreSQL Database (Port 5432) ↑ Hosted Checkout
(React - Port 3001)

------------------------------------------------------------------------

## Project Structure

```
payment-gateway/
│
├── backend/
│   ├── Dockerfile
│   ├── package.json
│   ├── package-lock.json
│   ├── tsconfig.json
│   ├── src/
│   └── dist/
│
├── frontend/
│   ├── Dockerfile
│   ├── index.html
│   ├── nginx.conf
│   ├── package.json
│   ├── package-lock.json
│   ├── vite.config.js
│   ├── src/
│   └── node_modules/
│
├── checkout-page/
│   ├── Dockerfile
│   ├── index.html
│   ├── nginx.conf
│   ├── package.json
│   ├── package-lock.json
│   ├── vite.config.js
│   ├── src/
│   └── node_modules/
│
├── docker-compose.yml
├── .env.example
└── README.md
```

------------------------------------------------------------------------

## Technology Stack

### Backend

-   Node.js
-   Express.js
-   PostgreSQL

### Frontend

-   React.js (Dashboard)
-   React.js (Hosted Checkout)

### Infrastructure

-   Docker
-   Docker Compose

------------------------------------------------------------------------

## Features

### Merchant API

-   API Key & Secret authentication
-   Merchant-specific data isolation

### Payments

-   UPI with VPA validation
-   Card payments with:
    -   Luhn Algorithm validation
    -   Network detection
    -   Expiry validation
-   Simulated success/failure rates

### Dashboard

-   View transactions
-   Payment analytics
-   API credential display

### Hosted Checkout

-   Secure payment interface
-   Real-time status updates

------------------------------------------------------------------------

## Quick Start

### Prerequisites

-   Docker
-   Docker Compose
-   Git

### Setup

    git clone <repository-url>
    cd payment-gateway
    cp .env.example .env
    docker-compose up -d

### Access Services

| Service        | URL                     |
|---------------|--------------------------|
| API           | http://localhost:8000    |
| Dashboard     | http://localhost:3000    |
| Checkout Page | http://localhost:3001    |

------------------------------------------------------------------------

## Testing Example

### Create Order

    curl -X POST http://localhost:8000/api/v1/orders -H "X-Api-Key: key_test_abc123" -H "X-Api-Secret: secret_test_xyz789" -H "Content-Type: application/json" -d '{ "amount": 50000, "currency": "INR" }'

------------------------------------------------------------------------
