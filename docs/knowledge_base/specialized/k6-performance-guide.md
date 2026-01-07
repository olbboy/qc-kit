# ⚡ k6 Performance Testing Guide

> **Quick Reference for Load Testing**
> Framework: k6 (Grafana k6)

---

## 1. Installation

```bash
# macOS
brew install k6

# Windows
winget install k6 --source winget

# Docker
docker run -i grafana/k6 run - <script.js

# npm (unofficial)
npm install -g k6
```

---

## 2. Basic Test Structure

```javascript
import http from 'k6/http';
import { check, sleep } from 'k6';

// Test configuration
export const options = {
  vus: 10,           // Virtual Users
  duration: '30s',   // Test duration
};

// Main test function (executed per VU)
export default function () {
  const res = http.get('https://api.example.com/users');
  
  check(res, {
    'status is 200': (r) => r.status === 200,
    'response time < 500ms': (r) => r.timings.duration < 500,
  });
  
  sleep(1);  // Think time
}
```

---

## 3. Load Test Scenarios

### 3.1 Smoke Test (Validation)
```javascript
export const options = {
  vus: 1,
  duration: '1m',
};
```
*Purpose: Verify script works, baseline performance*

### 3.2 Load Test (Expected Load)
```javascript
export const options = {
  stages: [
    { duration: '2m', target: 100 },   // Ramp up
    { duration: '5m', target: 100 },   // Steady state
    { duration: '2m', target: 0 },     // Ramp down
  ],
};
```
*Purpose: Test under normal expected load*

### 3.3 Stress Test (Breaking Point)
```javascript
export const options = {
  stages: [
    { duration: '2m', target: 100 },
    { duration: '5m', target: 100 },
    { duration: '2m', target: 200 },   // Push higher
    { duration: '5m', target: 200 },
    { duration: '2m', target: 300 },   // Find breaking point
    { duration: '5m', target: 300 },
    { duration: '2m', target: 0 },
  ],
};
```
*Purpose: Find system limits*

### 3.4 Spike Test (Sudden Burst)
```javascript
export const options = {
  stages: [
    { duration: '10s', target: 100 },  // Quick ramp
    { duration: '1m', target: 100 },   // Stay at peak
    { duration: '10s', target: 0 },    // Quick ramp down
  ],
};
```
*Purpose: Test sudden traffic surge*

### 3.5 Soak Test (Endurance)
```javascript
export const options = {
  stages: [
    { duration: '2m', target: 100 },
    { duration: '4h', target: 100 },   // Long duration
    { duration: '2m', target: 0 },
  ],
};
```
*Purpose: Find memory leaks, resource exhaustion*

---

## 4. Thresholds (Pass/Fail Criteria)

```javascript
export const options = {
  thresholds: {
    // Response time thresholds
    http_req_duration: ['p(95)<500'],      // 95% under 500ms
    http_req_duration: ['p(99)<1000'],     // 99% under 1s
    
    // Error rate threshold
    http_req_failed: ['rate<0.01'],        // Less than 1% errors
    
    // Custom metric threshold
    'http_req_duration{name:login}': ['p(95)<300'],
    
    // Checks threshold
    checks: ['rate>0.95'],                  // 95% checks pass
  },
};
```

---

## 5. HTTP Methods

```javascript
import http from 'k6/http';

// GET
const getRes = http.get('https://api.example.com/users');

// POST with JSON
const postRes = http.post(
  'https://api.example.com/users',
  JSON.stringify({ name: 'John', email: 'john@example.com' }),
  { headers: { 'Content-Type': 'application/json' } }
);

// PUT
const putRes = http.put(url, body, params);

// DELETE
const delRes = http.del(url, body, params);

// Batch requests (parallel)
const responses = http.batch([
  ['GET', 'https://api.example.com/users'],
  ['GET', 'https://api.example.com/orders'],
]);
```

---

## 6. Authentication

```javascript
import http from 'k6/http';
import { check } from 'k6';

export function setup() {
  // Login once, share token across VUs
  const loginRes = http.post('https://api.example.com/login', {
    username: 'testuser',
    password: 'testpass',
  });
  
  return { token: loginRes.json('token') };
}

export default function (data) {
  const params = {
    headers: {
      'Authorization': `Bearer ${data.token}`,
    },
  };
  
  const res = http.get('https://api.example.com/protected', params);
  check(res, { 'status is 200': (r) => r.status === 200 });
}
```

---

## 7. Data Parameterization

```javascript
import { SharedArray } from 'k6/data';

// Load test data from JSON file
const users = new SharedArray('users', function () {
  return JSON.parse(open('./testdata/users.json'));
});

export default function () {
  // Pick random user
  const user = users[Math.floor(Math.random() * users.length)];
  
  http.post('https://api.example.com/login', {
    email: user.email,
    password: user.password,
  });
}
```

---

## 8. Checks & Assertions

```javascript
import { check } from 'k6';

export default function () {
  const res = http.get('https://api.example.com/users');
  
  check(res, {
    // Status checks
    'status is 200': (r) => r.status === 200,
    'status is not 500': (r) => r.status !== 500,
    
    // Response body checks
    'body contains users': (r) => r.body.includes('users'),
    'users array not empty': (r) => r.json('users').length > 0,
    
    // Performance checks
    'response time < 500ms': (r) => r.timings.duration < 500,
    
    // Header checks
    'content type is JSON': (r) => 
      r.headers['Content-Type'].includes('application/json'),
  });
}
```

---

## 9. Custom Metrics

```javascript
import { Counter, Gauge, Rate, Trend } from 'k6/metrics';

// Define custom metrics
const orderCounter = new Counter('orders_created');
const orderAmount = new Trend('order_amount');
const errorRate = new Rate('errors');
const activeUsers = new Gauge('active_users');

export default function () {
  // Use custom metrics
  orderCounter.add(1);
  orderAmount.add(99.99);
  errorRate.add(false);  // false = success
  activeUsers.add(10);
}
```

---

## 10. Running Tests

```bash
# Basic run
k6 run script.js

# With virtual users and duration (override options)
k6 run --vus 50 --duration 30s script.js

# Output to JSON
k6 run --out json=results.json script.js

# Output to InfluxDB (for Grafana dashboards)
k6 run --out influxdb=http://localhost:8086/k6 script.js

# Run with environment variables
k6 run -e BASE_URL=https://staging.example.com script.js

# Cloud execution (Grafana Cloud k6)
k6 cloud script.js
```

---

## 11. Analyzing Results

Key metrics to watch:
| Metric | Description | Target |
| :--- | :--- | :--- |
| `http_req_duration` | Response time | p95 < 500ms |
| `http_req_failed` | Error rate | < 1% |
| `http_reqs` | Total requests | - |
| `vus` | Virtual users | - |
| `iterations` | Completed iterations | - |

Sample output:
```
     checks.........................: 99.50% ✓ 995  ✗ 5
     data_received..................: 1.2 MB 39 kB/s
     data_sent......................: 89 kB  2.9 kB/s
     http_req_duration..............: avg=245ms p(90)=401ms p(95)=512ms
     http_reqs......................: 1000   33/s
     vus............................: 10     min=10  max=10
```

---

*Reference: https://k6.io/docs/*
