🎯 Day 31 Task


✅ THM Room


https://tryhackme.com/room/burpsuitebasics


✅ 4.2.10 Test for Subdomain Takeover


✅ https://0xpatrik.com/subdomain-takeover-basics/


Test Objectives

1. Enumerate all possible domains (previous and current).
2. Identify forgotten or misconfigured domains.

How to Test

Black-Box Testing

The first step is to enumerate the victim DNS servers and resource records. There are multiple ways to accomplish this task, for example DNS enumeration using a list of common subdomains dictionary, DNS brute force or using web search engines and other OSINT data sources.


Using the dig command the tester looks for the following DNS server response messages that warrant further investigation:


NXDOMAIN

SERVFAIL

REFUSED

no servers could be reached.


Testing DNS A, CNAME Record Subdomain Takeover


Perform a basic DNS enumeration on the victim’s domain (victim.com) using dnsrecon:

```
$ ./dnsrecon.py -d victim.com
[*] Performing General Enumeration of Domain: victim.com
...
[-] DNSSEC is not configured for victim.com
[*]      A subdomain.victim.com 192.30.252.153
[*]      CNAME subdomain1.victim.com fictioussubdomain.victim.com
...
```


Identify which DNS resource records are dead and point to inactive/not-used services. Using the dig command for the CNAME record:


```
$ dig CNAME fictioussubdomain.victim.com
; <<>> DiG 9.10.3-P4-Ubuntu <<>> ns victim.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NXDOMAIN, id: 42950
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1
```


The following DNS responses warrant further investigation: NXDOMAIN.


To test the A record the tester performs a whois database lookup and identifies GitHub as the service provider:


```
$ whois 192.30.252.153 | grep "OrgName"
OrgName: GitHub, Inc.
```

The tester visits subdomain.victim.com or issues a HTTP GET request which returns a “404 - File not found” response which is a clear indication of the vulnerability.


Testing NS Record Subdomain Takeover


Identify all nameservers for the domain in scope:

```
$ dig ns victim.com +short
ns1.victim.com
nameserver.expireddomain.com
```


In this fictious example the tester checks if the domain expireddomain.com is active with a domain registrar search. If the domain is available for purchase the subdomain is vulnerable.


The following DNS responses warrant further investigation: SERVFAIL or REFUSED.


Gray-Box Testing

The tester has the DNS zone file available which means DNS enumeration is not necessary. The testing methodology is the same.



Tools - 

Subdomain Enum Tools - Amass, Subfinder, Assetfinder

dig

dnsrecon


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 

I am just Sharing what I learn for help Other's !!!

#infosec #learn365 #owasp 




