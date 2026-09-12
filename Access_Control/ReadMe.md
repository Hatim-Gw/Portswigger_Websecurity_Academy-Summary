
# PortSwigger Web Security Academy — [Access Control](https://portswigger.net/web-security/access-control)

## Objective
Build a practical understanding of access control vulnerabilities where the web application authenticates the user, but it fails to verify the user's privileges(authorization flaws).

## Tools
- Burp Suite Community


## Labs Completed 
1. [Unprotected admin functionality](https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality)
2. [Unprotected admin functionality with unpredictable URL](https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality-with-unpredictable-url)
3. [User role controlled by request parameter](https://portswigger.net/web-security/access-control/lab-user-role-controlled-by-request-parameter)


## Steps Performed
- **Unprotected admin functionality**: Identified that the application relied on hiding the  administration panel's URL rather than a permission check. Located the URL inside the `/robots.txt` and accessed `/admintstration-panel` without any authentication or authorization check and deleted the victim's account from the server.
- **Unprotected admin functionality with unpredictable URL**: same as the previous lab; the only difference was the unpredictable URL, which was leaked in `the home page's source`.

<img width="1603" height="1342" alt="image" src="https://github.com/user-attachments/assets/9a189595-f991-429a-bdb7-72aa33edc459" />


- **User role controlled by request parameter**: Logged in as a regular user, intercepted the `http request` to the `/admin` panel using Burp Suite Community, then changed the cookie parameter to `admin = true`, then resent the request with admin privileges.

