# 📋 QC-Kit Agent Cheat Sheet (v1.0.0)

> **Quick Reference Card: 15 QC Specialists at Your Fingertips**

---

## 🔴 THE COMMANDER
| Agent | Summon When | Example Prompt |
| :--- | :--- | :--- |
| **`@qc-master`** | You're lost | *"Help me plan testing for this feature."* |

---

## 🔵 THE DESIGNERS (Test Planning)
| Agent | Summon When | Example Prompt |
| :--- | :--- | :--- |
| **`@qc-strategy`** | New project | *"Create a test strategy for this release."* |
| **`@qc-testcase`**| Need tests | *"Generate test cases for Login feature."* |
| **`@qc-data`** | Need data | *"Generate edge case data for email field."* |

---

## 🟡 THE EXECUTORS (Test Running)
| Agent | Summon When | Example Prompt |
| :--- | :--- | :--- |
| **`@qc-manual`** | Explore | *"Do exploratory testing on checkout flow."* |
| **`@qc-automation`**| Script it | *"Convert these tests to Playwright."* |
| **`@qc-api`** | Test APIs | *"Generate tests for POST /users endpoint."* |
| **`@qc-performance`**| Load test | *"Create a k6 script for 1000 users."* |
| **`@qc-security`** | Secure it | *"Audit this form for OWASP Top 10."* |

---

## 🟣 THE ANALYZERS (Quality)
| Agent | Summon When | Example Prompt |
| :--- | :--- | :--- |
| **`@qc-bug`** | Document bug | *"Write a bug report for this issue."* |
| **`@qc-root-cause`**| Find cause | *"Why does this bug keep happening?"* |
| **`@qc-metrics`** | Need numbers | *"Calculate our test coverage %."* |
| **`@qc-regression`**| What to test | *"What tests to run after this change?"* |

---

## ⚫ THE REPORTERS (Communication)
| Agent | Summon When | Example Prompt |
| :--- | :--- | :--- |
| **`@qc-report`** | Status update | *"Generate test summary for this sprint."* |
| **`@qc-review`** | Quality gate | *"Review these test cases for completeness."* |

---

## ⚡ POWER COMBOS

| Scenario | Chain | Result |
| :--- | :--- | :--- |
| **Story → Tests** | `testcase` → `data` → `automation` | Executable Test Suite |
| **Bug Found** | `bug` → `root-cause` → `regression` | Prevention Strategy |
| **Security Audit** | `security` → `api` → `report` | OWASP Compliance Report |
| **Release Go/No-Go** | `metrics` → `report` | Executive Decision |

---

## 🧠 KEY PROTOCOLS

1.  **Context Injection**: Copy `templates/TEST_CONTEXT.md` to your root. Fill in environment details.
2.  **Visual Input**: Drag & Drop screenshots. Use `@[image] @qc-manual analyze this UI`
3.  **Tool Verification**: Agents use `pytest`, `playwright`, `k6` automatically.
4.  **Reflection**: All agents "Stop & Think" before delivering output.

---

*Print this page. Pin it to your monitor. Ship with confidence.*
