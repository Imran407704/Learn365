🎯 Day 21 Task


✅ 4.1.9 Fingerprint Web Application (Merged into 4.1.8)

✅ THM Room 


https://tryhackme.com/room/historyofmalware

✅ 4.1.10 Map Application Architecture

Test Objectives
Understand the architecture of the application and the technologies in use.

How to Test

1. Web Server
Simple applications may run on a single server, which can be identified by Date, Server, Last-Modified, ETag, Accept-Ranges, Content-Length, Connection, Content-Type

2. Platform-as-a-Service (PaaS)
It is possible to identify the use of PaaS, as the application may use a specific domain name (for example, applications deployed on Azure App Services will have a *.azurewebsites.net domain - although they may also use custom domains)

3. Serverless
In a Serverless model, the developers provide code which is directly run on a hosting platform as individual functions, rather than as an traditional larger web application deployed in a webroot.
For example, AWS Lambda functions will typically return the following headers:

X-Amz-Invocation-Type


X-Amz-Log-Type


X-Amz-Client-Context

4. Microservices - 
In a microservice-based totally architecture, the software API is made of more than one discrete offerings, instead of strolling as a monolithic software. The services themselves often run inner bins (normally with Kubernetes). Although they're generally behind a single API gateway and area.

5. Static Storage - 
Many applications store static content on dedicated storage platforms, rather than hosting it directly on the main web server. The two most common platforms are Amazon’s S3 Buckets, and Azure’s Storage Accounts, and can be easily identified by the domain names:


1. Amazon S3 Buckets are either BUCKET.s3.amazonaws.com or s3.REGION.amazonaws.com/BUCKET
2. Azure Storage Accounts are ACCOUNT.blob.core.windows.net

6. Database - 
a. Port scanning the server and looking for any open ports associated with specific databases.
b. Triggering SQL (or NoSQL) related error messages (or finding existing errors from a search engine.

Other Database - 
Windows, IIS and ASP.NET often use Microsoft SQL server. 
Embedded systems often use SQLite.
PHP often uses MySQL or PostgreSQL.
APEX often uses Oracle.

7. Authentication

a. Web server configuration
b. Local user accounts in a database.
c. An existing central authentication source such as Active Directory or an LDAP server
d. Single Sign-On (SSO) with either an internal or external provider.

8. Third Party Services and APIs

Almost all web applications include third party resources that are loaded or interacted with by the client. These can include:

a.Active content (such as scripts, style sheets, fonts, and iframes).
b.Passive content (such as images and videos).
c.External APIs.
d.Social media buttons.
e.Advertising networks.
f.Payment gateways.

Network Components

1. Reverse Proxy

a. Acting as a load balancer or web application firewall.
b. Allowing multiple applications to be hosted on a single IP address or domain (in subfolders).
c. Implementing IP filtering or other restrictions.
d. Caching content from the back end to improve performance.

It is not always possible to detect a reverse proxy (especially if there is only a application behind it), but you can often sometimes identify it by:

a. A mismatch between the front end server and the back end application (such as a Server: nginx header with an ASP.NET application).
b. This can sometimes lead to request smuggling vulnerabilities.
c. Duplicate headers (especially the Server header).
d. Multiple applications hosted on the same IP address or domain (especially if they use different languages).

Load Balancer
Load balancers can be difficult to detect, but can sometimes be identified by making multiple requests and examining the responses for differences, such as:

a. Inconsistent system times.
b. Different internal IP addresses or hostnames in detailed error messages.
c. Different addresses returned from Server-Side Request Forgery (SSRF).

Content Delivery Network (CDN)

When testing a site behind a CDN, you should bear in mind the following points:

a. The IPs and servers belong to the CDN provider, and are likely to be out of scope for infrastructure testing.
b. Many CDNs also include features like bot detection, rate limiting, and web application firewalls.
c. CDNs usually cache content, so any changes made to the back end website may not appear immediately.Security Components

Security Components

1. Network Firewall
Most web servers will be protected by a packet filtering or stateful inspection firewall, which blocks any network traffic that is not required. To detect this, perform a port scan of the server and examine the results.

2. Web Application Firewall (WAF)
A WAF can be deployed in multiple locations, including:

a. On the web server itself.
b. On a separate virtual machine or hardware appliance.
c. In the cloud in front of the back end server.

If a cloud-based WAF is in use, then it may be possible to bypass it by directly accessing the back end server, using the same methods discussed in the Content Delivery Network section.

Github Repo
https://github.com/Imran407704/Learn365

Note- I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 

I am just Sharing what I learn for help Other's !!!

#infosec #learn365 #owasp 


