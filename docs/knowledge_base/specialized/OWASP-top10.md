# 🛡️ OWASP Top 10 Reference (2021)

> **Quick Reference for Security Testing**
> Source: OWASP Top 10:2021

---

## The Top 10 Risks

### A01:2021 - Broken Access Control
**What**: Users can access unauthorized resources.

**Test For**:
*   IDOR (Insecure Direct Object Reference)
*   Privilege escalation (regular user → admin)
*   Missing function-level access control
*   Metadata manipulation (JWT tampering)

**Test Payloads**:
```
# IDOR: Change ID in URL
/api/users/123 → /api/users/456

# JWT manipulation
# Decode, change role, re-encode
```

---

### A02:2021 - Cryptographic Failures
**What**: Sensitive data exposed due to weak/missing encryption.

**Test For**:
*   Passwords in plain text
*   Sensitive data in URLs
*   Weak hashing (MD5, SHA1)
*   Missing HTTPS

**Checklist**:
- [ ] Data in transit encrypted (TLS 1.2+)
- [ ] Data at rest encrypted
- [ ] Passwords hashed with bcrypt/Argon2
- [ ] No sensitive data in logs

---

### A03:2021 - Injection
**What**: Untrusted data sent to interpreter.

**Test Payloads**:
```sql
-- SQL Injection
' OR '1'='1
'; DROP TABLE users;--
1 UNION SELECT * FROM users

-- Command Injection
; ls -la
| cat /etc/passwd
`whoami`

-- XSS
<script>alert('XSS')</script>
<img src=x onerror=alert('XSS')>
"><script>alert(1)</script>
```

---

### A04:2021 - Insecure Design
**What**: Missing security controls in design.

**Test For**:
*   Business logic flaws
*   Missing rate limiting
*   Unlimited resource allocation
*   Trust boundary violations

---

### A05:2021 - Security Misconfiguration
**What**: Insecure default configurations.

**Checklist**:
- [ ] No default credentials
- [ ] Error messages don't reveal stack traces
- [ ] Unnecessary features disabled
- [ ] Security headers present (CSP, X-Frame-Options)
- [ ] Directory listing disabled

---

### A06:2021 - Vulnerable Components
**What**: Using outdated libraries with known vulnerabilities.

**Test**:
```bash
# Check npm dependencies
npm audit

# Check Python dependencies
pip-audit

# Check for CVEs
```

---

### A07:2021 - Auth Failures
**What**: Broken authentication mechanisms.

**Test For**:
*   Brute force attacks (no rate limiting)
*   Weak passwords allowed
*   Session fixation
*   Missing MFA on critical actions

---

### A08:2021 - Data Integrity Failures
**What**: Insecure CI/CD or deserialization.

**Test For**:
*   Unsigned updates
*   Insecure deserialization
*   Unverified software sources

---

### A09:2021 - Logging Failures
**What**: Insufficient monitoring.

**Checklist**:
- [ ] Login attempts logged
- [ ] Access control failures logged
- [ ] Logs protected from tampering
- [ ] Alerts for suspicious activity

---

### A10:2021 - SSRF
**What**: Server-side request forgery.

**Test Payloads**:
```
# Internal network access
http://localhost:8080/admin
http://127.0.0.1/
http://169.254.169.254/  # AWS metadata

# Protocol smuggling
file:///etc/passwd
dict://localhost:11211/
```

---

## Quick Security Headers Check

```http
Content-Security-Policy: default-src 'self'
X-Frame-Options: DENY
X-Content-Type-Options: nosniff
Strict-Transport-Security: max-age=31536000
X-XSS-Protection: 1; mode=block
```

---

*Reference: OWASP Top 10:2021 - https://owasp.org/Top10/*
