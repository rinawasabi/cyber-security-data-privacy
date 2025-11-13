
# 1️⃣ Introduction

**Tester(s):**  
- Name:  Rina Poutiainen-Uekusa

**Purpose:**  
- To detect vulnerabilities and flows in Booking system's registration and authentication process

**Scope:**  
- Tested components: Registration page and database connected via Docker Container
- Exclusions: Other pages than registration page (e.g., Main, login & administration)
- Test approach: Gray-box, since the tester knows partially about the Docker container configuration and database connection.

**Test environment & dates:**  
Dates
- Start: 23.00
- End:  23.30
  
Test environment details (OS, runtime, DB, browsers)
- OS: macOS Tahoe 26.1
- Runtime: Deno in Docker Container
- Database: PostgreSQL 18.0
- Browser: Google Chrome 142.0 (tested via OWASP ZAP)

**Assumptions & constraints:**  
Assumptions
- The webpage and Docker containers correctly running locally.
- Stable internet connection during the test.
- ZAP Automated Scan is available.  

Constraints
- The tester is still in the biginner phase.
- The test focused mainly on basic vulnerability scanning via OWASP ZAP.

---

# 2️⃣ Executive Summary

**Short summary (1-2 sentences):**  
The testing of the booking system's registration process was done successfully using ZAP.
The results revealed several vulnabilities in the system ranging from low to high severity levels.

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

# 4️⃣ Findings

> Fill in one row per finding. Focus on clarity and the most important issues.

| ID | Severity | Finding | Description | Evidence / Proof |
|------|-----------|----------|--------------|------------------|
| F-01 | 🔴 High | Path Traversal | Input field allows `' OR '1'='1` injection | Screenshot or sqlmap result |
| F-02 | 🔴 High | SQL Injection | Session ID remains unchanged after login | Burp log or response headers |
| F-03 | 🟠 Medium | Absence of Anti-CSRF Tokens | Accepts passwords like "12345" | Screenshot of registration success |
| F-04 | 🟠 Medium | Content Security Policy (CSP) Header Not Set | Accepts passwords like "12345" | Screenshot of registration success |
| F-05 | 🟠 Medium | Format String Error | Accepts passwords like "12345" | Screenshot of registration success |


---

> [!NOTE]
> Include up to 5 findings total.   
> Keep each description short and clear.

---

# 5️⃣ OWASP ZAP Test Report (Attachment)

- The link to my OWASP ZAP scan results is [here](https://github.com/rinawasabi/cyber-security-data-privacy/blob/main/BookingSystem/Phase1/zap_report_round1.md).

---


