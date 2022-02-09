🎯 Day 40 Task


✅ 4.4.2 Testing for Default Credentials


Test Objectives

1. Determine whether the application has any user accounts with default passwords.

2. Review whether new user accounts are created with weak or predictable passwords.


How to Test - Testing for Vendor Default Credentials

The first step to identifying default passwords is to identify the software that is in use.

Once the software has been identified, try to find whether it uses default passwords, and if so, what they are. This should include:

1. Searching for “[SOFTWARE] default password”.

2. Reviewing the manual or vendor documentation.

3. Checking common default password databases, such as CIRT.net, SecLists Default Passwords or DefaultCreds-cheat-sheet.

4. Inspecting the application source code (if available).

5. Installing the application on a virtual machine and inspecting it.

6. Inspecting the physical hardware for stickers (often present on network devices).

If a default password can’t be found, try common options such as:

1. “admin”, “password”, “12345”, or other common default passwords.

2. An empty or blank password.

3. The serial number or MAC address of the device.

If the username is unknown, there are various options for enumerating users, discussed in the Testing for Account Enumeration guide. Alternatively, try common options such as “admin”, “root”, or “system”.



Testing for Organisation Default Passwords


When staff within an organisation manually create passwords for new accounts, they may do so in a predictable way. This can often be:

1. A single common password such as “Password1”.

2. Organisation specific details, such as the organisation name or address.

3. Passwords that follow a simple pattern, such as “Monday123” if account is created on a Monday.

Testing for Application Generated Default Passwords

If the application automatically generates passwords for new user accounts, these may also be predictable. In order to test these, create multiple accounts on the application with similar details at the same time, and compare the passwords that are given for them.


The passwords may be based on:

1. A single static string shared between accounts.

2. A hashed or obfuscated part of the account details, such as md5($username).

3. A time-based algorithm.

4. A weak pseudo-random number generator (PRNG).


Tools - BurpSuite Intruder, Hydra

#infosec #learn365 #owasp

