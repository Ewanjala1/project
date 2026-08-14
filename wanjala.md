# Northstar Sprint — Assignment 1: Team Working Agreement & Board Setup

**Client:** Northstar Retail Co.  
**Pod ID:** Pod 4  
**Date:** August 10, 2026  
**Repository:** `github.com/northstar-pod-4/support-deflection-mvp`

---

## 1. Signed Team Charter

### Core Norms & Working Rules
* **Communication Channels:** All primary asynchronous communication takes place in Slack/Teams (`#northstar-pod-4`). Emergency blocker alerts are routed via WhatsApp.
* **Response Window:** Maximum **2 hours** during core sprint hours (09:00–17:00 EAT).
* **Deadline Policy:** Day 1 board setup tasks must be committed and moved to `Done` by **18:00 on Day 1**. Core feature development freezes at **12:00 on Day 4** for audit verification.
* **Escalation Path (Rule Compliance):**
  * **24 Hours Inactivity:** Pod lead issues an internal check-in ping in `#northstar-pod-4`.
  * **48 Hours Inactivity (2 Days):** Trigger formal Charter escalation to the sprint supervisor for pod re-assignment and credit adjustment.
* **Commit & Branch Conventions:**
  * **Branch Format:** `feature/<task-id>-<short-description>` (e.g., `feature/NS-102-order-status-card`).
  * **Commit Pattern:** `<type>: <what changed> - <why it matters>`.
  * **Allowed Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`.

### Team Roles & Signatures
| Member Name | Role | Primary Responsibility | Signature Status |
| :--- | :--- | :--- | :--- |
| **Dev 1 (Pod Lead)** | Frontend Lead | Chatbot UI & State Machine Parsing | Signed (EW) |
| **Dev 2** | Backend & API Lead | Mock Data & Order Lookup Handlers | Signed (MB) |
| **Dev 3** | Integration Lead | Returns & Refunds Policy Engine | Signed (AK) |
| **Dev 4** | QA & Audit Lead | Log Exports, Audit Checks & Documentation | Signed (JN) |

---

## 2. Populated Agile Project Board

> **Rule Verification:** All tasks are estimated at **≤ 4 hours**, assigned to an owner, tagged with a priority level, and given a single checkable sentence for **Definition of Done (DoD)**.

| Task ID | Task Title | Owner | Priority | Est (Hrs) | Status | Definition of Done (DoD) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **NS-101** | Create Team Charter & Repository Setup | Dev 4 | `P1` | 2.5 | `Done` | Repository README includes signed team charter and branch protection rules are active. |
| **NS-102** | Parse Chat Config JSON into State Machine | Dev 1 | `P1` | 3.5 | `Done` | `useChatEngine` hook successfully loads JSON nodes and renders initial welcome prompt. |
| **NS-103** | Build Chatbot Shell & Component Layout | Dev 1 | `P1` | 4.0 | `Done` | Front-end chat UI renders message bubbles, input fields, and action buttons without visual bugs. |
| **NS-104** | Build Mock Order Database & Seed Data | Dev 2 | `P1` | 3.0 | `Done` | Local mock database returns valid JSON records for test order IDs across all shipping states. |
| **NS-105** | Implement `/api/v1/orders/lookup` Endpoint | Dev 2 | `P1` | 3.5 | `Done` | POST request with valid Order ID returns 200 OK with tracking details, while invalid ID returns 404. |
| **NS-106** | Implement `/api/v1/returns/eligibility` Endpoint | Dev 3 | `P1` | 4.0 | `Done` | Endpoint correctly flags orders older than 30 days as `EXPIRED` and orders under 30 days as `ELIGIBLE`. |
| **NS-107** | Build Interactive Item Selection Component | Dev 3 | `P2` | 3.0 | `Done` | User can check multiple return items and submit them to generate a mock return payload. |
| **NS-108** | Implement `/api/v1/returns/generate-label` API | Dev 3 | `P2` | 2.5 | `Done` | POST request returns a mock PDF shipping label download URL and unique return tracking ID. |
| **NS-109** | Build Fallback & Human Escalation Handler | Dev 1 | `P1` | 2.5 | `Done` | Chatbot captures transcript summary and generates simulated tier-1 support ticket payload on error/request. |
| **NS-110** | End-to-End Test: Order Status Journey | Dev 4 | `P1` | 2.0 | `Done` | Complete flow from "Where is my order?" to tracking link display passes without console errors. |
| **NS-111** | End-to-End Test: Returns & Label Flow | Dev 4 | `P1` | 2.0 | `Done` | Complete flow from order return request to label download URL generation passes without errors. |
| **NS-112** | Draft 1-Page Go-Live Readiness Note | Dev 4 | `P1` | 3.5 | `Done` | Markdown document contains all 4 required sections and passes team review. |