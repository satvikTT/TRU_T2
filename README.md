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
- **Date**: 13-06-2025
