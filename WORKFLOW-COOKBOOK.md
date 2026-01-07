# 📖 QC-Kit Workflow Cookbook (10 Real-World Scenarios)

**"How do I use these agents in a real testing fight?"**

This cookbook provides **10 Battle-Tested Workflows** ("Recipes") for common QC scenarios.
Each recipe shows exactly which agents to summon (`@`) and in what order.

---

## 🟢 SCENARIO 1: The "New Feature" (Story to Tests)
**Context**: A developer just finished a feature. You need to test it.
**Goal**: Generate complete test coverage.

**The Chain:**
1.  **`@qc-testcase`**: "Generate test cases for: 'As a user, I can reset my password via email.'"
    *   *(Agent generates Positive, Negative, Edge cases)*
2.  **`@qc-data`**: "Generate test data for password reset including invalid emails."
3.  **`@qc-automation`**: "Convert these test cases to Playwright TypeScript."
4.  **`@qc-report`**: "Summarize the test coverage for this feature."

---

## 🟡 SCENARIO 2: The "Bug Hunt" (Exploratory Testing)
**Context**: QA lead says "The checkout feels buggy." No specific bug reported.
**Goal**: Find hidden bugs through exploration.

**The Chain:**
1.  **`@qc-manual`**: "Do exploratory testing on the checkout flow. Focus on edge cases."
    *   *(Agent runs SBTM session, documents findings)*
2.  **`@qc-bug`**: "Write bug reports for the issues I found."
3.  **`@qc-regression`**: "Recommend tests to add to prevent these bugs."

---

## 🔴 SCENARIO 3: The "Production Incident" (Root Cause)
**Context**: A critical bug made it to production. Management wants answers.
**Goal**: Find root cause and prevent recurrence.

**The Chain:**
1.  **`@qc-bug`**: "Document this production incident: Users can't complete checkout on iOS Safari."
2.  **`@qc-root-cause`**: "Analyze this bug using 5 Whys. Why wasn't it caught?"
    *   *(Agent drills: Missing Safari test → No mobile test env → Budget constraint)*
3.  **`@qc-metrics`**: "Calculate our defect leakage rate."
4.  **`@qc-strategy`**: "Recommend improvements to our test strategy."

---

## 🔵 SCENARIO 4: The "API Integration" (Backend Testing)
**Context**: You need to test a new REST API before the frontend is ready.
**Goal**: Comprehensive API test coverage.

**The Chain:**
1.  **`@qc-api`**: "Generate tests for POST /api/orders endpoint. Here's the Swagger spec."
    *   *(Agent creates positive, negative, schema validation tests)*
2.  **`@qc-security`**: "Check this API endpoint for injection vulnerabilities."
3.  **`@qc-performance`**: "Create a k6 script to load test 500 orders per minute."
4.  **`@qc-report`**: "Generate API test summary report."

---

## 🟣 SCENARIO 5: The "Security Audit" (Compliance Check)
**Context**: The security team wants an OWASP assessment before release.
**Goal**: OWASP Top 10 compliance report.

**The Chain:**
1.  **`@qc-security`**: "Audit the login page for OWASP Top 10 vulnerabilities."
    *   *(Agent checks: Injection, Broken Auth, XSS, etc.)*
2.  **`@qc-api`**: "Test the auth API for brute force protection."
3.  **`@qc-bug`**: "Document the security findings as bugs."
4.  **`@qc-report`**: "Generate OWASP compliance report."

---

## 🟢 SCENARIO 6: The "Sprint Planning" (Test Strategy)
**Context**: New sprint starting. 5 user stories to test.
**Goal**: Define what and how to test.

**The Chain:**
1.  **`@qc-strategy`**: "Create a test strategy for Sprint 23. Here are the user stories..."
2.  **`@qc-testcase`**: "Generate test cases for User Story 1: Shopping Cart."
3.  **`@qc-review`**: "Review these test cases for completeness."
4.  **`@qc-metrics`**: "Estimate test execution time for the sprint."

---

## 🟡 SCENARIO 7: The "Regression Nightmare" (Impact Analysis)
**Context**: A developer changed the payment module. What might break?
**Goal**: Identify impacted tests and areas.

**The Chain:**
1.  **`@qc-regression`**: "Analyze the impact of these code changes: Modified PaymentService.js"
    *   *(Agent scans dependencies, identifies affected tests)*
2.  **`@qc-automation`**: "Run the affected regression tests."
3.  **`@qc-report`**: "Generate regression test results."

---

## 🔴 SCENARIO 8: The "Performance Crisis" (Load Testing)
**Context**: Black Friday is coming. Can the system handle 10x traffic?
**Goal**: Validate performance under load.

**The Chain:**
1.  **`@qc-performance`**: "Create a stress test for 10,000 concurrent users on checkout."
    *   *(Agent generates k6 script with ramp-up stages)*
2.  **`@qc-metrics`**: "Analyze the performance results. Compare to SLAs."
3.  **`@qc-root-cause`**: "The P99 latency is too high. What's the bottleneck?"
4.  **`@qc-report`**: "Generate performance test report for stakeholders."

---

## 🔵 SCENARIO 9: The "Test Review" (Quality Gate)
**Context**: QA team wrote test cases. Need peer review before execution.
**Goal**: Ensure test quality.

**The Chain:**
1.  **`@qc-review`**: "Review these test cases for Login. Check for completeness and clarity."
    *   *(Agent applies checklist: traceable, specific, no duplicates)*
2.  **`@qc-testcase`**: "Add the missing edge cases identified in the review."
3.  **`@qc-metrics`**: "Update the test coverage matrix."

---

## 🟣 SCENARIO 10: The "Release Decision" (Go/No-Go)
**Context**: Release is tomorrow. Need to make a data-driven decision.
**Goal**: Provide GO/NO-GO recommendation.

**The Chain:**
1.  **`@qc-metrics`**: "Calculate: Pass rate, Defect density, Open critical bugs."
2.  **`@qc-regression`**: "Are all P0 features fully tested?"
3.  **`@qc-report`**: "Generate executive test summary with GO/NO-GO recommendation."
    *   *(Agent produces: 🟢 GO / 🟡 CONDITIONAL / 🔴 NO-GO)*

---

**Tip**: You can copy-paste these scenario prompts directly into the Antigravity chat!
