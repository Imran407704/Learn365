🎯 Day 15 Task

✅ 4.1.3 Review Webserver Metafiles for Information Leakage

Objective 
1. Identify hidden or obfuscated paths and functionality through the analysis of metadata files.
2. Extract and map other information that could lead to better understanding of the systems at hand.

✅ How to Test

Spider/crawler, Google Dorks, Burpsuite/ZAP
1. robots.txt     - curl -O -Ss http://www.TARGET.TLD/robots.txt
2. Sitemap.xml  - wget --no-verbose https://www.TARGET.TLD/sitemap.xml
3. Security.txt  - wget --no-verbose https://www.linkedin.com/.well-known/security.txt 


https://TARGET.TLD/security.txt or https://TARGET.TLD/.well-known/security.txt


4. humans.txt   - wget --no-verbose  https://www.google.com/humans.txt

✅ Tools 

wget, BurpSuite, Dev Tools

✅ THM Room 

https://tryhackme.com/room/linuxfundamentalspart3

Github Repo
https://github.com/Imran407704/Learn365

Disclaimer- I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 

I am just Sharing what I learn for help Other's !!!

#infosec #learn365 #owasp 
