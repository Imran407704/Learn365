🎯 Day 27 Task


✅ THM Room


https://tryhackme.com/room/activerecon


✅ Web App Pentesting - HTTP Headers & Methods Video by 


https://youtu.be/8q5mc1AEtYo


✅ 4.2.6 Test HTTP Methods


Test Objectives

1. Enumerate supported HTTP methods.
2. Test for access control bypass.
3. Test XST vulnerabilities.
4. Test HTTP method overriding techniques.

How to Test

Discover the Supported Methods


To perform this test, the tester needs some way to figure out which HTTP methods are supported by the web server that is being examined. While the OPTIONS HTTP method provides a direct way to do that, verify the server’s response by issuing requests using different methods. This can be achieved by manual testing or something like the http-methods Nmap script.


To use the http-methods Nmap script to test the endpoint /index.php on the server localhost using HTTPS, issue the command:

```
nmap -p 443 --script http-methods --script-args http-methods.url-path='/index.php' localhost
```


Testing the PUT Method


1. Capture the base request of the target with a web proxy.
2. Change the request method to PUT and add test.html file and send the request to the application server.

```
PUT /test.html HTTP/1.1
Host: testing-website

<html>
HTTP PUT Method is Enabled
</html>
```

3. If the server response with 2XX success codes or 3XX redirections and then confirm by GET request for test.html file. The application is vulnerable.


Testing for Access Control Bypass


Find a page to visit that has a security constraint such that a GET request would normally force a 302 redirect to a log in page or force a log in directly. Issue requests using various methods such as HEAD, POST, PUT etc. as well as arbitrarily made up methods such as BILBAO, FOOBAR, CATS, etc. If the web application responds with a HTTP/1.1 200 OK that is not a log in page, it may be possible to bypass authentication or authorization


```
$ ncat www.example.com 80
HEAD /admin HTTP/1.1
Host: www.example.com

HTTP/1.1 200 OK
Date: Mon, 18 Aug 2008 22:44:11 GMT
Server: Apache
Set-Cookie: PHPSESSID=pKi...; path=/; HttpOnly
Expires: Thu, 19 Nov 1981 08:52:00 GMT
Cache-Control: no-store, no-cache, must-revalidate, post-check=0, pre-check=0
Pragma: no-cache
Set-Cookie: adminOnlyCookie1=...; expires=Tue, 18-Aug-2009 22:44:31 GMT; domain=www.example.com
Set-Cookie: adminOnlyCookie2=...; expires=Mon, 18-Aug-2008 22:54:31 GMT; domain=www.example.com
Set-Cookie: adminOnlyCookie3=...; expires=Sun, 19-Aug-2007 22:44:30 GMT; domain=www.example.com
Content-Language: EN
Connection: close
Content-Type: text/html; charset=ISO-8859-1
```


If the system appears vulnerable, issue CSRF-like attacks such as the following to exploit the issue more fully:


```
HEAD /admin/createUser.php?member=myAdmin
```
```
PUT /admin/changePw.php?member=myAdmin&passwd=foo123&confirm=foo123
```
```
CATS /admin/groupEdit.php?group=Admins&member=myAdmin&action=add
```


Using the above three commands, modified to suit the application under test and testing requirements, a new user would be created, a password assigned, and the user made an administrator, all using blind request submission


Testing for Cross-Site Tracing Potential

Note: in order to understand the logic and the goals of a cross-site tracing (XST) attack, one must be familiar with cross-site scripting attacks.


The TRACE method, intended for testing and debugging, instructs the web server to reflect the received message back to the client. This method, while apparently harmless, can be successfully leveraged in some scenarios to steal legitimate users’ credentials. This attack technique was discovered by Jeremiah Grossman in 2003, in an attempt to bypass the HttpOnly attribute that aims to protect cookies from being accessed by JavaScript. However, the TRACE method can be used to bypass this protection and access the cookie even when this attribute is set.


Test for cross-site tracing potential by issuing a request such as the following:


```
$ ncat www.victim.com 80
TRACE / HTTP/1.1
Host: www.victim.com
Random: Header

HTTP/1.1 200 OK
Random: Header
...
```


The web server returned a 200 and reflected the random header that was set in place. To further exploit this issue:


```
$ ncat www.victim.com 80
TRACE / HTTP/1.1
Host: www.victim.com
Attack: <script>prompt()</script>
```


The above example works if the response is being reflected in the HTML context.


Testing for HTTP Method Overriding


Some web frameworks provide a way to override the actual HTTP method in the request by emulating the missing HTTP verbs passing some custom header in the requests. The main purpose of this is to circumvent some middleware (e.g. proxy, firewall) limitation where methods allowed usually do not encompass verbs such as PUT or DELETE. The following alternative headers could be used to do such verb tunneling:


**X-HTTP-Method**


**X-HTTP-Method-Override**


**X-Method-Override**


In order to test this, in the scenarios where restricted verbs such as PUT or DELETE return a “405 Method not allowed”, replay the same request with the addition of the alternative headers for HTTP method overriding, and observe how the system responds. The application should respond with a different status code (e.g. 200) in cases where method overriding is supported.


The web server in the following example does not allow the DELETE method and blocks it:


```
$ ncat www.example.com 80
DELETE /resource.html HTTP/1.1
Host: www.example.com

HTTP/1.1 405 Method Not Allowed
Date: Sat, 04 Apr 2020 18:26:53 GMT
Server: Apache
Allow: GET,HEAD,POST,OPTIONS
Content-Length: 320
Content-Type: text/html; charset=iso-8859-1
Vary: Accept-Encoding
```
After adding the X-HTTP-Method header, the server responds to the request with a 200:

```
$ ncat www.example.com 80
DELETE /resource.html HTTP/1.1
Host: www.example.com
X-HTTP-Method: DELETE

HTTP/1.1 200 OK
Date: Sat, 04 Apr 2020 19:26:01 GMT
Server: Apache
```

Tools

1. Netcat 
2. cURL
3. BurpSuite/ZAP


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 


I am just Sharing what I learn for help Other's !!!


#infosec #learn365 #owasp 




