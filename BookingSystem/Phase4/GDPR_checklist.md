# GDPR Compliance Checklist – Web-based Booking System

| **Result** | **Personal data mapping and minimization** |
| :----: | :--- |
| &nbsp;✅&nbsp; | All personal data collected and processed have been identified (e.g., username, password_hash, role,  birthdate, terms_accepted)|
| &nbsp;✅&nbsp; | Only minimal and necessary information is collected to register as a user. |
| &nbsp;✅&nbsp; | The system prevents registration if the user’s birthdate is under 15 years old |

---

| **Result** | **User registration and management** |
| :----: | :--- |
| &nbsp;✅&nbsp; | The registration form includes GDPR-compliant consent for processing<br> personal data ("I accept the Terms of Service")|
| &nbsp;❌&nbsp; | Users can only view and cannot edit and delete their own personal data on `/account` |
| &nbsp;✅/❌&nbsp; | No mechanism available for the administrator to delete a reserver in<br> accordance with the "right to be forgotten" |
| &nbsp;✅&nbsp; | Underage registration (under 15 years) and booking functionality are correctly restricted |

---

| **Result** | **Booking visibility** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Bookings is visible to non-logged-in users without showing Reserver's personal data |
| &nbsp;✅/❌/⚠️&nbsp; | Is it ensured that names, emails, or other personal data of bookers are not exposed<br> publicly or to unauthorized users? |

--- 

| **Result** | **Access control and authorization** |
| :----: | :--- |
| &nbsp;✅/❌/⚠️&nbsp; | Have you ensured that only administrators can add, modify, and delete<br> resources and bookings? |
| &nbsp;✅/❌/⚠️&nbsp; | Is the system using role-based access control (e.g., reserver vs. administrator)? |
| &nbsp;✅/❌/⚠️&nbsp; | Are administrator privileges limited to ensure GDPR compliance (e.g., administrators<br> cannot use data for unauthorized purposes)? |

---

| **Result** | **Privacy by Design Principles** |
| :----: | :--- |
| &nbsp;✅/❌/⚠️&nbsp; | Has Privacy by Default been implemented (e.g., collecting the minimum data by default)? |
| &nbsp;✅/❌/⚠️&nbsp; | Are logs implemented without unnecessarily storing personal data? |
| &nbsp;✅/❌/⚠️&nbsp; | Are forms and system components designed with data protection in mind<br> (e.g., secured login, minimal fields)? |

---

| **Result** | **Data security** |
| :----: | :--- |
| &nbsp;✅/❌/⚠️&nbsp; | Are CSRF, XSS, and SQL injection protections implemented? |
| &nbsp;✅/❌/⚠️&nbsp; | Are passwords securely hashed using a strong algorithm (e.g., bcrypt, Argon2)? |
| &nbsp;✅/❌/⚠️&nbsp; | Are data backup and recovery processes GDPR-compliant? |
| &nbsp;✅/❌/⚠️&nbsp; | Is personal data stored in data centers located within the EU? |

---

| **Result** | **Data anonymization and pseudonymization** |
| :----: | :--- |
| &nbsp;✅/❌/⚠️&nbsp; | Is personal data anonymized where possible? |
| &nbsp;✅/❌/⚠️&nbsp; | Are pseudonymization techniques used to protect data while maintaining its utility? |

---

| **Result** | **Data subject rights** |
| :----: | :--- |
| &nbsp;✅/❌/⚠️&nbsp; | Can users download or request all personal data related to them (data access request)? |
| &nbsp;✅/❌/⚠️&nbsp; | Is there an interface or process for users to request the deletion of their personal data? |
| &nbsp;✅/❌/⚠️&nbsp; | Can users withdraw their consent for data processing? |

---

| **Result** | **Documentation and communication** |
| :----: | :--- |
| &nbsp;✅/❌/⚠️&nbsp; | Is there a privacy policy available to users during registration and easily accessible? |
| &nbsp;✅/❌/⚠️&nbsp; | Are administrators and developers provided with documented data protection practices <br>and processing activities? |
| &nbsp;✅/❌/⚠️&nbsp; | Is there a documented data breach response process (e.g., how to notify authorities <br>and users of a breach)? |

---

**Symbols used:**  
✅ Pass (a note can be added)  
❌ Fail (a note can be added)  
⚠️ Attention (a note can be added)
