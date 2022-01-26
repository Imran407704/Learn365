🎯 Day 26 Task


✅ THM Room


https://tryhackme.com/room/linuxfundamentalspart2


✅ 4.2.5 Enumerate Infrastructure and Application Admin Interfaces


Test Objectives

Identify hidden administrator interfaces and functionality.


How to Test

Black-Box Testing


1. Directory and file enumeration. An administrative interface may be present but not visibly available to the tester. Attempting to guess the path of the administrative interface may be as simple as requesting: /admin or /administrator etc.. or in some scenarios can be revealed within seconds using Google dorks.
2. There are many tools available to perform brute forcing of server contents, see the tools section below for more information. A tester may have to also identify the filename of the administration page. Forcibly browsing to the identified page may provide access to the interface.
3. Comments and links in source code. Many sites use common code that is loaded for all site users. By examining all source sent to the client, links to administrator functionality may be discovered and should be investigated.
4. Reviewing server and application documentation. If the application server or application is deployed in its default configuration it may be possible to access the administration interface using information described in configuration or help documentation. Default password lists should be consulted if an administrative interface is found and credentials are required.
5. Publicly available information. Many applications such as WordPress have default administrative interfaces .
6. Alternative server port. Administration interfaces may be seen on a different port on the host than the main application. For example, Apache Tomcat’s Administration interface can often be seen on port 8080.
7. Parameter tampering. A GET or POST parameter or a cookie variable may be required to enable the administrator functionality. Clues to this include the presence of hidden fields such as:

```
<input type="hidden" name="admin" value="no">
```
or in a cookie:

```
Cookie: session_cookie; useradmin=0
```
Once an administrative interface has been discovered, a combination of the above techniques may be used to attempt to bypass authentication. If this fails, the tester may wish to attempt a brute force attack. In such an instance the tester should be aware of the potential for administrative account lockout if such functionality is present.


Gray-Box Testing


Each web framework may have its own admin default pages or path. For example

WebSphere:
```
/admin
/admin-authz.xml
/admin.conf
/admin.passwd
/admin/*
/admin/logon.jsp
/admin/secure/logon.jsp
```
PHP:
```
/phpinfo
/phpmyadmin/
/phpMyAdmin/
/mysqladmin/
/MySQLadmin
/MySQLAdmin
/login.php
/logon.php
/xmlrpc.php
/dbadmin
```
FrontPage:
```
/admin.dll
/admin.exe
/administrators.pwd
/author.dll
/author.exe
/author.log
/authors.pwd
/cgi-bin
```
WebLogic:
```
/AdminCaptureRootCA
/AdminClients
/AdminConnections
/AdminEvents
/AdminJDBC
/AdminLicense
/AdminMain
/AdminProps
/AdminRealm
/AdminThreads
```
WordPress:
```
wp-admin/
wp-admin/about.php
wp-admin/admin-ajax.php
wp-admin/admin-db.php
wp-admin/admin-footer.php
wp-admin/admin-functions.php
wp-admin/admin-header.php
```

Tools 


1. BurpSuite/ZAP

3. https://github.com/vanhauser-thc/thc-hydra


Default-Wordlist :- https://cirt.net/passwords


Logins.txt :- https://github.com/fuzzdb-project/fuzzdb/blob/master/discovery/predictable-filepaths/login-file-locations/Logins.txt


Common admin/debugging parameters :- https://github.com/fuzzdb-project/fuzzdb/blob/master/attack/business-logic/CommonDebugParamNames.txt


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 


I am just Sharing what I learn for help Other's !!!


#infosec #learn365 #owasp 
