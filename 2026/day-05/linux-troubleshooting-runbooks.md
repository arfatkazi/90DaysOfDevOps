# Day 05 — Linux Troubleshooting Runbook (CPU, Memory, Logs)

## Target service / process
Target for this drill: cron.service
Goal: take a quick health snapshot + review logs + write next steps.



1) Environment basics (2 commands)

Command 1 — Kernel + machine details
```bash
uname -a

cat /etc/os-release


mkdir -p /tmp/runbook-demo


cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo

systemctl status cron --no-pager


systemctl show -p MainPID --value cron

ps -o pid,ppid,pcpu,pmem,etime,comm -p <PID>

top -b -n 1 | head -n 20

free -h


df -h

du -sh /var/log

vmstat 1 5


ss -tulpn | head -n 50


curl -I www.google.com


journalctl -u cron -n 50 --no-pager


tail -n 50 /var/log/syslog

