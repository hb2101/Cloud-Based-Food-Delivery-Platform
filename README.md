# Cloud-Based Food Delivery Platform

A scalable and cloud-native food delivery platform built using **Next.js**, **AWS Amplify**, and a modular microservices backend. This project simulates a full-stack online food ordering system with features for users, restaurants, delivery drivers, and admins.

---

## Architecture Overview

```
                         +-----------------------+
                         |     Frontend (Next.js)|
                         +-----------+-----------+
                                     |
                                     v
                       +-----------------------------+
                       |     API Gateway / Amplify   |
                       +-----------------------------+
                                     |
               +---------------------+----------------------+
               |                                            |
       +---------------+                          +---------------------+
       |  Auth Service |                          |   Restaurant Service |
       +---------------+                          +---------------------+
               |                                            |
       +---------------+                          +---------------------+
       |  Order Service |<----------------------->|  Delivery Service   |
       +---------------+                          +---------------------+
                                     |
                         +-----------------------------+
                         |     DynamoDB / OpenSearch   |
                         +-----------------------------+
```

---

## Features

- Browse restaurants and menus
- Add items to cart and place orders
- Real-time delivery tracking
- Location-based restaurant discovery
- Authentication and authorization for users, drivers, and admins
- Modular microservices integration using AWS

---

## Tech Stack

- **Frontend**: Next.js, TypeScript, TailwindCSS
- **Backend**: AWS Lambda, API Gateway, DynamoDB, OpenSearch, Step Functions
- **Authentication**: AWS Cognito / OIDC Provider
- **Deployment**: AWS Amplify, CloudFormation, Docker (optional)

---

## Project Structure

```
Cloud-Based-Food-Delivery-Platform/
├── amplify.yml                # Amplify deployment config
├── frontend/                  # Next.js frontend
│   ├── app/                   # App routes (e.g. /restaurants, /orders)
│   ├── components/            # Shared UI components (Navbar, LoginButton, etc.)
│   ├── globals.css            # Global styles
│   ├── layout.tsx             # Root layout component
│   └── oidc-provider.tsx      # OIDC-based auth logic
├── backend/                   # (Assumed) Lambda/API source (if separate)
└── README.md
```

---

## Setup Instructions

### Prerequisites

- Node.js (v18+)
- AWS CLI configured with access
- Amplify CLI (`npm install -g @aws-amplify/cli`)

### Run Locally

```bash
cd frontend
npm install
npm run dev
```

Visit: `http://localhost:3000`

---

## Deployment

This project is configured for AWS Amplify. To deploy:

```bash
amplify init
amplify push
```

For CI/CD, refer to `amplify.yml`.

---

## Future Enhancements

- Add payment gateway (Stripe or Razorpay)
- Notification system with SES or SNS
- Admin dashboard for managing users and orders
- Integrate route optimization for deliveries

---

## License

MIT License. See `LICENSE` for details.
