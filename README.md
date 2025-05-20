# FUTURE-CS_01

# Web Application Security Testing – DVWA

## 📌 Project Overview

**Project Title**: Web Application Security Testing  
**Tested Application**: [DVWA (Damn Vulnerable Web Application)]
**Tested By**: Rohan Sen  
**Email**: rohasnsen1104@gmail.com  
**Tools Used**: Burp Suite, SQLMap

This project demonstrates a hands-on web application security assessment conducted on DVWA — an intentionally vulnerable web application designed for practicing common web exploits. The primary objective was to identify, exploit, and document real-world vulnerabilities such as SQL Injection, Cross-Site Scripting (XSS), and Authentication flaws.

---

## 🛠️ Tools Used

- **Burp Suite**: For intercepting and manipulating HTTP requests/responses, and conducting brute-force attacks.
- **SQLMap**: For automated SQL injection detection and exploitation.
- **DVWA**: The intentionally vulnerable web application used as the test environment.

---

## 🔍 Methodology

1. **Reconnaissance**  
   Scanned the application to discover potential attack surfaces.

2. **Vulnerability Scanning**  
   Automated scanning using Burp Suite to identify common web vulnerabilities.

3. **Exploitation**  
   - **SQL Injection** tested via SQLMap and manual payloads.  
   - **XSS** tested using script injections in form inputs.  
   - **Authentication Flaws** tested using brute-force attack with Burp Intruder.

4. **Reporting**  
   Documented vulnerabilities found, exploitation techniques, and mitigation strategies.

---

## ⚠️ Vulnerabilities Identified

### 1. SQL Injection (SQLi)

- **Description**: Malicious SQL queries allowed unauthorized access.
- **Test Example**: `' OR '1'='1` in login input bypassed authentication.
- **Mitigation**:
  - Use parameterized queries.
  - Sanitize and validate user input.

### 2. Cross-Site Scripting (XSS)

- **Description**: Malicious scripts were executed in the browser.
- **Test Example**: `<script>alert('XSS')</script>` produced a popup.
- **Mitigation**:
  - Sanitize input and escape special characters.
  - Use Content Security Policy (CSP), HttpOnly, and SameSite cookie attributes.

### 3. Authentication Flaws (Brute-Force)

- **Description**: Unrestricted login attempts without lockout.
- **Method**:
  - Used Burp Intruder with common credentials list.
- **Mitigation**:
  - Enforce strong password policy.
  - Add CAPTCHA and rate limiting.
  - Implement multi-factor authentication (MFA).
  - Secure session tokens (Secure, HttpOnly, SameSite).

---

## 📋 Summary of Findings

| Vulnerability Type     | Description                            | Risk Level |
|------------------------|----------------------------------------|------------|
| SQL Injection          | Unfiltered input led to DB access      | High       |
| Cross-Site Scripting   | Unsanitized input executed scripts     | Medium     |
| Authentication Flaws   | Brute-force login success              | High       |

---

## ✅ Recommendations

- **Input Validation**: Sanitize and validate all inputs server-side.
- **Secure Authentication**: Use lockouts, CAPTCHA, and MFA.
- **Session Management**: Set Secure, HttpOnly, and SameSite flags.

---

## 📌 Conclusion

This assessment enhanced my understanding of web application vulnerabilities and testing methodologies. Using both manual and automated tools, I was able to successfully identify critical flaws in the DVWA application and recommend industry-standard mitigations.

---

