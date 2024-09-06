# Vehicle_Record_Management_System
Vehicle Record Management System using PHP and MySQL

# Auditor:
Shouvik Dutta <a href="https://www.linkedin.com/in/shouvik-dutta/">@shouvik_dutta</a>

# Description: 
Blind SQL Injection detected in Vehicle Record Management Project

Index Page - Search button is vulnerable to Blind SQL Injection

The Vehicle Record Management system application contains a vulnerability in the `searchinputdata` parameter on the index page. This parameter is vulnerable to a Blind SQL Injection attack due to improper sanitization of user input. An attacker can manipulate the `searchinputdata` input to execute crafted SQL queries, allowing them to dump the entire database, as the application's responses vary based on the injected queries. This vulnerability can be exploited by sending malicious input through the search functionality and observing subtle changes in the application's behavior or response times.

Vulnerable Endpoint - /index.php
Vulnerable Parameter - `searchinputdata`

# PoCs

`Vulnerable URL: /index.php`
```
POST Request

POST / HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:129.0) Gecko/20100101 Firefox/129.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/png,image/svg+xml,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 55
Origin: http://localhost
Connection: close
Referer: http://localhost/
Cookie: PHPSESSID=77ucjdgusue0vgbu0ouv7kcrqu
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Priority: u=0, i

searchinputdata=BLIND_SQL_VULNERABLE&Submit=Submit
