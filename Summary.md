## Summary
### Below is the summary of 2025-Report_zap (attached)
#### **REPORT for http://127.0.0.1:8080 Webgoat Environment using ZAP**
### Overall Alert Summary
| Risk Level     | Number of Alerts |
|----------------|------------------|
| High           | 0                |
| Medium         | 4                |
| Low            | 2                |
| Informational  | 4                |

### Medium-Risk Alerts
1. Missing CSRF Tokens (5) – Forms are vulnerable to CSRF attacks.
   - Fix: Add anti-CSRF tokens (e.g., with OWASP CSRFGuard).
2. No Content Security Policy (8) – Site lacks CSP headers, increasing XSS risk.
   - Fix: Implement Content-Security-Policy headers.
3. Missing Clickjacking Protection (5) – No X-Frame-Options or frame-ancestors.
   - Fix: Use X-Frame-Options: DENY or CSP directive.
4. Spring Actuator Leak (1) – /actuator/health exposes internal app info.
   - Fix: Restrict access to actuator endpoints.
### Low-Risk Alerts
1. SameSite Cookie Missing (1) – Cookie is vulnerable to cross-site attacks.
   - Fix: Set SameSite=Strict or Lax.
2. X-Content-Type-Options Missing (11) – Allows MIME sniffing.
   - Fix: Add X-Content-Type-Options: nosniff header.
### Informational Alerts
- Auth Request Detected (3) – Login forms found.
- Session Token Found (8) – JSESSIONID cookie identified.
- User-Agent Fuzzing (84) – Different responses based on user agents.
- Potential XSS in HTML Attributes (6) – User input reflected in attributes.
**Fix: Validate and sanitize user input.**
---
