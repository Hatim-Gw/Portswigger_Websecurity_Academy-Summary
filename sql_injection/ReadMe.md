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
- Break the original query using a single quote ` ' ` which closes the string, allowing the attacker to inject SQL query, and it is going to be treated as code rather than a string.
- Bypass filters using ` '-- ` which comments the rest of the query (it's essential in every SQL injection)
- UNION Attcak: `UNION SELECT`  First, determine the number of columns returned by the original query using `UNION SELECT NULL, NULL, {continue passing NULL  till it returns 200, not an error}--` then pull data from different DB tables.
- Extracting users and passwords from an unknown schema by listing the tables of the database to identify the table; after that, retrieve the columns of that table; eventually, pull the users' data based on the columns and the table.
- Using database-specific queries to deal with each kind of database, which can be found on this page: [SQL injection cheat sheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)
- when the original query returns only a single column, it's necessary  to use the concatenation operator` || ` such as ` 'UNION SELECT username || '-' || password--`, to retrieve the whole data at once


## Problem encountered 
I got confused about the leading quote in UNION attack. It was not clear to me why a query like `Gifts' UNION SELECT ...` needed a `'`; it turns out it is used because the application wraps the user input in single quotes, so by adding another single quote, it closes the string.

Locating the real data after schema discovery. After listing all database tables through  `information_schema.tables`, the relevant table wasn't obviously named `users`. It appeared as a randomized name `users_dzdwqp` among dozens of Postgres system tables. Had to specifically query `information_schema.columns WHERE table_name='users_dzdwqp'--` to find the actual column names before the final extraction query could be written.
