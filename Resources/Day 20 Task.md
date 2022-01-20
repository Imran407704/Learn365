🎯 Day 20 Task

✅ Recon Techniques


https://securib.ee/beelog/the-best-bug-bounty-recon-methodology/


https://www.bugcrowd.com/resources/webinars/practical-recon-techniques-for-bug-hunters-pen-testers/


https://infosecsanyam.medium.com/bug-bounty-methodology-ttp-tactics-techniques-and-procedures-v-2-0-2ccd9d7eb2e2


✅ TryHackMe Room


https://tryhackme.com/room/pythonbasics


✅ 4.1.8 Fingerprint Web Application Framework


Test Objectives
Fingerprint the components being used by the web applications.

How to Test

1. HTTP headers
2. Cookies
3. HTML source code
4. Specific files and folders
5. File extensions
6. Error messages


1. HTTP headers


Identifying a web framework by X-Powered-By field in the HTTP response header. Use netcat command -  nc 127.0.0.1 80
This methodology doesn’t work in 100% of cases,It is possible to easily disable X-Powered-By header by a proper configuration. 

2. Cookies
Identifying a web framework by Cookies field in the HTTP request header but it is possible to change the name of cookies

3. HTML Source Code


4. Specific Files and Folders
Use directory brute forcing on a target with known folder and filenames and monitoring HTTP-responses to enumerate server content.


5. File Extensions : Here are some common web file extensions and associated technologies:


.php – PHP


.aspx – Microsoft ASP.NET


.jsp – Java Server Pages


6. Error Messages


You can see the Error Messages on the Web page 


✅ Tools


1. WhatWeb
2. Wappalyzer

Github Repo
https://github.com/Imran407704/Learn365

Note- I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 

I am just Sharing what I learn for help Other's !!!

#infosec #learn365 #owasp 
