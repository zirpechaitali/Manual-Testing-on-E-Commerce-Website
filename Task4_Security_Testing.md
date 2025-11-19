# **Task 4 – Security Testing**

## **Task Description**
- Test the application for vulnerabilities like **SQL Injection (SQLi)** and **Cross-Site Scripting (XSS)**.  
- Validate that user credentials are stored using **encryption or hashing** and not in plain text.  
- Ensure the login module displays **secure and generic error messages** that do not reveal system details.

---

## **Test Case**

### **Test Case ID:** TC_Security_004  
### **Title:** Check Login Security Measures  
### **Preconditions:** A valid test user account must be available.

---

## **Test Steps**
1. Attempt to inject SQL queries such as `' OR 1=1 --` into the login input fields.  
2. Try logging in using invalid credentials.  
3. Observe the type of error message displayed by the system.  
4. Attempt to enter XSS payloads (e.g., `<script>alert('XSS')</script>`) in the input fields to test sanitization.  
5. Verify backend password storage to ensure hashing/encryption is applied.

---

## **Expected Results**
- SQL Injection attempts should be blocked and not allow unauthorized access.  
- The system must not display any sensitive backend or database errors.  
- Error message should be generic like **“Invalid username or password”**.  
- XSS scripts should not execute or be reflected back in the response.  
- Passwords should be stored using secure hashing algorithms (e.g., bcrypt, SHA-256).

---

## **Actual Results**
- SQL Injection attempts were successfully blocked, preventing login bypass.  
- The login page did not expose database/system-level errors.  
- Error messages displayed were generic and secure, with no sensitive details revealed.  
- XSS payloads did not execute — the system sanitized the input correctly.  
- Backend credentials were confirmed to be hashed, ensuring secure storage.

---

## **Status**
**✔ Passed**  
All security validation checks matched expected outcomes. The login module follows secure authentication best practices.
