🎯 Day 39 Task


✅ 4.4.1 Testing for Credentials Transported over an Encrypted Channel


Test Objectives


1. Identify sensitive information transmitted through the various channels.

2. Assess the privacy and security of the channels used.


Example 1: Basic Authentication over HTTP


A typical example is the usage of Basic Authentication over HTTP. When using Basic Authentication, user credentials are encoded rather than encrypted, and are sent as HTTP headers. In the example below the tester uses curl to test for this issue. Note how the application uses Basic authentication, and HTTP rather than HTTPS.

```
 curl -kis http://example.com/restricted/
HTTP/1.1 401 Authorization Required
Date: Fri, 01 Aug 2013 00:00:00 GMT
WWW-Authenticate: Basic realm="Restricted Area"
Accept-Ranges: bytes Vary:
Accept-Encoding Content-Length: 162
Content-Type: text/html

<html><head><title>401 Authorization Required</title></head>
<body bgcolor=white> <h1>401 Authorization Required</h1>  Invalid login credentials!  </body></html>
```

Example 2: Form-Based Authentication Performed over HTTP


Another typical example is authentication forms which transmit user authentication credentials over HTTP. In the example below one can see HTTP being used in the action attribute of the form. It is also possible to see this issue by examining the HTTP traffic with an interception proxy.

```
<form action="http://example.com/login">
    <label for="username">User:</label> <input type="text" id="username" name="username" value=""/><br />
    <label for="password">Password:</label> <input type="password" id="password" name="password" value=""/>
    <input type="submit" value="Login"/>
</form>
```

Example 3: Cookie Containing Session ID Sent over HTTP


The Session ID Cookie must be transmitted over protected channels. If the cookie does not have the secure flag set, it is permitted for the application to transmit it unencrypted. Note below the setting of the cookie is done without the Secure flag, and the entire log in process is performed in HTTP and not HTTPS.

```
https://secure.example.com/login

POST /login HTTP/1.1
Host: secure.example.com
[...]
Referer: https://secure.example.com/
Content-Type: application/x-www-form-urlencoded
Content-Length: 188

HTTP/1.1 302 Found
Date: Tue, 03 Dec 2013 21:18:55 GMT
Server: Apache
Set-Cookie: JSESSIONID=BD99F321233AF69593EDF52B123B5BDA; expires=Fri, 01-Jan-2014 00:00:00 GMT; path=/; domain=example.com; httponly
Location: private/
Content-Length: 0
Content-Type: text/html
```

```
http://example.com/private

GET /private HTTP/1.1
Host: example.com
[...]
Referer: https://secure.example.com/login
Cookie: JSESSIONID=BD99F321233AF69593EDF52B123B5BDA;

HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 730
Date: Tue, 25 Dec 2013 00:00:00 GMT
```


Example 4: Password Reset, Change Password or Other Account Manipulation over HTTP


If the web application has features that allow a user to change an account or call a different service with credentials, verify all of those interactions use HTTPS. The interactions to test include the following:


1. Forms that allow users to handle a forgotten password or other credentials

2. Forms that allow users to edit credentials

3. Forms that require the user to authenticate with another provider (for example, payment processing)


Example 5: Testing Password Sensitive Information in Source Code or Logs


Use one of the following techniques to search for senstive information.


Checking if password or encyrption key is hardcoded in the source code or configuration files.

```
grep -r –E "Pass | password | pwd |user | guest| admin | encry | key | decrypt | sharekey " ./PathToSearch/
```


Checking if logs or source code may contain phone number, email address, ID or any other PII. Change the regular expression based on the format of the PII.


```
grep -r " {2\}[0-9]\{6\} " ./PathToSearch/

```


Remediation - Use HTTPS for the whole web site and redirect any HTTP requests to HTTPS.


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 


I am just Sharing what I learn for help Other's !!!


#infosec #learn365 #owasp 
