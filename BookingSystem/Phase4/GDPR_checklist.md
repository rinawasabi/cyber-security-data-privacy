# GDPR Compliance Checklist – Web-based Booking System

| **Result** | **Personal data mapping and minimization** |
| :----: | :--- |
| &nbsp;✅&nbsp; | All personal data collected and processed have been identified (including username, password_hash,<br> role, birthdate, terms_accepted)|
| &nbsp;✅&nbsp; | Only minimal and necessary information is collected to register as a user |
| &nbsp;✅&nbsp; | The system prevents registration if the user’s birthdate is under 15 years old |

---

| **Result** | **User registration and management** |
| :----: | :--- |
| &nbsp;✅&nbsp; | The registration form includes GDPR-compliant consent for processing<br> personal data ("I accept the Terms of Service")|
| &nbsp;❌&nbsp; | Users can only view and cannot edit and delete their own personal data on `/account`! |
| &nbsp;⚠️&nbsp; | Mechanism for the administrator to delete a reserver on UI <br> has not been implemented. However, database-level deletion procedures exist |
| &nbsp;✅&nbsp; | Underage registration (under 15 years) and booking functionality are correctly restricted |

---

| **Result** | **Booking visibility** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Bookings is visible to non-logged-in users without showing Reserver's personal data |
| &nbsp;✅&nbsp; | Personal data including names and emails of bookers are not exposed<br> publicly or to unauthorized users |

--- 

| **Result** | **Access control and authorization** |
| :----: | :--- |
| &nbsp;❌&nbsp; | Other reserver can modify the reservation made by another reserver!<br> (Reserver username can be even changed) |
| &nbsp;❌&nbsp; | Role-based access control reserver vs. administrator is not fully implemented.<br> Reserver can access API endpoints and see the list of users with emails. |
| &nbsp;⚠️&nbsp; |　`booking_admin_logs` for admin actions exists but not active; privileges are broad and unmonitored. |

---

| **Result** | **Privacy by Design Principles** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Privacy by Default has been implemented since the system only collects the minimum data |
| &nbsp;❌&nbsp; | Logs include reserverUsername, which could identify a user! |
| &nbsp;✅&nbsp; | Forms and system components designed with data protection in mind<br> Overall design is privacy focused |

---

| **Result** | **Data security** |
| :----: | :--- |
| &nbsp;✅&nbsp; | CSRF, XSS and SQL injection protections are successfully implemented, verified by the ZAP scan |
| &nbsp;✅&nbsp; | Passwords are securely hashed using bcrypt |
| &nbsp;⚠️&nbsp; | No formal backup/recovery process, relies on local Docker volume persistence |
| &nbsp;✅&nbsp; | All personal data is stored locally on the host machine within the EU |

---

| **Result** | **Data anonymization and pseudonymization** |
| :----: | :--- |
| &nbsp;⚠️&nbsp; | Personal data is partially anonymized. However, `username`, `user_id` and `birthdate`<br> should be hashed |
| &nbsp;⚠️&nbsp; | Partially pseudonymization techniques are used to protect data, <br>but username is saved as plaintext, which is not safe|

---

| **Result** | **Data subject rights** |
| :----: | :--- |
| &nbsp;✅/❌/⚠️&nbsp; | Can users download or request all personal data related to them (data access request)? |
| &nbsp;✅/❌/⚠️&nbsp; | Is there an interface or process for users to request the deletion of their personal data? |
| &nbsp;✅/❌/⚠️&nbsp; | Can users withdraw their consent for data processing? |

---

| **Result** | **Documentation and communication** |
| :----: | :--- |
| &nbsp;✅&nbsp; | A privacy policy is available to users during registration and easily accessible |
| &nbsp;✅/❌/⚠️&nbsp; | Are administrators and developers provided with documented<br> data protection practices <br>and processing activities? |
| &nbsp;✅/❌/⚠️&nbsp; | Is there a documented data breach response process<br> (e.g., how to notify authorities <br>and users of a breach)? |

---

**Symbols used:**  
✅ Pass (a note can be added)  
❌ Fail (a note can be added)  
⚠️ Attention (a note can be added)
