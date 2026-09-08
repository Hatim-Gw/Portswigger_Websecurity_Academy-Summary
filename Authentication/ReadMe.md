
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
- **Usernames and Passwords enumeration**: used Burp Suite to watch the `http history` then identified the `post request` to the login page and sent it to the `intruder` page; afterwards, added a `list` of prepared usernames, then started the attack, and finally, the results page showed each `request` and its `response` to distinguish the right username. *This technique can be used for the password too.*

<img width="2543" height="1251" alt="username_enumeration_via_different_responses" src="https://github.com/user-attachments/assets/50064f9a-a915-461f-a1bf-22d6812bdf17" />


- **2FA simple bypass**: this vulnerability lab started with logging in to the user's account, then the next step was to copy the URL of the user's account `/myaccount`, then log in to the victim's account. When the application asked for the verification code, it was bypassed by simply editing the URL by adding `/myaccount`. 
This technique shows how a simple flow can make the whole 2FA process useless.*

<img width="1694" height="936" alt="t2fa_bypass" src="https://github.com/user-attachments/assets/4915fe0a-72dd-4df2-945e-47dfab44ef61" />

- **Password reset broken logic**: Examined the reset password `post request` using Burp Suite, which had a validation problem where the request parameter could be interfered  and changed to match any username to reset its password instead of only the user's password.

<img width="3047" height="775" alt="passwordreset" src="https://github.com/user-attachments/assets/ac20ed89-5efa-4282-90f3-3ef483e92820" />


## Problems Encountered
- Assuming all three vulnerabilities required a similar technique, but figured out it is more about testing and exploiting logic flaws, which are things that developers won't assume users will skip pages or they will read `http requests` and modify them.



