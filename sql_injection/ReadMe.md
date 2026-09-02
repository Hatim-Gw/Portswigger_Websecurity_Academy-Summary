# PortSwigger Web Security Academy SQL Injection

## Objective
Build a practical understanding of SQL injection vulnerabilities using PortSwigger's web Security Academy labs. The goal was to move beyond the theory and actually detect, exploit, and reason through different SQL injection attacks.

## Tools
- Burp Suite Community
- Burp Suite Browser
- 
## Labs completed
1. SQL injection vulnerability in WHERE clause allowing retrieval of hidden data
2. SQL injection vulnerability allowing login bypass
3. SQL injection attack, querying the database type and version on Oracle
4. SQL injection attack, querying the database type and version on MySQL and Microsof
5. SQL injection attack, listing the database contents on non-Oracle databases
6. SQL injection attack, listing the database contents on Oracle
7. SQL injection UNION attack, determining the number of columns returned by the query
8. SQL injection UNION attack, finding a column containing text
9. SQL injection with filter bypass via XML encoding

## Steps performed
Worked through each lab using Burp Suite Community to intercept and modify  `GET requests` :
-Break the original query using a single quote ` ' ` which closes the string, allowing the attacker to inject SQL query, and it is going to be treated as code rather than a string.
