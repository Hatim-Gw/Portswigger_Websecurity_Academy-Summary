
# PortSwigger Web Security Academy - [Authentication vulnerabilities](https://portswigger.net/web-security/authentication)

## Objective
Build a practical understanding of authentication vulnerabilities. These vulnerabilities are based on identification flaws in the user and password login page, 2FA bypass, and broken reset password logic.

## Tools:
- Burp Suite Community
- Burp Suite Browser


## Labs Completed
1. [Username enumeration via different responses](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-different-responses)
2. [2FA simple bypass](https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-simple-bypass)
3. [Password reset broken logic](https://portswigger.net/web-security/authentication/other-mechanisms/lab-password-reset-broken-logic)

## Steps Performed
- **Usernames and Passwords enumeration**: using Burp Suite to watch the `http history` then identify the `post request` to the login page, and send it to the `intruder` page; afterwards, add a `list` of prepared usernames, next, start the attack, and finally, the results page shows each `request` and its `response` to distiush the right username. This technique can be used for the password too.

<img width="2543" height="1251" alt="username_enumeration_via_different_responses" src="https://github.com/user-attachments/assets/50064f9a-a915-461f-a1bf-22d6812bdf17" />


- **2FA simple bypass**: 
