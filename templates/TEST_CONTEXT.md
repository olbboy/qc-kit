# 📒 TEST_CONTEXT.md (The Squad Ledger)

> **Antigravity Protocol Note**: This file serves as the **Shared Test Memory** for all 15 QC Agents.
> **Rule**: Agents MUST read this file (if it exists) at the start of every task to understand the Global Test Context.

---

## 1. Current Test Scope

**What are we testing?**
<!-- Example: Sprint 23 features, Login Module, API v2.0 -->

---

## 2. Test Environment

**Where are we testing?**

| Environment | URL/Details |
| :--- | :--- |
| **Dev** | <!-- https://dev.example.com --> |
| **Staging** | <!-- https://staging.example.com --> |
| **Production** | <!-- https://example.com --> |

**Tech Stack**:
<!-- Example: React 18, Node.js 20, PostgreSQL 16 -->

---

## 3. Test Constraints & Assumptions

**What limitations or assumptions apply?**

*   <!-- Example: No access to production database -->
*   <!-- Example: Mobile testing limited to iOS only -->
*   <!-- Example: Assume all users have stable internet -->

---

## 4. Key Quality Attributes (ISO 25010)

| Attribute | Priority | Target |
| :--- | :---: | :--- |
| **Performance** | High | p95 < 500ms |
| **Security** | High | OWASP Top 10 clean |
| **Reliability** | Medium | 99.9% uptime |
| **Usability** | Medium | SUS Score > 80 |

---

## 5. Test Accounts & Data

| Role | Username | Password |
| :--- | :--- | :--- |
| Admin | <!-- admin@test.com --> | <!-- TestPass123! --> |
| User | <!-- user@test.com --> | <!-- TestPass123! --> |

---

## 6. Open Blockers

*   <!-- Example: Payment gateway is down in staging -->
*   <!-- Example: Test data not seeded for mobile tests -->

---

## 7. Working Set (Current Focus)

**What files/features are we actively testing?**

```
src/
├── auth/          # ← Focus: Login, Registration
├── payments/      # ← Focus: Checkout flow
```

---

*Last Updated: <!-- YYYY-MM-DD -->*
