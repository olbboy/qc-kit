# 📚 ISTQB Foundation Reference

> **Quick Reference for QC-Kit Agents**
> Source: ISTQB Certified Tester Foundation Level Syllabus

---

## 1. Test Design Techniques

### 1.1 Black-Box Techniques (Specification-Based)

#### Equivalence Partitioning (EP)
*   Divide input data into valid and invalid partitions
*   One test case per partition is usually sufficient
*   Example: Age field (0-17: Minor, 18-64: Adult, 65+: Senior)

#### Boundary Value Analysis (BVA)
*   Test at the edges of partitions
*   Min-1, Min, Max, Max+1
*   Example: If valid range is 1-100, test: 0, 1, 100, 101

#### Decision Table Testing
*   Use when multiple conditions affect outcomes
*   Each column = one test case
*   Useful for business rules

#### State Transition Testing
*   Model system as states/transitions
*   Test valid and invalid transitions
*   Good for workflows, status changes

### 1.2 White-Box Techniques (Structure-Based)

#### Statement Coverage
*   Every statement executed at least once
*   Minimum coverage level

#### Branch/Decision Coverage
*   Every decision outcome executed
*   Both true and false paths

---

## 2. Test Levels

| Level | Focus | Performed By |
| :--- | :--- | :--- |
| **Unit Testing** | Individual components | Developers |
| **Integration Testing** | Component interactions | Developers/Testers |
| **System Testing** | Complete system | Testers |
| **Acceptance Testing** | Business requirements | Users/Business |

---

## 3. Test Types

| Type | Purpose |
| :--- | :--- |
| **Functional** | Verify what the system does |
| **Non-Functional** | Verify how the system performs |
| **Structural** | Verify internal structure |
| **Change-Related** | Verify after changes (Regression) |

---

## 4. Test Process Activities

1.  **Test Planning** - Define scope, approach, resources
2.  **Test Monitoring & Control** - Track progress, adjust plans
3.  **Test Analysis** - Identify test conditions
4.  **Test Design** - Create test cases
5.  **Test Implementation** - Prepare test data, environment
6.  **Test Execution** - Run tests, log results
7.  **Test Completion** - Close activities, archive

---

## 5. Defect Classification

### Severity Levels
| Severity | Description |
| :--- | :--- |
| **Critical** | System crash, data corruption |
| **Major** | Feature not working, no workaround |
| **Minor** | Feature issue, workaround exists |
| **Trivial** | Cosmetic, documentation |

### Priority Levels
| Priority | Action |
| :--- | :--- |
| **P0** | Fix immediately, blocker |
| **P1** | Fix before release |
| **P2** | Fix in next release |
| **P3** | Nice to have |

---

## 6. Key Metrics

```python
# Test Coverage
coverage_pct = (tested_requirements / total_requirements) * 100

# Defect Density
defect_density = defects_found / KLOC  # per thousand lines of code

# Defect Removal Efficiency
DRE = (defects_before_release / total_defects) * 100

# Pass Rate
pass_rate = (tests_passed / tests_executed) * 100
```

---

*Reference: ISTQB® Certified Tester Foundation Level Syllabus v4.0*
