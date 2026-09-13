# grassy.agro
# Agro-Marketplace QA Test Suite

## Overview

This repository documents a comprehensive **manual QA test case suite** designed for an early-stage startup project — an **Agro-Marketplace platform** connecting agricultural producers, buyers, and logistics providers across B2B and B2C segments.

The test suite was built directly from the product concept defined during the startup's discovery meeting, covering every core pillar of the platform: user roles and functionality, legal/security compliance, monetization logic, the technical stack, logistics, and marketing/SEO.

## Project Context

The platform's goal is to unify:
- **Producers** — list and sell agricultural goods (wholesale/retail)
- **Buyers** — search, filter, and purchase products, including via pooled "forward orders"
- **Carriers (Logistics providers)** — handle verified delivery of goods
- **Administrators** — manage verification, disputes, and platform oversight

Key differentiators: **forward purchasing** (pooling multiple producers' volumes into a single large order) and a **secured-transaction escrow model** with dispute resolution.

## Scope of Testing

A total of **134 test cases** were designed, split evenly between positive and negative scenarios, across six functional domains:

| # | Domain | Positive Cases | Negative Cases | Total |
|---|--------|:---:|:---:|:---:|
| 1 | Platform Functionality & User Roles | 15 | 15 | 30 |
| 2 | Legal & Security Aspects | 12 | 12 | 24 |
| 3 | Economic Model & Monetization | 11 | 11 | 22 |
| 4 | Technical Stack | 15 | 15 | 30 |
| 5 | Logistics | 7 | 7 | 14 |
| 6 | Marketing & Promotion | 7 | 7 | 14 |
| | **Total** | **67** | **67** | **134** |

## Test Design Approach

Each test case follows a structured format:
- **Test case** — short descriptive title
- **Steps** — reproducible execution steps
- **Expected result** — defined pass criteria
- **Status** — Pass / Fail / In Progress / Skip

### Areas covered in depth
- **Role-based access control** — registration, authentication, and authorization boundaries between Producer, Buyer, Carrier, and Admin roles
- **Search & filtering logic** — product, location, sale terms, and combined multi-filter queries
- **Transaction & escrow security** — payment gateway validation, fund-freezing/release logic, dispute resolution flows
- **Data protection & compliance** — GDPR deletion requests, encrypted payment data, user agreement versioning
- **Monetization** — subscription tiers, platform commissions, referral bonuses, forward-order pooling mechanics
- **Technical resilience** — API auth (JWT/OAuth2), input validation (XSS/SQL injection), service failover (DB/message queue outages), load handling
- **Logistics workflows** — carrier verification, delivery status tracking, address-change restrictions post-dispatch
- **Marketing infrastructure** — SEO metadata, analytics event tracking, email/push notification opt-outs

### Security-focused negative testing highlights
- SQL injection and XSS input sanitization checks
- JWT token tampering and expiration handling
- Unauthorized cross-role access attempts (e.g., Buyer trying to access Admin/Producer endpoints)
- Double-spend / double-confirmation prevention on transactions
- File upload validation (type and size restrictions)

## Tech Stack Under Test

**Frontend:** Next.js (SSR), TypeScript, Zustand, TanStack Query, Mantine, React Hook Form + Zod, Axios
**Backend:** Java 17, Spring Boot, Spring Security, Spring Data JPA, Spring AI, RabbitMQ, JWT/OAuth2, Swagger, JUnit5, Mockito
**Database:** PostgreSQL
**DevOps:** Docker, Docker Compose, AWS

## My Role

I independently designed and documented the full QA test case matrix for this project — translating early-stage product requirements and system architecture discussions into structured, executable positive and negative test scenarios covering functional, security, financial, and technical dimensions of the platform.

## Status

This is a living document; test cases are being e
