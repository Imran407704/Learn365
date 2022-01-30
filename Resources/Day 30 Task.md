🎯 Day 30 Task


✅ THM Room


https://tryhackme.com/room/windowsfundamentals2x0x


✅ 4.2.9 Test File Permission


Test Objectives - Review and identify any rogue file permissions.

How to Test

In Linux, use ls command to check the file permissions. Alternatively, namei can also be used to recursively list file permissions.

```
namei -l /PathToCheck/
```

The files and directories that require file permission testing include but are not limited to:

1. Web files/directory
2. Configuration files/directory
3. Sensitive files (encrypted data, password, key)/directory
4. Log files (security logs, operation logs, admin logs)/directory
5. Executables (scripts, EXE, JAR, class, PHP, ASP)/directory
6. Database files/directory
7. Temp files /directory
8. Upload files/directory


Remediation

Set the permissions of the files and directories properly so that unauthorized users cannot access critical resources unnecessarily.

Tools - https://linux.die.net/man/1/namei


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 

I am just Sharing what I learn for help Other's !!!

#infosec #learn365 #owasp 
