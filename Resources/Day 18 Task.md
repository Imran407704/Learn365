🎯 Day 18 Task


✅ P1 Bugs WriteUp


https://medium.com/@harrmahar/how-i-get-my-first-p1-sensitive-information-disclosure-using-wpscan-c2fba00ac361


https://medium.com/@sw33tlie/finding-a-p1-in-one-minute-with-shodan-io-rce-735e08123f52


https://medium.com/techiepedia/my-easiest-critical-bug-81c341a0d6d4


✅ 4.1.6 Identify Application Entry Pointss


Test Objectives


1. Identify possible entry and injection points through request and response analysis.


Requests


1. Identify where GETs are used and where POSTs are used.


3. Identify all parameters used in a POST request (these are in the body of the request).


5. Within the POST request, pay special attention to any hidden parameters. When a POST is sent all the form fields (including hidden parameters) will be sent in the body of the HTTP message to the application. These typically aren’t seen unless a proxy or view the HTML source code is used. In addition, the next page shown, its data, and the level of access can all be different depending on the value of the hidden parameter(s).


7. Identify all parameters used in a GET request (i.e., URL), in particular the query string (usually after a ? mark).


9. Identify all the parameters of the query string. These usually are in a pair format, such as foo=bar. Also note that many parameters can be in one query string such as separated by a &, \~, :, or any other special character or encoding.


11. Identify all the parameters of the query string. These usually are in a pair format, such as foo=bar. Also note that many parameters can be in one query string such as separated by a &, \~, :, or any other special character or encoding.


13. Also pay attention to any additional or custom type headers not typically seen (such as debug: false).


Responses


1. Identify where new cookies are set (Set-Cookie header), modified, or added to.


3. Identify where there are any redirects (3xx HTTP status code), 400 status codes, in particular 403 Forbidden, and 500 internal server errors during normal responses (i.e., unmodified requests).


5. Also note where any interesting headers are used. For example, Server: BIG-IP indicates that the site is load balanced. Thus, if a site is load balanced and one server is incorrectly configured, then the tester might have to make multiple requests to access the vulnerable server, depending on the type of load balancing used.


✅ Tools


Burpsuite/ZAP


Note- I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 


I am just Sharing what I learn for help Other's !!!


#infosec #learn365 #owasp 
