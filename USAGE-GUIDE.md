# 📘 QC-Kit: The Antigravity Codex (v1.0.0)

> **"We don't just test. We think, we verify, and we prevent."**

Welcome to the **Cognitive Quality Control Squad (Antigravity Native)**.
This is not a chatbot. It is a **Multi-Agent Expert System** designated to enable **High-Assurance Quality Control** (inspired by CMMI Level 5).

---

## 🌌 The Philosophy: Three Pillars of Testing Intelligence

To master this kit, you must understand how the Squad "thinks".

### 1. 🧠 System 2 Cognition (The Brain)
Standard AI generates tests instantly (System 1). This is prone to missing edge cases.
**Our Agents Stop & Think.**
*   **Reflection Loop**: Before delivering tests, every agent critiques its own output.
*   **Tool Mandates**: They don't assume tests pass (they run them). They don't guess coverage (they use Python).

### 2. 🤝 Squad Collaboration (The Network)
Agents are no longer isolated. They form a **Collaborative Testing Network (DAG)**.
*   **Old Way**: You call `@qc-testcase`. It finishes. You wonder what's next.
*   **New Way**: `@qc-testcase` finishes and *advises you*: "Handover: Summon `@qc-automation` to script these tests."

### 3. 📒 Test Context (The Memory)
The Squad shares a "Testing Brain" via `templates/TEST_CONTEXT.md`.
*   **Problem**: "I told `@qc-testcase` we test on Chrome, but `@qc-automation` scripts for Safari."
*   **Solution**: You define the Context ONCE in the Test Context. All 15 agents read it before acting.

---

## 🚦 The Roster: 15 Specialists, One Mission

| Agent | The Archetype | When to Summon |
| :--- | :--- | :--- |
| **COMMANDER** | | |
| **`@qc-master`** | *Test Strategist* | "I'm starting a new project. Help me plan testing." |
| **DESIGN SQUAD** | | |
| **`@qc-strategy`** | *Test Architect* | "Create a test strategy for this release." |
| **`@qc-testcase`**| *Test Designer* | "Generate test cases from this User Story." |
| **`@qc-data`** | *Data Engineer* | "Generate edge case test data for email validation." |
| **EXECUTION SQUAD**| | |
| **`@qc-manual`** | *Exploratory Tester* | "Do a bug hunt on the checkout flow." |
| **`@qc-automation`**| *SDET* | "Convert these test cases to Playwright scripts." |
| **`@qc-api`** | *API Tester* | "Generate tests for this REST API endpoint." |
| **`@qc-performance`**| *Performance Engineer* | "Create a k6 load test for 1000 users." |
| **`@qc-security`** | *Security Tester* | "Audit this form for OWASP Top 10." |
| **ANALYSIS SQUAD**| | |
| **`@qc-bug`** | *Bug Reporter* | "Write a detailed bug report for this issue." |
| **`@qc-root-cause`**| *Defect Analyst* | "Why does this bug keep happening? Use 5 Whys." |
| **`@qc-metrics`** | *QA Analyst* | "Calculate our test coverage percentage." |
| **`@qc-regression`**| *Regression Guardian* | "What tests should we run after this code change?" |
| **REPORTING SQUAD**| | |
| **`@qc-report`** | *Test Reporter* | "Generate a test summary for this sprint." |
| **`@qc-review`** | *Review Facilitator* | "Review these test cases for completeness." |

---

## ⚔️ Tactical Protocols

### Protocol 1: The "Context Injection"
**Stop repeating yourself.**
1.  Copy `templates/TEST_CONTEXT.md` to your project root.
2.  Fill it out: `Scope: Login Feature`. `Environment: Chrome, Staging`.
3.  **Result**: Every agent now knows the testing context.

### Protocol 2: The "User Story → Test Suite" Chain
**Zero to automated tests in 3 steps.**
1.  `@qc-testcase Generate test cases for: "As a user, I can login with email/password."`
2.  `@qc-data Generate test data for the login tests.`
3.  `@qc-automation Convert these to Playwright TypeScript.`

### Protocol 3: The "Bug Forensics"
**Find the root cause, not just the symptom.**
1.  `@qc-bug Write a bug report for: "Checkout fails on mobile."`
2.  `@qc-root-cause Analyze this bug using 5 Whys.`
3.  `@qc-regression What tests should we add to prevent this?`

---

## 🚀 How to Begin (Zero-Shot)

You do not need to learn complex prompts. The Agents know what to do.

**Just Type:**
> `@qc-master I need to test a new payment feature.`

**The Squad will take over:**
1.  `@qc-master` will analyze the request.
2.  It will route you to `@qc-strategy` to plan the test approach.
3.  `@qc-strategy` will route you to `@qc-testcase` to generate cases.
4.  The **Chain Reaction** begins.

*Welcome to System 2 Testing.*

---

## 🛡️ Tool Mandates (High-Assurance)

| Agent | Risk Without Tool | Mandatory Tool |
| :--- | :--- | :--- |
| `@qc-metrics` | Wrong calculations | `run_command(python)` |
| `@qc-automation` | Non-working scripts | `run_command(npx playwright test)` |
| `@qc-performance` | Invalid load tests | `run_command(k6 run)` |
| `@qc-security` | Outdated vulnerabilities | `search_web` (OWASP) |
| `@qc-regression` | Missed dependencies | `grep_search` |

---

## 📊 Quality Standards

This kit is built on industry-leading standards:

| Standard | Application |
| :--- | :--- |
| **ISTQB** | Test design techniques, test levels, processes |
| **OWASP Top 10** | Security testing checklist |
| **ISO 25010** | Quality attributes (Performance, Security, Usability) |
| **IEEE 829** | Test documentation standards |

---

<p align="center">
  <strong>Built for the Antigravity Age.</strong><br>
  <em>Test Smarter. Ship Faster.</em>
</p>
