🎯 Day 14 Task


✅ 4.1.2 Fingerprint Web Server


_Objective_ 


Determine the version and type of a running web server to enable further discovery of any known vulnerabilities.


✅ How to Test


Nmap - **nmap -sV --script=banner TARGET**

  
Note :  Exposed server information is not necessarily in itself a vulnerability, it is information that can assist attackers in exploiting other vulnerabilities that may exist

  
✅ Remediation 

  
1. Obscuring web server information in headers, such as with Apache’s mod_headers module.
2. Using a hardened reverse proxy server to create an additional layer of security between the web server and the Internet.
3. Ensuring that web servers are kept up-to-date with the latest software and security patches.

  
✅ THM Room 
  
  
https://tryhackme.com/room/linuxprivescarena

Github Repo
  
  
https://github.com/Imran407704/Learn365

  
**Disclaimer- I am making notes from Official OWASP Website you can check it from here**
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 

  
I am just Sharing what I learn for help Other's !!!

  
#infosec #learn365 #owasp 
