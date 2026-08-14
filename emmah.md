# Northstar Sprint — Assignment 2: Collaborative Delivery & Audit Log

**Client:** Northstar Retail Co.  
**Pod ID:** Pod 4  
**Date:** August 14, 2026  
**Repository:** `github.com/northstar-pod-4/support-deflection-mvp`

---

## 1. Prototype Architecture & Overview

The **Northstar Support Deflection MVP** is built to relieve support team volume by directly resolving repetitive tickets in two key categories: **Order Status** and **Returns & Refunds**.

### Core Architecture
* **State Machine Config Parser (`src/hooks/useChatEngine.js`):** Dynamically loads conversational node trees, manages input states, and controls API navigation without hardcoded UI flows.
* **Mock REST Endpoints (`src/pages/api/v1/*`):** Handles order retrieval, policy rule execution (30-day return window validation), and simulated shipping label generation.

---

## 2. Go-Live Readiness Note (1-Page)

### 1. What Works (Supported Capabilities)
* **Order Status Inquiries:**
  * **Trigger:** User inputs Order ID (e.g., `NS-98234`) and Email.
  * **Outcome:** System queries database and returns delivery status (`DELIVERED`, `IN_TRANSIT`, `PROCESSING`), shipping carrier name, and live tracking links without human intervention.
* **Returns & Refunds Inquiries:**
  * **Trigger:** User submits Order ID and Postal Code under "Start Return".
  * **Outcome:** System evaluates purchase date against the 30-day return policy rule. Eligible orders trigger interactive item selection and generate downloadable pre-paid return shipping labels.

### 2. What's Known-Broken (Limitations & Edge Cases)
* **Partial Shipments:** Orders split across multiple packages default to human escalation, as package tracking is currently mapped 1:1 per order ID.
* **Space-Sensitivity in Forms:** Input forms do not automatically trim trailing spaces, resulting in avoidable lookup failures if whitespace is present.
* **Legacy Orders:** Orders placed prior to database migration (pre-2026) are not populated in the mock dataset and route to fallback.

### 3. Operations & Handoff Instructions
* **Prerequisites:** Node.js v18+ installed.
* **Environment Configuration:** Create a `.env.local` file with the following variables:
  ```env
  NORTHSTAR_DB_URL="[https://api.northstar.internal/v1](https://api.northstar.internal/v1)"
  ZENDESK_SANDBOX_KEY="your_api_key_here"