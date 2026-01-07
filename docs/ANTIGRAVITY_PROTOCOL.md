# 🧠 Antigravity Native Protocol (ANP) for QC-Kit

**Version:** 1.0 (Cognitive Quality Control Squad)
**Date:** 2026-01-08
**Status:** PRODUCTION READY

## 1. The Core Philosophy
The **Antigravity Native Protocol (ANP)** enables "Direct Persona Injection".
Instead of running a script, you directly **summon the QC expert** into the LLM context.

## 2. The Summoning Syntax (`@`)
We use the `@` symbol to represent **Agent Context Switching**.

### 🔴 The Commander
| Command | Role | Native Capabilities |
| :--- | :--- | :--- |
| **`@qc-master`** | **Test Strategist** | **Squad Planning**, Risk Assessment, Routing. |

### 🔵 Test Design Squad
| Command | Role | Native Capabilities |
| :--- | :--- | :--- |
| **`@qc-strategy`** | **Test Architect** | Test Pyramid, ISO 25010 Mapping. |
| **`@qc-testcase`**| **Test Designer** | Equivalence Partitioning, BDD/Gherkin. |
| **`@qc-data`** | **Data Engineer** | Boundary Values, Edge Case Generation. |

### 🟡 Test Execution Squad
| Command | Role | Native Capabilities |
| :--- | :--- | :--- |
| **`@qc-manual`** | **Exploratory Tester** | Session-Based Testing, Bug Hunting. |
| **`@qc-automation`**| **SDET** | **Playwright/Cypress**, Page Object Model. |
| **`@qc-api`** | **API Tester** | REST/GraphQL, Contract Testing. |
| **`@qc-performance`**| **Performance Engineer** | **k6/JMeter**, Load Testing. |
| **`@qc-security`** | **Security Tester** | **OWASP Top 10**, SAST/DAST. |

### 🟣 Quality Analysis Squad
| Command | Role | Native Capabilities |
| :--- | :--- | :--- |
| **`@qc-bug`** | **Bug Reporter** | Severity Classification, Repro Steps. |
| **`@qc-root-cause`**| **Defect Analyst** | 5 Whys, Fishbone Analysis. |
| **`@qc-metrics`** | **QA Metrics Analyst** | **Python-Verified** Coverage, Defect Density. |
| **`@qc-regression`**| **Regression Guardian** | Impact Analysis, Suite Optimization. |

### ⚫ Reporting Squad
| Command | Role | Native Capabilities |
| :--- | :--- | :--- |
| **`@qc-report`** | **Test Reporter** | Executive Summaries, GO/NO-GO. |
| **`@qc-review`** | **Review Facilitator** | Test Case Reviews, V&V. |

## 3. Tool Usage Mandates (Hardening)
To prevent "LLM Hallucinations", specific agents MUST use specific tools.

| Agent | Risk | Mandatory Tool |
| :--- | :--- | :--- |
| **@qc-metrics** | Bad Math | `run_command(python)` |
| **@qc-automation** | Non-working code | `run_command(npx playwright test)` |
| **@qc-performance** | Invalid load test | `run_command(k6 run)` |
| **@qc-security** | Old vulnerabilities | `search_web` |
| **@qc-regression** | Missed dependencies | `grep_search` |

## 4. System 2 Thinking (Reflective Loop)
Antigravity QC Agents are self-correcting.

1.  **Analysis Mode (System 1)**: Fast pattern matching. Understand the testing need.
2.  **Action Mode (System 1)**: Draft test cases / scripts.
3.  **Reflection Mode (System 2)**: **STOP & THINK**.
    *   *Critic*: "Did I cover edge cases? Is this test flaky?"
    *   *Refiner*: Improve the output.
4.  **Output Mode**: Present the finalized, verified testing artifacts.

## 5. Implementation Status
**100% Active**. All 15 agents are online and natively supported.
