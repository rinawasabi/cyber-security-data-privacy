# **Authorization Main Testing List**


---

###  **Guest**

**✅ Can do**
* Can access the main page `/`
* Can register her/himself if they are over 15 years old with strong password on `/register`
* Can see other people's reservations without reserver usernames on `/`
* Can see http://localhost:8003/api/reservations
* Can access `/resources` (Found in Gobuster & wfuzz)
* Can access http://localhost:8003/api/users (Found in wfuzz)
* Can access http://localhost:8003/api/reservations/2

---

**❌ Cannot do**
List every action that a *Guest* is blocked from doing.
* Cannot login without registering first on `/login`
* Cannot add a new resource on `/resource`
* Cannot add a new reservation on `/reservation`
* Cannot access 

---

**Role summary**
* Crucial vulnability found -> Can access `/resources` which should not be visible.
* 
  

---

###  **Reserver**

**✅ Can do**
List actions a *Reserver* can do according to specs + actual test results.
Include visible pages **and** API endpoints.

* “Can login with own credentials on `/login`”
* “Can manage own booking events on `/resources`”
* “Can create/manage reservations on `/reservation`”
* 

---

**❌ Cannot do**
List actions a *Reserver* is correctly blocked from.
* “Cannot 
* “Cannot 
* “Cannot
* “Cannot

---

**Role summary**
*
  

---

###  **Administrator**


**✅ Can do**
* “Can see people's reservations with reservor usernames on `/`”
* “Can add new resources on `/resources`”
* “Can add new reservations on `/reservation`”
* “Canmanage (update/delete) reservations made by reservors on `/reservation?id=`”
* “Can access Main page without logging in after registering (redirected) from `/register` to `/`“
---

**❌ Cannot do**
List prohibited behaviors, if any, or incorrect implementation issues.

* “Cannot ”
* “Cannot ”

---

**Role summary**
*
  
---
