🎯 Day 33 Task


✅ THM Room


https://tryhackme.com/room/picklerick


-------------------------------------------------------------------------------------------------------------------------
✅ eJPT

✅ Introduction (4-7)

4. HTTP(s) Traffic Sniffing
5. Connecting to your first lab
6. HTTP(S) Traffic Sniffing
7. Binary Arithmetic Basics - Study Guide

Binary Arithmetic Calculator
https://www.rapidtables.com/convert/number/ 

**Note:- eJPT Material are very good for cracking the eJPT exam but I share some additional resource for learning !!!**

-------------------------------------------------------------------------------------------------------------------------

✅ 4.2.12 Test for Content Security Policy


Test Objectives - Review the Content-Security-Policy header or meta element to identify misconfigurations.

How to Test


To test for misconfigurations in CSPs, look for insecure configurations by examining the Content-Security-Policy HTTP response header or CSP meta element in a proxy tool:


1. unsafe-inline directive enables inline scripts or styles making the applications susceptible to XSS attacks.

2. unsafe-eval directive allows eval() to be used in the application.

3. Resources such as scripts can be allowed to be loaded from any origin by the use wildcard (*) source.


    a. Also consider wildcards based on partial matches, such as: https://* or *.cdn.com.
    
    
    b. Consider whether allow listed sources provide JSONP endpoints which might be used to bypass CSP or same-origin-policy.


4. Framing can be enabled for all origins by the use of wildcard (*) source for frame-ancestors directive.

5. Business critical applications should require to use a strict policy.

**Remediation**

Configure a strong content security policy which reduces the attack surface of the application. Developers can verify the strength of content security policy using online tools such as Google CSP Evaluator.

**Strict Policy**


A strict policy is a policy which provides protection against classical stored, reflected, and some of the DOM XSS attacks and should be the optimal goal of any team trying to implement CSP.


Google went ahead and set up a guide to adopt a strict CSP based on nonces. Based on a presentation at LocoMocoSec, the following two policies can be used to apply a strict policy:


Moderate Strict Policy:

```
script-src 'nonce-r4nd0m' 'strict-dynamic';
object-src 'none'; base-uri 'none';
```

Locked down Strict Policy:

```
script-src 'nonce-r4nd0m';
object-src 'none'; base-uri 'none';
```

Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 


I am just Sharing what I learn for help Other's !!!


#infosec #learn365 #owasp 
