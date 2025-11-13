
# 1️⃣ Introduction

**Tester(s):**  
- Name:  Rina Poutiainen-Uekusa

**Purpose:**  
- To detect vulnerabilities and flows in Booking system's registration and authentication process

**Scope:**  
- Tested components: Registration page 
- Exclusions:  
- Test approach: Gray-box

**Test environment & dates:**  
Dates
- Start: 23.00
- End:  23.15
  
Test environment details (OS, runtime, DB, browsers)
- OS: macOS Tahoe 26.1
- Runtime: Docker Container (internal runtime unknown)
- Database: PostgreSQL 18.0
- Browser: Google Chrome 142.0 (tested via OWASP ZAP)

**Assumptions & constraints:**  
- e.g., credentials provided, limited time, etc.

---

# 2️⃣ Executive Summary

**Short summary (1-2 sentences):**  

**Overall risk level:** (Low / Medium / High / Critical)

**Top 5 immediate actions:**  
1.  
2.  
3.  
4.  
5.  

---

# 3️⃣ Severity scale & definitions

|  **Severity Level**  | **Description**                                                                                                              | **Recommended Action**           |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
|      🔴 **High**     | A serious vulnerability that can lead to full system compromise or data breach (e.g., SQL Injection, Remote Code Execution). | *Immediate fix required*         |
|     🟠 **Medium**    | A significant issue that may require specific conditions or user interaction (e.g., XSS, CSRF).                              | *Fix ASAP*                       |
|      🟡 **Low**      | A minor issue or configuration weakness (e.g., server version disclosure).                                                   | *Fix soon*                       |
| 🔵 **Info** | No direct risk, but useful for system hardening (e.g., missing security headers).                                            | *Monitor and fix in maintenance* |


---

# 4️⃣ Findings (filled with examples → replace)

> Fill in one row per finding. Focus on clarity and the most important issues.

| ID | Severity | Finding | Description | Evidence / Proof |
|------|-----------|----------|--------------|------------------|
| F-01 | 🔴 High | SQL Injection in registration | Input field allows `' OR '1'='1` injection | Screenshot or sqlmap result |
| F-02 | 🟠 Medium | Session fixation | Session ID remains unchanged after login | Burp log or response headers |
| F-03 | 🟡 Low | Weak password policy | Accepts passwords like "12345" | Screenshot of registration success |

---

> [!NOTE]
> Include up to 5 findings total.   
> Keep each description short and clear.

---

# 5️⃣ OWASP ZAP Test Report (Attachment)

- The link to my OWASP ZAP scan results is [here](https://github.com/rinawasabi/cyber-security-data-privacy/blob/main/BookingSystem/Phase1/zap_report_round1.md).

---


