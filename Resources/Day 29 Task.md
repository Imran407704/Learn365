🎯 Day 29 Task

✅ THM Room


https://tryhackme.com/room/sqlinjectionlm


✅ 4.2.8 Test RIA Cross Domain Policy


Test Objectives - Review and validate the policy files.


What are cross-domain policy files?

A cross-domain policy file specifies the permissions that a web client such as Java, Adobe Flash, Adobe Reader, etc. use to access data across different domains. For Silverlight, Microsoft adopted a subset of the Adobe’s crossdomain.xml, and additionally created it’s own cross-domain policy file: clientaccesspolicy.xml.


Whenever a web client detects that a resource has to be requested from other domain, it will first look for a policy file in the target domain to determine if performing cross-domain requests, including headers, and socket-based connections are allowed.


**Crossdomain.xml** vs. **Clientaccesspolicy.xml**

Most RIA applications support crossdomain.xml. However in the case of Silverlight, it will only work if the crossdomain.xml specifies that access is allowed from any domain. For more granular control with Silverlight, clientaccesspolicy.xml must be used.

Policy files grant several types of permissions:

1. Accepted policy files (Master policy files can disable or restrict specific policy files)
2. Sockets permissions
3. Header permissions
4. HTTP/HTTPS access permissions
5. Allowing access based on cryptographic credentials


An example of an overly permissive policy file:

```
<?xml version="1.0"?>
<!DOCTYPE cross-domain-policy SYSTEM
"http://www.adobe.com/xml/dtds/cross-domain-policy.dtd">
<cross-domain-policy>
    <site-control permitted-cross-domain-policies="all"/>
    <allow-access-from domain="*" secure="false"/>
    <allow-http-request-headers-from domain="*" headers="*" secure="false"/>
</cross-domain-policy>
```

How can cross domain policy files can be abused?

Overly permissive cross-domain policies.
Generating server responses that may be treated as cross-domain policy files.
Using file upload functionality to upload files that may be treated as cross-domain policy files.

Impact of Abusing Cross-Domain Access


1. Defeat CSRF protections.
2. Read data restricted or otherwise protected by cross-origin policies.

How to Test - Testing for RIA Policy Files Weakness

To test for RIA policy file weakness the tester should try to retrieve the policy files crossdomain.xml and clientaccesspolicy.xml from the application’s root, and from every folder found.

For example, if the application’s URL is http://www.owasp.org, the tester should try to download the files http://www.owasp.org/crossdomain.xml and http://www.owasp.org/clientaccesspolicy.xml.


For example, if the application’s URL is http://www.owasp.org, the tester should try to download the files http://www.owasp.org/crossdomain.xml and http://www.owasp.org/clientaccesspolicy.xml.

After retrieving all the policy files, the permissions allowed should be be checked under the least privilege principle. Requests should only come from the domains, ports, or protocols that are necessary. Overly permissive policies should be avoided. Policies with * in them should be closely examined.

Example
```
<cross-domain-policy>
    <allow-access-from domain="*" />
</cross-domain-policy>
```
Result Expected

1. A list of policy files found.
2. A list of weak settings in the policies.

✅ Tools - Nikto, BurpSuite/ZAP


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 

I am just Sharing what I learn for help Other's !!!

#infosec #learn365 #owasp 


