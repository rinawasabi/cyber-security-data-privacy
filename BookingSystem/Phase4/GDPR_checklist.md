# GDPR Compliance Checklist – Web-based Booking System

| **Result** | **Personal data mapping and minimization** |
| :----: | :--- |
| &nbsp;✅&nbsp; | All personal data collected and processed have been identified (including `username`, `password_hash`,<br> `role`, `birthdate`, `terms_accepted`).|
| &nbsp;✅&nbsp; | Only minimal and necessary information is collected to register as a user. |
| &nbsp;✅&nbsp; | The system prevents registration if the user’s birthdate is under 15 years old. |

---

| **Result** | **User registration and management** |
| :----: | :--- |
| &nbsp;✅&nbsp; | The registration form includes GDPR-compliant consent for processing<br> personal data ("I accept the Terms of Service".)|
| &nbsp;❌&nbsp; | Users can only view, but cannot edit or delete their own personal data on `/account`! |
| &nbsp;⚠️&nbsp; | The mechanism for the administrator to delete a reserver on the UI has<br> not been implemented. However, database-level deletion procedures exist.  |
| &nbsp;✅&nbsp; | Underage registration (under 15 years) and booking functionality are correctly restricted. |

---

| **Result** | **Booking visibility** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Bookings are visible to non-logged-in users without showing the reserver’s personal data. |
| &nbsp;✅&nbsp; | Personal data, including names and emails of bookers, are not exposed publicly or to unauthorized users. |

--- 

| **Result** | **Access control and authorization** |
| :----: | :--- |
| &nbsp;❌&nbsp; | A reserver can modify reservations made by another reserver (the reserver’s username can even be changed). |
| &nbsp;❌&nbsp; | Role-based access control between reserver and administrator is not fully implemented.<br>  Reservers can access API endpoints and view the list of users with emails. |
| &nbsp;⚠️&nbsp; |`booking_admin_logs` for admin actions exists but not active; privileges are broad and unmonitored. |

---

| **Result** | **Privacy by Design Principles** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Privacy by Default has been implemented, as the system only collects the minimum necessary data. |
| &nbsp;❌&nbsp; | Logs include `reserverUsername`, which could identify a user. |
| &nbsp;⚠️&nbsp; | Forms and system components are designed with data protection in mind. Overall design is privacy-focused;<br> however not perfect. |

---

| **Result** | **Data security** |
| :----: | :--- |
| &nbsp;✅&nbsp; | CSRF, XSS and SQL injection protections are successfully implemented and verified by the ZAP scan. |
| &nbsp;✅&nbsp; | Passwords are securely hashed using bcrypt. |
| &nbsp;⚠️&nbsp; | No formal backup/recovery process, relies on local Docker volume persistence. |
| &nbsp;✅&nbsp; | All personal data is stored locally on the host machine within the EU. |

---

| **Result** | **Data anonymization and pseudonymization** |
| :----: | :--- |
| &nbsp;⚠️&nbsp; | Personal data is partially anonymized. However, `username`, `user_id` and `birthdate`<br> should also be hashed. |
| &nbsp;⚠️&nbsp; | Partially pseudonymization techniques are used to protect data, <br>but username is saved as plaintext, which is not secure.|

---

| **Result** | **Data subject rights** |
| :----: | :--- |
| &nbsp;⚠️&nbsp; | Users can request all personal data related to them via email, but there is currently no download feature available on the UI. |
| &nbsp;⚠️&nbsp; | Users can request the deletion of their personal data via email, but no interface is available on the UI. |
| &nbsp;✅&nbsp; | Users can withdraw their consent for data processing anytime. |

---

| **Result** | **Documentation and communication** |
| :----: | :--- |
| &nbsp;✅&nbsp; | A privacy policy is available to users during registration and easily accessible. |
| &nbsp;✅&nbsp; | Administrators and developers are provided with documented data protection practices <br>and processing activities on `/privacypolicy`. |
| &nbsp;✅&nbsp; | A documented data for breach response process exists on `/privacypolicy`. |

---

**Symbols used:**  
✅ Pass (compliant)  
❌ Fail (not compliant)  
⚠️ Attention (partially compliant or needs improvement)
