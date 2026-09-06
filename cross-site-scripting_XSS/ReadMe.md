# PortSwigger Web Security Academy - [Cross-Site Scripting (XSS)](https://portswigger.net/web-security/cross-site-scripting)

## Objective
Build a practical understanding of Cross-Site Scripting, which is known as XSS where the attacker injects JavaScript script that executes in another user's browser(device).
This write-up covers the three foundational XSS types: reflected, stored, and DOM.

## Tools
- Google chrome browser


## Labs Completed
1. Reflected XSS into HTML context with nothing encoded
2. Stored XSS into HTML context with nothing encoded
3. DOM XSS in `document.write` sink using source `location.search`


## Steps Performed

- **Reflected XSS**: inject a `<script>` payload directly into the search parameter that the server returns into the page, causing the script to execute immediately when the page loads.
<img width="1500" height="758" alt="image" src="https://github.com/user-attachments/assets/ce499406-848d-49da-af53-720a39d84bb4" />

- **Stored XSS**: inject a `<script>` payload into *a comment*(input field), which the web application stores and then loads and executes the injected script for every user who views the web page.

<img width="1529" height="547" alt="image" src="https://github.com/user-attachments/assets/a6987d9c-ab87-47ee-95ad-d0b54ca418a2" />

- **DOM XX**: inject the script on the client side into `location.search` where it passes it into `document.write`; then, after the page is rendered, it executes the injected script.

<img width="1744" height="1194" alt="image" src="https://github.com/user-attachments/assets/22a66731-9434-4e30-a51b-ddc3fb3bceb3" />

- 

