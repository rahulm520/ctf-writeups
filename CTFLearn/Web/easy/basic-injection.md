# Basic Injection

Platform: CTFLearn  
Category: Web  
Difficulty: Easy  

---

## 1. Challenge Overview

This challenge involved a web page that accepted user input and returned database records.  
The task was to test whether the input handling was secure or vulnerable to SQL injection.  
It focused on understanding how improper input validation can expose backend data.

---

## 2. Objective

The objective was to manipulate the input in a way that would cause the application to return all database records and reveal the hidden flag.

---

## 3. Environment & Tools Used

- Web browser  
- Page source inspection  
- Manual input testing  

---

## 4. Step-by-Step Approach

I started by interacting with the input field to understand how the application behaved.  
When I entered a normal value, the page returned a single record, which suggested that the input was being used in a database query.

Next, I checked the page source and noticed hints indicating that the backend was using a SQL query with user-controlled input.

Based on this behavior, I assumed the query structure was similar to a `SELECT` statement with a `WHERE` clause.

To test this, I entered a condition that would always evaluate to true.  
By doing this, the query logic was altered to ignore the original filter and return all rows.

This resulted in multiple records being displayed, including the one containing the flag.

---

## 5. Key Finding / Vulnerability

The application was vulnerable to SQL injection due to unsanitized user input.  
User input was directly inserted into a SQL query without validation or parameterization.

This allowed modification of the query logic.

---

## 6. Result

I was able to retrieve all database records from the application, including the one containing the flag.

---

## 7. Security Impact (Real-World Mapping)

In a real application, this type of vulnerability could allow attackers to:
- Extract sensitive user data  
- Bypass authentication  
- Modify or delete database content  

This represents a high-risk issue for any production system.

---

## 8. Mitigation / Defensive Takeaway

- Use parameterized queries or prepared statements  
- Validate and sanitize all user input  
- Apply least-privilege access to database accounts  

---

## 9. Learning Outcome

- Understood how SQL injection affects query logic  
- Improved ability to recognize unsafe input handling  
- Learned the importance of secure database interaction  
