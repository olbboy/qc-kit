# 📊 QA Metrics & Formulas

> **Quick Reference for @qc-metrics Agent**
> All formulas with Python implementations

---

## 1. Coverage Metrics

### Requirements Coverage
```python
# How many requirements have at least one test?
requirements_coverage = (requirements_with_tests / total_requirements) * 100
```

### Test Case Coverage
```python
# How many test cases have been executed?
execution_coverage = (tests_executed / total_tests) * 100
```

### Code Coverage
```python
# Statement coverage
statement_coverage = (statements_executed / total_statements) * 100

# Branch coverage
branch_coverage = (branches_executed / total_branches) * 100
```

---

## 2. Defect Metrics

### Defect Density
```python
# Defects per thousand lines of code
defect_density = (total_defects / KLOC)

# Example: 50 defects in 10,000 LOC = 5 defects/KLOC
```

### Defect Removal Efficiency (DRE)
```python
# How many defects did we find before release?
DRE = (defects_found_before_release / (defects_before_release + defects_in_production)) * 100

# Target: > 95%
```

### Defect Leakage
```python
# How many defects escaped to production?
defect_leakage = (defects_in_production / total_defects_found) * 100

# Target: < 5%
```

### Defect Injection Rate
```python
# Defects introduced per phase
injection_rate = defects_introduced / (requirements_or_code_changes)
```

---

## 3. Execution Metrics

### Pass Rate
```python
pass_rate = (tests_passed / tests_executed) * 100
```

### Fail Rate
```python
fail_rate = (tests_failed / tests_executed) * 100
```

### Block Rate
```python
block_rate = (tests_blocked / total_tests) * 100
```

### Automation Rate
```python
automation_rate = (automated_tests / total_tests) * 100

# Target: > 70% for regression
```

---

## 4. Efficiency Metrics

### Test Execution Productivity
```python
# Tests executed per day
productivity = tests_executed / testing_days
```

### Defect Detection Rate
```python
# Defects found per hour of testing
detection_rate = defects_found / testing_hours
```

### Cost Per Defect
```python
# Average cost to find and fix one defect
cost_per_defect = total_qa_cost / defects_found
```

---

## 5. Quality Metrics

### Test Effectiveness
```python
# How good are our tests at finding defects?
effectiveness = (defects_from_tests / total_defects) * 100
```

### Regression Defect Rate
```python
# Defects introduced by changes
regression_rate = (regression_defects / total_defects) * 100

# Target: < 10%
```

---

## 6. Python Calculator Script

```python
#!/usr/bin/env python3
"""QA Metrics Calculator for @qc-metrics"""

def calculate_all_metrics(data: dict) -> dict:
    """Calculate all QA metrics from input data."""
    
    metrics = {}
    
    # Coverage
    if 'requirements_with_tests' in data and 'total_requirements' in data:
        metrics['requirements_coverage'] = round(
            (data['requirements_with_tests'] / data['total_requirements']) * 100, 2
        )
    
    # Pass Rate
    if 'tests_passed' in data and 'tests_executed' in data:
        metrics['pass_rate'] = round(
            (data['tests_passed'] / data['tests_executed']) * 100, 2
        )
    
    # Defect Density
    if 'total_defects' in data and 'kloc' in data:
        metrics['defect_density'] = round(
            data['total_defects'] / data['kloc'], 2
        )
    
    # DRE
    if 'defects_before_release' in data and 'defects_in_production' in data:
        total = data['defects_before_release'] + data['defects_in_production']
        metrics['DRE'] = round(
            (data['defects_before_release'] / total) * 100, 2
        ) if total > 0 else 100.0
    
    # Automation Rate
    if 'automated_tests' in data and 'total_tests' in data:
        metrics['automation_rate'] = round(
            (data['automated_tests'] / data['total_tests']) * 100, 2
        )
    
    return metrics


# Example usage
if __name__ == "__main__":
    sample_data = {
        'requirements_with_tests': 45,
        'total_requirements': 50,
        'tests_passed': 190,
        'tests_executed': 200,
        'total_defects': 25,
        'kloc': 10,
        'defects_before_release': 23,
        'defects_in_production': 2,
        'automated_tests': 150,
        'total_tests': 200,
    }
    
    results = calculate_all_metrics(sample_data)
    
    print("=== QA Metrics Report ===")
    for metric, value in results.items():
        print(f"{metric}: {value}%")
```

---

## 7. Benchmark Targets

| Metric | Poor | Average | Good | Excellent |
| :--- | :---: | :---: | :---: | :---: |
| **Pass Rate** | <80% | 80-90% | 90-95% | >95% |
| **DRE** | <85% | 85-90% | 90-95% | >95% |
| **Defect Density** | >10 | 5-10 | 2-5 | <2 |
| **Automation Rate** | <30% | 30-50% | 50-70% | >70% |
| **Requirements Coverage** | <70% | 70-85% | 85-95% | >95% |

---

*Use `run_command(python)` to calculate these metrics accurately.*
