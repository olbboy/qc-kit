# 📒 TEST_CONTEXT.md (The Squad Ledger)

> **Compaction-Safe Testing Context**
> This ledger is the canonical test session briefing designed to survive context compaction.
> **Rule**: Do NOT rely on earlier chat text unless it's reflected in this ledger.

---

## Goal (incl. success criteria)
<!-- What are we trying to achieve? When is testing "done"? -->

**Test Goal**: <!-- e.g., Validate Login feature for Sprint 23 -->

**Success Criteria**:
- [ ] All P0/P1 test cases executed
- [ ] Pass rate ≥ 95%
- [ ] No open Critical/Major defects
- [ ] Coverage ≥ 90%

---

## Constraints/Assumptions
<!-- What limitations apply? What are we assuming? -->

**Constraints**:
*   <!-- e.g., No access to production database -->
*   <!-- e.g., Mobile testing limited to iOS only -->
*   <!-- e.g., Testing window: 3 days -->

**Assumptions** (mark `UNCONFIRMED` if uncertain):
*   <!-- e.g., All users have stable internet (UNCONFIRMED) -->
*   <!-- e.g., Test data is pre-seeded -->

---

## Key Decisions
<!-- Important decisions made during testing -->

*   <!-- e.g., Decided to skip Safari testing due to time constraints -->
*   <!-- e.g., Using Playwright over Cypress for better mobile support -->

---

## State

### Done
<!-- What has been completed -->
- [ ] <!-- e.g., Test Plan approved -->
- [ ] <!-- e.g., Test Environment set up -->
- [ ] <!-- e.g., Happy path tests completed -->

### Now
<!-- What is currently in progress -->
*   <!-- e.g., Running edge case tests for Login -->

### Next
<!-- What comes after current work -->
*   <!-- e.g., Security testing for Login -->
*   <!-- e.g., Performance testing -->

---

## Open Questions (mark UNCONFIRMED if needed)
<!-- Questions that need answers to proceed -->

1.  <!-- e.g., What's the expected behavior for 3 failed login attempts? (UNCONFIRMED) -->
2.  <!-- e.g., Is SSO login in scope? -->

---

## Working Set (files/ids/commands)
<!-- Active files, test IDs, or commands being used -->

**Active Test Files**:
```
tests/
├── login.spec.ts          # ← Current focus
├── checkout.spec.ts
└── payment.spec.ts
```

**Key Test IDs**:
*   TC-LOGIN-001 to TC-LOGIN-015

**Key Commands**:
```bash
npx playwright test --grep @login
npx k6 run tests/load/login.js
```

---

## Test Environment

| Environment | URL | Status |
| :--- | :--- | :---: |
| **Dev** | <!-- https://dev.example.com --> | ⚪ |
| **QA** | <!-- https://qa.example.com --> | 🟢 Active |
| **Staging** | <!-- https://staging.example.com --> | ⚪ |

**Tech Stack**:
*   Frontend: <!-- e.g., React 18 -->
*   Backend: <!-- e.g., Node.js 20 -->
*   Database: <!-- e.g., PostgreSQL 16 -->

**Test Accounts**:
| Role | Username | Password |
| :--- | :--- | :--- |
| Admin | <!-- admin@test.com --> | <!-- TestPass123! --> |
| User | <!-- user@test.com --> | <!-- TestPass123! --> |

---

## Quality Attributes (ISO 25010)

| Attribute | Priority | Target | Status |
| :--- | :---: | :--- | :---: |
| **Performance** | High | p95 < 500ms | ⚪ Not tested |
| **Security** | High | OWASP Top 10 clean | ⚪ Not tested |
| **Reliability** | Medium | 99.9% uptime | ⚪ Not tested |
| **Usability** | Medium | SUS Score > 80 | ⚪ Not tested |
| **Accessibility** | Medium | WCAG 2.1 AA | ⚪ Not tested |

---

*Last Updated: <!-- YYYY-MM-DD HH:mm -->*
*Updated By: <!-- Name/Agent -->*
