1 . uname -r kernel release version (the Linux kernel version your system is running)

2 . uname -a all kernel/system info in one line

3 . cat /etc/os-release OS / distribution info (Ubuntu version, name, ID)

4 . ps -p 1 -o pid,comm,args we can break it down more  

    ps:  show you Process Status
    Shows information about running processes
   
    -p: means pick a specific PID.

    so -p 1 : show only  info about process id  1 

    -o:  means ouptut 
    
    pid: the process ID here it will be 1
    
    comm: the command name short name like systemd

    args: the full command line used to start it 
    
    full command is ps -p 1 -o pid,comm,args


5. echo $$  is a special shell variable in bash that  means your current bash shell process ID is 2345

6 . ps -o pid,ppid,cmd -p $$ break it sown for you 
    
    ps: show process info

   -p $$: show info only for the PID that equals your shell PID

   pid: PID of this process (your bash)
   
   ppid: Parent PID of bash (who started bash)
    
   cmd: the command line (like bash)

    output :   PID  PPID CMD
              2345  2210 bash

7 . sleep 120 &

    sleep 120: run a program that does nothing for 120 seconds
    & : run it in the background


8 . echo $! breadown for you
    echo: used for print what you want 
    $!is another special bash variable.
It expands to the PID of the most recent background command


9. ps -o pid,ppid,state,cmd -p $!

    ps:  show process info

   -p $!:  show only the process whose PID is $! (your sleep PID)

    -o pid,ppid,state,cmd

10. kill $! If you don’t want to wait 120 seconds


11. top -p <PID>

12. htop <PID>

13. sleep 60 &
    ps -o pid,state,cmd -p $!

    if you want to stop use ctrl + z 


14 . use sleep 300  and then press ctrl + z and check using this command  jobs -l   ps -o pid,state,cmd -p <PID> you can see T it is stopped state 

15 .  first do 
        `sudo apt-get install nginx`
        `sudo apt-get install docker.io` 
        and then check 
       ` sudo systemctl status nginx`
        u can do 
        ` sudo journalctl  -u  nginx  -n 50 --no-pager `
        

16 . `sudo systemctl status cron`
     `sudo systemctl restart cron`
     `sudo systemctl status cron`


17 . yes > /dev/null &  
    print yes   > /dev/null throws output away 
    & runs in background 


18 . ps aux --sort=-%mem | head

    ps aux : list all processes
    --sort=-%mem : sort by memory usage descending
    head :  show top 10 
    you can do tail 10 also show last 10 
        




