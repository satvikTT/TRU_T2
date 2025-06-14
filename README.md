# Introduction to Web Application Security
## Objective
To understand common web application vulnerabilities by analyzing an intentionally vulnerable web application and using OWASP ZAP for scanning, exploiting, and mitigation recommendations.
---
## Tools Used:-
- **WebGoat** (vulnerable web application for practice)
- **OWASP ZAP** (vulnerability scanning and exploitation tool)
- **Web Browser** (Chrome/Firefox)
---
## Steps for Installation
1. Installing Webgoat
   - Install Java JDK from Oracle (required for WebGoat)
     ```bash
     https://www.oracle.com/java/technologies/javase-downloads.html
     ```
   - After installation, verify it:
     ```bash
     java -version
     ```
   - Download WebGoat _**.jar**_ from github:
     ```bash
     https://github.com/WebGoat/WebGoat/releases
     ```
   - Open Command Prompt in the download directory:
     ```bash
     java -jar webgoat-2025.3.jar
     ```
   - Then launch WebGoat at:
     ```bash
     http://localhost:8080/WebGoat
     ```
2. Installation of OWASP ZAP (for vulnerability scanning)
   - Downloading ZAP with default settings
     ```bash
     https://www.zaproxy.org/download/
     ```
   - Configure ZAP and change the configuration of port to 8888
     - As both works default on 8080 but using it already for WebGoat
3. Working
   - In ZAP's Sites pane add address of WebGoat
     ```bash
     http://localhost:8080
     ```
   - Select **Active Scan** to detect vulnerabilities
   - ZAP will report detected issues like:
     - SQL Injection
     - XSS
     - CSRF, etc.
4. After completion export the report in which ever suited format needed (pdf).
---
## Focus Areas for Vulnerability Identification

- **SQL Injection (SQLi):**  
  Deliberately attempt to inject malicious SQL statements — for example, by submitting inputs like ```' OR '1'='1``` in login forms or search fields. This helps determine if the application improperly handles user-supplied data in database queries, potentially allowing unauthorized access or data leakage.
- **Cross-Site Scripting (XSS):**  
  Assess input fields for inadequate output encoding by submitting harmless JavaScript payloads, such as ```<script>alert(1)</script>```. Observe whether these scripts execute in the browser, indicating that the application fails to neutralize untrusted input.
- **Cross-Site Request Forgery (CSRF):**  
  Examine forms and state-changing requests to identify the absence of protective anti-CSRF mechanisms (such as unique tokens). This vulnerability could allow malicious sites to perform unauthorized actions on behalf of an authenticated user.
---
## Manual Exploitation
1. SQL Injection (SQLi)
   - How it’s done:
     - Test input fields (login forms, search bars) with special characters like ' OR '1'='1.
     - Use simple payloads to bypass login or retrieve extra data.
     - Experiment with UNION SELECT to extract database tables and columns.
   - Goal:
     - Access, modify, or leak database information without permission.
2. Cross-Site Scripting (XSS)
   - How it’s done:
     - Enter harmless HTML or JavaScript in input fields (e.g., <script>alert(1)</script>).
     - See if the script runs in the browser.
     - Try different variations to bypass filters.
   - Goal:
     - Run malicious scripts in other users’ browsers to steal cookies or hijack sessions.
3. Cross-Site Request Forgery (CSRF)
   - How it’s done:
     - Identify forms or actions that change data (e.g., change password) without CSRF tokens.
     - Create a fake HTML form that auto-submits using the victim’s session.
     - Send the malicious link to the victim.
   - Goal:
     - Trick users into performing unwanted actions without their knowledge.
---
## Vulnerability Exploration and Verification

- **Develop a comprehensive understanding:**  
  For each identified vulnerability, carefully review the technical description and impact details provided by OWASP ZAP. Supplement this information with external research to understand real-world exploitation scenarios and consequences.

- **Perform controlled manual exploitation:**  
  - **For SQL Injection:**  
    Manually test input fields by injecting crafted SQL commands to bypass authentication, retrieve hidden data, or modify database content, validating whether user input is properly sanitized.
  - **For Cross-Site Scripting:**  
    Enter harmless script tags or payloads into comment sections, input boxes, or URL parameters to verify if the application executes them in the user's browser, which could lead to session hijacking or data theft.
  - **For Cross-Site Request Forgery:**  
    Craft custom HTML forms or use tools like Burp Suite's Repeater to submit unauthorized requests. Check whether these requests can successfully change user data or perform sensitive actions without appropriate server-side verification.
---
## Detected Vulnerabilities and Their Potential Harm

1. SQL Injection (SQLi)
   - SQL Injection occurs when an attacker can insert or manipulate SQL queries via user input fields.
   - Why it’s dangerous:
     - Attackers can read, modify, or delete database records.
     - It can lead to unauthorized data access, including sensitive info like passwords or financial data.
     - In some cases, it allows complete control over the database server.
2. Cross-Site Scripting (XSS)
   - XSS happens when an attacker injects malicious JavaScript into web pages viewed by other users.
   - Why it’s dangerous:
     - Attackers can steal cookies, session tokens, or other sensitive data.
     - They can impersonate victims and perform actions on their behalf.
     - It can spread malware or redirect users to malicious sites.
3. Cross-Site Request Forgery (CSRF)
   - CSRF tricks a logged-in user’s browser into sending unauthorized requests to a web app.
   - Why it’s dangerous:
     - It can lead to unwanted actions like changing passwords, transferring funds, or modifying account settings — all without user knowledge.
     - It exploits trust in the user’s session.
---
## Mitigation Measures for Common Web Vulnerabilities

1. Preventing SQL injection
   - Use prepared statements or parameterized queries instead of dynamic SQL.
   - Validate and sanitize all user inputs.
   - Use the principle of least privilege for database accounts.
2. Preventing Cross-Site Scripting (XSS)
   - Escape or encode user-generated content before displaying it.
   - Implement input validation and sanitization.
   - Use Content Security Policy (CSP) to limit script execution.
3. Preventing Cross-Site Request Forgery (CSRF)
   - Implement anti-CSRF tokens for forms and state-changing requests.
   - Use SameSite cookie attributes.
   - Require re-authentication for sensitive actions.
---
## Attachments

1. Screenshots of ZAP scan results
2. Screenshots for each manual exploit
3. HTML sample for CSRF test
4. Exported ZAP report
---
## Learning Outcomes

- Understood how attackers exploit common web vulnerabilities
- Used OWASP ZAP to identify threats in a web app
- Performed basic attacks on an intentionally vulnerable system
- Learned how to mitigate vulnerabilities effectively
---
#### Prepared By:
- **_Satvik Bhagat_**
- Internship: Cyber Security Internship @ The Red Users
- **Date**: 13-06-2025
