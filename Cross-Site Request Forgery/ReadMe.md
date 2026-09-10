# PortSwigger Web Security Academy - [Cross-site request forgery (CSRF)](https://portswigger.net/web-security/csrf)

## Objective
Build a practical understanding of CSRF vulnerabilities. CSRF is mainly about  how an attacker can trick the user's browser into sending `requests` to the user's logged-in websites by attaching the browsing cookies to them.

# Tools
Burp Suite Community
Burp suite browser

# Labs Completed
1. CSRF Vulnerability with no defence

# Steps Performed
- Logged in to the vulnerable website, then located the functionality of `hanging the email`.
- Looked into the `http request` in Burp Suite > Proxy > HTTP History, then opened the `post request` for changing the email
- Used [csrfshark](csrfshark.github.i), which is a free tool to generate proof-of-concept (PoC) exploits for CSRF vulnerabilities, to generate the `html body for my exploit server.`
- then posted the generated form into the exploit server, stored it, and tested it.

<img width="2222" height="704" alt="image" src="https://github.com/user-attachments/assets/72562424-8994-42ba-adab-f57dfb0aeb17" />

- Eventually, delivered it to the victim.

## Problems Encountered
- Misunderstanding where the exploit runs. Expected the vulnerability would be in the main application, similar to to  SQL injection, XSS, Auth vuln..., but figured out the CSRF works differently; it's hosted on another server and delivered to the victim via email or message.

- Assumed some techniques are required to get the user's cookie. Then, clarified that CSRF does not require knowing the user's cookie, and what surprised me was how browsers work by how they automatically attaching stored cookies to every request sent to that cookie's domain.
