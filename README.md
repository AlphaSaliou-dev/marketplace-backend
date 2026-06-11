# Marketplace Backend — Node.js & MongoDB

A full-scale multi-service marketplace backend covering real estate, jobs, and finance.
Built to handle complex data relationships, high-volume API workflows, and multi-role user management.

---

## Overview

This platform serves as the backend engine for a marketplace aggregating three distinct services
under one unified API. Each service has its own data model while sharing a common auth layer
and user system.

---

## Services

### Real Estate
- Property listings with geolocation filtering
- Multi-image upload support
- Advanced search (price range, location, type)

### Jobs
- Job post management for employers
- Application tracking system for candidates
- Match scoring based on candidate profile

### Finance
- Loan and investment product listings
- Application submission and status tracking
- Document upload and verification workflow

---

## Tech Stack

- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB / Mongoose
- **Auth:** JWT with role-based access (Admin, Seller, Buyer, Employer, Candidate)
- **File Storage:** Multer — local + cloud-ready
- **Payments:** Stripe integration (subscription and one-time)

---

## Project Structure

```
marketplace-backend/
├── src/
│   ├── config/
│   │   └── db.js
│   ├── modules/
│   │   ├── auth/
│   │   ├── real-estate/
│   │   │   ├── realestate.model.js
│   │   │   ├── realestate.controller.js
│   │   │   └── realestate.routes.js
│   │   ├── jobs/
│   │   │   ├── job.model.js
│   │   │   ├── job.controller.js
│   │   │   └── job.routes.js
│   │   └── finance/
│   │       ├── finance.model.js
│   │       ├── finance.controller.js
│   │       └── finance.routes.js
│   ├── middlewares/
│   │   ├── auth.middleware.js
│   │   └── upload.middleware.js
│   └── utils/
│       └── apiResponse.js
├── .env.example
├── package.json
└── README.md
```

---

## Key Architecture Decisions

- **Module-based structure** — each service is fully isolated, independently scalable
- **Shared auth layer** — single JWT system across all three services
- **Unified response format** — consistent API responses regardless of the service called
- **Role-based access control** — granular permissions per user type and service

---

## Status

Currently in active development. Core architecture and all three service modules are functional.
Payment integration and admin dashboard in progress.

---

## Environment Variables

```env
PORT=3000
MONGODB_URI=mongodb://localhost:27017/marketplace
JWT_SECRET=your_secret_here
STRIPE_SECRET_KEY=your_stripe_key
CLOUDINARY_URL=your_cloudinary_url
```

---

*Built by [Alpha Saliou](https://github.com/AlphaSaliou-dev) — Backend Developer specializing in Node.js & MongoDB*
