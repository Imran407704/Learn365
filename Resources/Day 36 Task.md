🎯 Day 36 Task


✅ 4.3.3 Test Account Provisioning Process


Test Objectives - Verify which accounts may provision other accounts and of what type.

How to Test


Determine which roles are able to provision users and what sort of accounts they can provision.

1. Is there any verification, vetting and authorization of provisioning requests?

3. Is there any verification, vetting and authorization of de-provisioning requests?
 
5. Can an administrator provision other administrators or just users?

7. Can an administrator or other user provision accounts with privileges greater than their own?
 
9. Can an administrator or user de-provision themselves?

11. How are the files or resources owned by the de-provisioned user managed? Are they deleted? Is access transferred?

Example


In WordPress, only a user’s name and email address are required to provision the user, as shown below:


De-provisioning of users requires the administrator to select the users to be de-provisioned, select Delete from the dropdown menu (circled) and then applying this action. The administrator is then presented with a dialog box asking what to do with the user’s posts (delete or transfer them).


Tools


While the most thorough and accurate approach to completing this test is to conduct it manually, HTTP proxy tools could be also useful.


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 


I am just Sharing what I learn for help Other's !!!


#infosec #learn365 #owasp 
