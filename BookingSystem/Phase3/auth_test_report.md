# **Authorization Main Testing List**


---

###  **Guest**

**✅ Can do**
* Can access the main page `/`
* Can register her/himself (if they are over 15 years old with strong password) on `/register`
* Can see other people's reservations without reserver usernames on `/`
* Can access `/api/reservations`, this is okay because it does not show reserver usernames
* Can access `/resources` (found via Gobuster & wfuzz), which should not be available for guests! ⚠️
* Can access `api/resources` (found via wfuzz) and see every resource made by guests + admin! ⚠️
* Can access `/api/users` (found via wfuzz), which should only be visible to admin! ⚠️
* Can access `/api/reservations/{id}`(found via wfuzz), reserver_token also visible! ⚠️

---

**❌ Cannot do**
List every action that a *Guest* is blocked from doing.
* Cannot login without registering first on `/login`
* Cannot add a new resource on `/resource` when accessed from `/`
* Cannot add a new reservation on `/reservation`

---

**Observation**
* **Crucial vulnability found** ->`api/resources` and `/api/users` are visible to guests, they should not be open for guests.
* `/resources` was accessible and able to add a new resource, which should not be allowed.
* `/api/reservations/` can be visible since the reserver username is hidden, but when the ID is specified`/api/reservations/{id}`, reserver username is visible. This is violating role-based access control.
  
  

---

###  **Reserver**

**✅ Can do**
* Can login with own credentials on `/login`
* Can manage own booking events on `/resources`
* Can create/manage reservations on `/reservation`
* Can access `/api/reservations/`, which is expected
* Can access `/api/reservations/{id}`(found via wfuzz), reserver_token also visible! ⚠️
* Can access `/api/users` (found via wfuzz), which should only be visible to admin! ⚠️
* Can access `/api/resources`(found via wfuzz) and see every resource made by guests + admin! ⚠️


---

**❌ Cannot do**
* Cannot manage reservations made by others on `/reservation?id={id}`
* Cannot 
* Cannot
* Cannot

---

**Observation**
 `/api/reservations/` can be visible, but when the ID is specified`/api/reservations/{id}`, reserver_token is visible. This means Reserver can see other Reserver's token and attackers could use this to modify or cancel reservations.

---

###  **Administrator**


**✅ Can do**
* Can see people's reservations with reservor usernames on `/`
* Can add new resources on `/resources`”
* Can add new reservations on `/reservation`”
* Can access `/register`” and `/login`”
* Can manage (update/delete) reservations made by reservors on `/reservation?id=`
* Can access Main page without logging in after registering (redirected) from `/register` to `/`
* Can access `/api/users` (found via wfuzz), which is expected!
* Can access `/api/reservations` (found via wfuzz), which is expected for this role!
* Can access `/api/reservations/{id}`(found via wfuzz), which is expected!
* Can access `/api/resources` (found via wfuzz), which is expected!

  
---

**❌ Cannot do**
* Cannot delete users - `curl DELETE` command was tested, but received `HTTP 303` response ⚠️
* Cannot add new users - `curl POST` command was denied (`HTTP 303` response) ⚠️
* Cannot edit existing users - `curl PUT` command was denied (`HTTP 303` response) ⚠️

---

**Observation**
* The visiblity of pages and API end points is role-appropriate.
  However, editing, deleting and adding users were impossible for this role. These actions should be permitted for the admin role.
  
---

### **Overall Summary & Reflection**
The Booking System has crucial vulnabilities when checked based on roles.
This assignment was truly fun to complete. It was also my first time to use Wfuzz tool, and seeing and experiencing how it works was interesting.
This time, somehow the ZAP automated scan took quite a long time and used significant amount of CPU. Other than this, everything worked fine and I appreciate this experience!
