# 🧠 Cyber Security Internship – Task 1  
## Web Application Security Testing using OWASP ZAP  

### 📌 Basic Information
- *Name:* Shaun Dsouza
- *Date:* 12 November 2025  
- *Tool Used:* OWASP ZAP 2.16.1  
- *Target URL:* [https://juice-shop.herokuapp.com](https://juice-shop.herokuapp.com)  

---

### 🔍 1. Overview
The purpose of this cybersecurity task was to perform a *vulnerability assessment* of the OWASP Juice Shop web application using *OWASP ZAP*.  
The goal was to identify and document security flaws according to *OWASP Top 10* standards.

---

### ⚙ 2. Tools & Methodology
*Tools Used:*
- OWASP ZAP (Automated Scan – Quick Start)  
- Google Chrome (for testing and validation)

*Testing Steps:*
1. Selected the OWASP Juice Shop as the target web application.  
2. Performed an automated scan using OWASP ZAP with the target URL.  
3. Reviewed and analyzed alerts generated after the scan.  
4. Documented vulnerabilities and captured screenshots for reference.  

*Scan Duration:* Approximately 2 minutes.  

---

### 🧾 3. Findings Summary
| No | Vulnerability | OWASP Category | Risk | Description | Recommended Fix |
|----|----------------|----------------|------|--------------|-----------------|
| 1 | Content Security Policy Header Not Set | A06: Security Misconfiguration | *High* | Missing CSP header may allow XSS attacks. | Add Content-Security-Policy header. |
| 2 | Strict-Transport-Security Header Not Set | A06: Security Misconfiguration | *High* | Site doesn’t enforce HTTPS. | Implement HSTS header. |
| 3 | Cross-Domain Misconfiguration | A01: Broken Access Control | *Medium* | Allows access from unauthorized domains. | Restrict CORS to trusted origins. |
| 4 | Cross-Domain JavaScript Source File Inclusion | A06: Security Misconfiguration | *Medium* | External JS loaded without integrity check. | Use Subresource Integrity or trusted sources. |
| 5 | Timestamp Disclosure (Unix) | A05: Security Misconfiguration | *Low* | Reveals server timestamps. | Remove or mask timestamp info. |
| 6 | Information Disclosure – Suspicious Comments | A02: Cryptographic Failures | *Low* | Developer comments visible in code. | Remove debug comments before deployment. |
| 7 | Modern Web Application | — | Info | General information about framework. | No action needed. |
| 8 | Cache-Control Directives – Re-Examine | A06: Security Misconfiguration | *Low* | Missing secure cache headers. | Add Cache-Control: no-store, no-cache. |

---

### 📉 4. Detailed Vulnerability Analysis

#### 🔹 Content Security Policy (CSP) Header Not Set – *High Risk*
The lack of a CSP header allows unrestricted content execution, making the application vulnerable to *Cross-Site Scripting (XSS)* attacks.  
*Recommendation:* Implement a strong Content-Security-Policy restricting scripts and resources to trusted domains.

---

#### 🔹 Strict-Transport-Security (HSTS) Header Not Set – *High Risk*
Without HSTS, users accessing the site via HTTP can face *Man-in-the-Middle (MITM)* attacks.  
*Recommendation:* Add the Strict-Transport-Security header with a max-age directive and includeSubDomains option.

---

#### 🔹 Cross-Domain Misconfiguration – *Medium Risk*
Overly permissive CORS settings may expose sensitive user data to external sites.  
*Recommendation:* Restrict Access-Control-Allow-Origin to trusted domains only.

---

#### 🔹 Cross-Domain JavaScript Inclusion – *Medium Risk*
External JS is loaded without Subresource Integrity (SRI), risking supply-chain attacks.  
*Recommendation:* Implement SRI checks for all external resources.

---

#### 🔹 Timestamp Disclosure – *Low Risk*
Server timestamps exposed in headers can assist attackers in reconnaissance.  
*Recommendation:* Remove or mask timestamps from HTTP responses.

---

#### 🔹 Information Disclosure – Suspicious Comments – *Low Risk*
Developer comments in the source code can reveal internal logic or future features.  
*Recommendation:* Remove all non-production comments and debug statements before deployment.

---

#### 🔹 Cache-Control Directives – *Low Risk*
Lack of secure cache headers could lead to data exposure in shared environments.  
*Recommendation:* Use Cache-Control: no-store, no-cache, must-revalidate for sensitive pages.

---

### 🧩 5. OWASP Top 10 Compliance Checklist
| No | Vulnerability | OWASP Category | Compliance | Risk |
|----|----------------|----------------|-------------|------|
| 1 | CSP Header Not Set | A06: Security Misconfiguration | ❌ Non-Compliant | High |
| 2 | HSTS Header Not Set | A06: Security Misconfiguration | ❌ Non-Compliant | High |
| 3 | Cross-Domain Misconfiguration | A01: Broken Access Control | ❌ Non-Compliant | Medium |
| 4 | Cross-Domain JS Inclusion | A06: Security Misconfiguration | ❌ Non-Compliant | Medium |
| 5 | Timestamp Disclosure | A05: Security Misconfiguration | ❌ Non-Compliant | Low |
| 6 | Information Disclosure | A02: Cryptographic Failures | ❌ Non-Compliant | Low |
| 7 | Modern Web Application (Info) | — | ✅ Informational Only | Info |
| 8 | Cache-Control Re-Examine | A06: Security Misconfiguration | ❌ Non-Compliant | Low |

---

### 🧠 6. Conclusion
The *OWASP ZAP* scan of the OWASP Juice Shop identified multiple configuration-related vulnerabilities.  
While most were of *low-to-medium risk, implementing the recommended fixes — especially around **HTTP headers* and *CORS policies* — will significantly improve the application’s overall security posture and OWASP Top 10 compliance.  

This task successfully demonstrated the *web vulnerability assessment process* and the use of *automated security tools* to identify potential flaws in a modern web application.

---

### 🗂 7. Deliverables
- [Task1_Report.pdf](./Task1_Report.pdf) – Full Web Application Security Testing Report  
- [/screenshots](./screenshots) – OWASP ZAP scan screenshots  

---

👨‍💻 *Analyst:* Shaun Dsouza 
*Internship:* Future Interns – Cybersecurity (2025)
