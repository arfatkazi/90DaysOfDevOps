arfat@arfat-VirtualBox:~/90DaysOfDevOps/2026/day-06$ touch notes.txt
arfat@arfat-VirtualBox:~/90DaysOfDevOps/2026/day-06$ echo task1 > notes.txt 
arfat@arfat-VirtualBox:~/90DaysOfDevOps/2026/day-06$ cat notes.txt 
task1
arfat@arfat-VirtualBox:~/90DaysOfDevOps/2026/day-06$ echo "task2" >> notes.txt 
arfat@arfat-VirtualBox:~/90DaysOfDevOps/2026/day-06$ cat notes.txt 
task1
task2
arfat@arfat-VirtualBox:~/90DaysOfDevOps/2026/day-06$ echo "task3" | tee -a notes.txt 
task3
arfat@arfat-VirtualBox:~/90DaysOfDevOps/2026/day-06$ head -n 2 notes.txt 
task1
task2
arfat@arfat-VirtualBox:~/90DaysOfDevOps/2026/day-06$ tail -1 notes.txt 
task3
arfat@arfat-VirtualBox:~/90DaysOfDevOps/2026/day-06$ cat notes.txt 
task1
task2
task3

