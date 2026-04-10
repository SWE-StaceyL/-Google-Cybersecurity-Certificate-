# SQL Filtering Portfolio Project – Cybersecurity Analysis

---

# **Project Description**

In this project, I acted as a security analyst investigating potential security incidents within an organization. Using SQL, I queried data from the `log_in_attempts` and `employees` tables to identify suspicious login activity and retrieve employee information for system updates. I applied filtering techniques using operators such as `AND`, `OR`, `NOT`, and `LIKE` to extract relevant data efficiently.

---

# **1. Retrieve After-Hours Failed Login Attempts**

### SQL Query

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00:00' AND success = 0;
```

### Explanation

This query retrieves all login attempts that:

* Occurred after **18:00 (6 PM)** → `login_time > '18:00:00'`
* Were **unsuccessful** → `success = 0`

The `AND` operator ensures that both conditions must be true.

### Security Insight

This helps identify **suspicious login attempts outside business hours**, which may indicate unauthorized access or brute-force attacks.

---

# **2. Retrieve Login Attempts on Specific Dates**

### SQL Query

```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';
```

### Explanation

This query retrieves login attempts that occurred on:

* May 8, 2022
* May 9, 2022

The `OR` operator allows results that match **either date**.

### Security Insight

Useful for investigating **specific incident windows** and identifying unusual activity around known events.

---

# **3. Retrieve Login Attempts Outside of Mexico**

### SQL Query

```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```

### Explanation

* `LIKE 'MEX%'` matches:

  * `MEX`
  * `MEXICO`
* `%` is a wildcard representing any number of characters
* `NOT` excludes those matches

### Security Insight

Helps detect **foreign or unexpected login locations**, which could indicate compromised accounts.

---

# **4. Retrieve Employees in Marketing (East Building)**

### SQL Query

```sql
SELECT *
FROM employees
WHERE department = 'Marketing'
AND office LIKE 'East%';
```

###  Explanation

This query filters employees who:

* Work in the **Marketing department**
* Are located in offices starting with **East**

The `LIKE 'East%'` pattern matches all East building offices.

### Security Insight

Used to target **specific departments and locations** for updates or alerts.

---

# **5. Retrieve Employees in Finance or Sales**

### SQL Query

```sql
SELECT *
FROM employees
WHERE department = 'Finance'
OR department = 'Sales';
```

### Explanation

This query returns employees in either:

* Finance
* Sales

The `OR` operator allows either condition to be true.

### Security Insight

Useful when applying updates to **multiple high-risk departments** handling sensitive data.

---

# **6. Retrieve All Employees NOT in IT**

### SQL Query

```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```

### Explanation

* `NOT` excludes employees in the IT department
* Returns all other departments

### Security Insight

Ensures updates are applied only to **systems that have not yet been patched**.

---

# **Key SQL Concepts Demonstrated**

###  AND Operator

Used to combine multiple conditions where **all must be true**

###  OR Operator

Used when **any condition can be true**

### NOT Operator

Used to **exclude specific conditions**

### LIKE Operator

Used for **pattern matching**

* `%` wildcard represents any sequence of characters

### Date & Time Filtering

* Dates: `'YYYY-MM-DD'`
* Time: `'HH:MM:SS'`
* Enables **incident timeline analysis**

---

# **Summary**

In this project, I used SQL filtering techniques to investigate security incidents and retrieve targeted data from organizational databases. I applied logical operators such as `AND`, `OR`, and `NOT` to refine search results, and used `LIKE` with wildcards to match patterns. These queries enabled me to identify suspicious login activity, analyze access patterns, and retrieve employee data for security updates. This experience demonstrates my ability to use SQL in real-world cybersecurity scenarios, particularly in incident investigation and system monitoring.

---

# **Screenshots Section (To Add)**

 Insert screenshots here from your lab:

* After-hours failed login query results
* Date-based login query results
* Mexico filter query
* Employee queries

*(Tip: Label each screenshot clearly for recruiters)*

---

#  ****

This project demonstrates:

* Practical SQL skills
* Security-focused thinking
* Real-world incident investigation

 This is exactly the kind of work employers look for in:

* **SOC Analysts**
* **Cloud Security Engineers**
* **Cybersecurity Analysts**

---
