🎯 Day 24 Task


✅ THM Room 


https://tryhackme.com/room/vulnversity


✅ 4.2.3 Test File Extensions Handling for Sensitive Information

Test Objectives


1. Dirbust sensitive file extensions, or extensions that might contain raw data (e.g. scripts, raw data, credentials, etc.).
2. Validate that no system framework bypasses exist on the rules set. 


How to Test


Forced Browsing


Submit requests with different file extensions and verify how they are handled. The verification should be on a per web directory basis. Verify directories that allow script execution. Web server directories can be identified by scanning tools which look for the presence of well-known directories. In addition, mirroring the web site structure allows the tester to reconstruct the tree of web directories served by the application.
If the web application architecture is load-balanced, it is important to assess all of the web servers. This may or may not be easy, depending on the configuration of the balancing infrastructure. In an infrastructure with redundant components there may be slight variations in the configuration of individual web or application servers. This may happen if the web architecture employs heterogeneous technologies (think of a set of IIS and Apache web servers in a load-balancing configuration, which may introduce slight asymmetric behavior between them, and possibly different vulnerabilities).

Example

The tester has identified the existence of a file named connection.inc. Trying to access it directly gives back its contents, which are:
```
<?
    mysql_connect("127.0.0.1", "root", "password")
        or die("Could not connect");
?>
```
The following file extensions should never be returned by a web server, since they are related to files which may contain sensitive information or to files for which there is no reason to be served.

File Upload


1. file.phtml gets processed as PHP code.
2. FILE~1.PHT is served, but not processed by the PHP ISAPI handler.
3. shell.phPWND can be uploaded.
4. SHELL~1.PHP will be expanded and returned by the OS shell, then processed by the PHP ISAPI handler.


Gray-Box Testing


Performing white-box testing against file extensions handling amounts to checking the configurations of web servers or application servers taking part in the web application architecture, and verifying how they are instructed to serve different file extensions.


If the web application relies on a load-balanced, heterogeneous infrastructure, determine whether this may introduce different behavior.


✅ Tools


HTTrack


wget 


curl


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 

I am just Sharing what I learn for help Other's !!!

#infosec #learn365 #owasp 


