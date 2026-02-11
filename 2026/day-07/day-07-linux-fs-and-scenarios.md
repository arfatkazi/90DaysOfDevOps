Day 07 — Linux File System Hierarchy & Scenario-Based Practice

Core Directories



sudo ls -l  /root 


ls -l /home


ls -l /etc


ls -l /var/log


ls -l /tmp


ls -l /bin


ls -l /usr/bin


ls -l /opt




du -sh /var/log/*  2>/dev/null | sort -h | tail -5


cat /etc/os-release

cat /etc/hostname

ls -la ~


# Part  2 : Scenarios-Based practice 


Question: How do you check if the 'nginx' service is running?


sudo systemctl status nginx

systemctl list-units --type=service 

systemctl is-enabled nginx 



Scenario 1: Service Not Starting

systemctl status myapp

journalctl -u myapp -n 50

systemctl is-enabled myapp


Scenario 2: High CPU Usage

Your manager reports that the application server is slow.
You SSH into the server. What commands would you run to identify
which process is using high CPU?


top 

htop 

ps aux --sort=%cpu | head -10 


Scenario 3: Finding Service Logs

A developer asks: "Where are the logs for the 'docker' service?"
The service is managed by systemd.
What commands would you use?



sudo systemctl status docker --no-pager

journalctl -u docker  -n 50 --no-pager 


journal -u docker   -f 


Scenario 4: File Permissions Issue

A script at /home/user/backup.sh is not executing.
When you run it: ./backup.sh
You get: "Permission denied"

What commands would you use to fix this?
Hint:

First: Check what permissions the file has
Understand: Files need 'x' (execute) permission to run
Fix: Add execute permission with chmod
Step-by-step solution structure:

Step 1: Check current permissions
Command: ls -l /home/user/backup.sh
Look for: -rw-r--r-- (notice no 'x' = not executable)

Step 2: Add execute permission
Command: chmod +x /home/user/backup.sh

Step 3: Verify it worked
Command: ls -l /home/user/backup.sh
Look for: -rwxr-xr-x (notice 'x' = executable)

Step 4: Try running it
Command: ./backup.sh












