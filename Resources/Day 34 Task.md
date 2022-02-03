🎯 Day 34 Task


✅ THM Room


-------------------------------------------------------------------------------------------------------------------------

✅ eJPT


Networking (1-3)

1. Protocols - Study Guide 

2. Internet Protocols (IP) - Study Guide

3. Routing - Study Guide


Ports Cheatsheet 



**Note:- eJPT Material are very good for cracking the eJPT exam but I share some additional resource for learning !!!**

-------------------------------------------------------------------------------------------------------------------------


🔃 4.3 Identity Management Testing 


✅ 4.3.1 Test Role Definitions


Test Objectives


1. Identify and document roles used by the application.

2. Attempt to switch, change, or access another role.

3. Review the granularity of the roles and the needs behind the permissions given.


How to Test - Roles Identification


The tester should start by identifying the application roles being tested through any of the following methods:


1. Application documentation.

2. Guidance by the developers or administrators of the application.

3. Application comments.

4. Fuzz possible roles:


   a. cookie variable (e.g. role=admin, isAdmin=True)
   
   
   b. account variable (e.g. Role: manager)
   
   
   c. hidden directories or files (e.g. /admin, /mod, /backups)
   
   
   d. switching to well known users (e.g. admin, backups, etc.)


Switching to Available Roles


After identifying possible attack vectors, the tester needs to test and validate that they can access the available roles.


Some applications define the roles of the user on creation, through rigorous checks and policies, or by ensuring that the user’s role is properly protected through a signature created by the backend. Finding that roles exist doesn’t mean that they’re a vulnerability.


Review Roles Permissions

After gaining access to the roles on the system, the tester must understand the permissions provided to each role.

A support engineer shouldn’t be able to conduct administrative functionalities, manage the backups, or conduct any transactions in the place of a user.

An administrator shouldn’t have full powers on the system. Sensitive admin functionality should leverage a maker-checker principle, or use MFA to ensure that the administrator is conducting the transaction. A clear example on this was the Twitter incident in 2020.


Tools

The above mentioned tests can be conducted without the use of any tool, except the one being used to access the system.


To make things easier and more documented, one can use:


Burp's Authorize extension

ZAP 


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 



I am just Sharing what I learn for help Other's !!!


#infosec #learn365 #owasp 

