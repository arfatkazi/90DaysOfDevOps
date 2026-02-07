

## A) Process Management (CPU/RAM/kill)
- `ps aux` — list all processes (CPU/RAM, user, command)
- `ps -ef` — process list in full format (good for servers)
- `top` — live view of CPU/memory usage
- `htop` — better top (if installed), easy kill/sort
- `pgrep nginx` — find PID by process name
- `pkill nginx` — kill processes by name (careful)
- `kill <PID>` — stop a process gracefully
- `kill -9 <PID>` — force kill (last option)
- `nice -n 10 <cmd>` — run command with lower priority
- `renice 10 -p <PID>` — change priority of running process
- `uptime` — check load average quickly
- `free -h` — memory usage in human-readable format

## B) File System + Disk (space, files, search)
- `pwd` — show current directory
- `ls -lah` — list files with size + hidden files
- `cd /path` — change directory
- `mkdir -p dir/subdir` — create folders (with parents)
- `cp file1 file2` — copy file
- `mv old new` — move/rename
- `rm -rf folder` — delete folder forcefully (VERY careful)
- `du -sh * | sort -h` — find which folders take space
- `df -h` — disk usage by filesystem
- `find /var/log -type f -name "*.log" -mtime -7` — find logs modified in last 7 days
- `tail -n 50 file.log` — last 50 lines of a file
- `tail -f file.log` — follow logs live (real-time)
- `grep -n "error" file.log` — search keyword with line numbers
- `less file.log` — open large file safely (scroll/search)
- `wc -l file.log` — count lines (quick size check)

## C) Networking Troubleshooting (must know)
- `ip addr` — see IP addresses/interfaces (replacement for ifconfig)
- `ip route` — show routing table (default gateway)
- `ping -c 4 google.com` — check basic connectivity + DNS
- `dig google.com` — check DNS resolution (very useful)
- `curl -I https://example.com` — check HTTP response headers (health check)
- `curl -v http://IP:PORT` — debug connection + response details
- `ss -tulpn` — show listening ports + which process owns them
- `lsof -i :8080` — find what is using a specific port
- `traceroute google.com` — see network path (if installed)

## D) systemd + Logs (service debugging)
- `systemctl status <service>` — check service health + last logs
- `systemctl restart <service>` — restart service after changes
- `systemctl --failed` — list failed services
- `journalctl -u <service> -e --no-pager` — latest logs for a service
- `journalctl -xe --no-pager` — system-wide recent errors (quick incident view)

## E) Permissions + Users (common real issues)
- `whoami` — show current user
- `id` — show user/groups
- `chmod 644 file` — set file permissions (rw-r--r--)
- `chmod +x script.sh` — make script executable
- `chown user:user file` — change file owner
- `sudo -l` — check what sudo permissions you have

