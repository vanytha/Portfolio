# How Payment Authorization Works in a SaaS Platform

This document explains the end-to-end flow of a **payment authorization** in a typical SaaS application — from the moment a user submits card details to the point where the system logs the result.

---
<p align="center">
  <img src="images/payment-authorization-flow.png" alt="Payment Authorization Flow" width="700"/>
</p>
## 1) User Input

The user enters payment details in the SaaS checkout UI (web or mobile).

**Typical inputs:**
- Card number, expiry date, CVV
- Cardholder name
- Billing address (optional, but common for fraud checks)
- Amount and currency
- Email / user ID (for receipts and account mapping)

**Example (UI payload concept):**
- Amount: `499.00`
- Currency: `USD`
- Payment method: `card`
- Customer ID: `cus_12345`

---
