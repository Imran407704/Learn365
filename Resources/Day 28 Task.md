🎯 Day 28 Task


✅ THM Room


https://tryhackme.com/room/walkinganapplication


✅ 4.2.7 Test HTTP Strict Transport Security (HSTS)


The HTTP Strict Transport Security (HSTS) feature lets a web application inform the browser through the use of a special response header that it should never establish a connection to the specified domain servers using un-encrypted HTTP. Instead, it should automatically establish all connection requests to access the site through HTTPS. It also prevents users from overriding certificate errors.

The HTTP strict transport security header uses two directives:

1. **max-age**: to indicate the number of seconds that the browser should automatically convert all HTTP requests to HTTPS.
2. **includeSubDomains**: to indicate that all related sub-domains must use HTTPS.
3. **preload Unofficial**: to indicate that the domain(s) are on the preload list(s) and that browsers should never connect without HTTPS.


Here’s an example of the HSTS header implementation:

```
Strict-Transport-Security: max-age=31536000; includeSubDomains
```

The use of this header by web applications must be checked to find if the following security issues could be produced:


1. Attackers sniffing the network traffic and accessing the information transferred through an un-encrypted channel.
2. Attackers exploiting a manipulator in the middle attack because of the problem of accepting certificates that are not trusted.
3. Users who mistakenly entered an address in the browser putting HTTP instead of HTTPS, or users who click on a link in a web application which mistakenly indicated use of the HTTP protocol.


Test Objectives


Review the HSTS header and its validity.


How to Test


The presence of the HSTS header can be confirmed by examining the server’s response through an intercepting proxy or by using curl as follows:

```
curl -s -D- https://owasp.org | grep -i strict
Strict-Transport-Security: max-age=31536000
```


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 

I am just Sharing what I learn for help Other's !!!

#infosec #learn365 #owasp 


