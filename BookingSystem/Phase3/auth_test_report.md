# **Authorization Main Testing List**


---

###  **Guest**

**✅ Can do**
* Can access the main page `/`
* Can register her/himself (if they are over 15 years old with strong password) on `/register`
* Can see other people's reservations without reserver usernames on `/`
* Can access `/api/reservations`, this is okay because it does not show reserver usernames
* Can access `/resources` (Found via Gobuster & wfuzz), which should not be available for guests
* Can access `api/resources` (Found via wfuzz) and see every resource made by guests + admin!⚠️
* Can access `/api/users` (Found via wfuzz), which should only visible to admin!⚠️
* Can access `/api/reservations/2`(Found via wfuzz), reserver_token also visible!⚠️

---

**❌ Cannot do**
List every action that a *Guest* is blocked from doing.
* Cannot login without registering first on `/login`
* Cannot add a new resource on `/resource`
* Cannot add a new reservation on `/reservation`
* Cannot access 

---

**Role summary**
* Crucial vulnability found ->`api/resources` and `/api/users` were visible, they should not be open for guests.
* `/resources` was accessible and able to add a new resource, which should not be allowed.
* `/api/reservations/` can be visible since the reserver username is hidden, but when the ID is specified, reserver username is visible. This is not along with the role.
  
  

---

###  **Reserver**

**✅ Can do**
List actions a *Reserver* can do according to specs + actual test results.
Include visible pages **and** API endpoints.

* Can login with own credentials on `/login`
* Can manage own booking events on `/resources`
* Can create/manage reservations on `/reservation`
* 

---

**❌ Cannot do**
List actions a *Reserver* is correctly blocked from.
* Cannot 
* Cannot 
* Cannot
* Cannot

---

**Role summary**
*
  

---

###  **Administrator**


**✅ Can do**
* Can see people's reservations with reservor usernames on `/`
* Can add new resources on `/resources`”
* Can add new reservations on `/reservation`”
* Canmanage (update/delete) reservations made by reservors on `/reservation?id=`
* Can access Main page without logging in after registering (redirected) from `/register` to `/`
---

**❌ Cannot do**
List prohibited behaviors, if any, or incorrect implementation issues.

* Cannot 
* Cannot
* Cannot

---

**Role summary**
*
  
---
