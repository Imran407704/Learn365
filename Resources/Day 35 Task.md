🎯 Day 35 Task

✅ eJPT

🔃 Networking (4)


Link Layer Devices & Protocols - Study Guide

-------------------------------------------------------------------------------------------------------------
✅ 4.3.2 Test User Registration Process


Test Objectives - Verify that the identity requirements for user registration are aligned with business and security requirements.


Validate the registration process.


How to Test - Verify that the identity requirements for user registration are aligned with business and security requirements:


1. Can anyone register for access?


3. Are registrations vetted by a human prior to provisioning, or are they automatically granted if the criteria are met?


5. Can the same person or identity register multiple times?


6. Can users register for different roles or permissions?


8. What proof of identity is required for a registration to be successful?


10. Are registered identities verified?


Validate the registration process:

1. Can identity information be easily forged or faked?


3. Can the exchange of identity information be manipulated during registration?


Example

In the WordPress example below, the only identification requirement is an email address that is accessible to the registrant.


In contrast, in the Google example below the identification requirements include name, date of birth, country, mobile phone number, email address and CAPTCHA response. While only two of these can be verified (email address and mobile number), the identification requirements are stricter than WordPress.


Remediation


Implement identification and verification requirements that correspond to the security requirements of the information the credentials protect.


Tools


BurpSuite/ZAP


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 


I am just Sharing what I learn for help Other's !!!


#infosec #learn365 #owasp 
