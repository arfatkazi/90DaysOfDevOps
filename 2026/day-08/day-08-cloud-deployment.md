# Day 08 – Cloud Server Setup: Docker, Nginx & Web Deployment

## Instance Details
- Cloud: AWS EC2 / Utho
- OS: Ubuntu / CentOS
- Public IP: <YOUR_PUBLIC_IP>

## Commands Used
### SSH
- `ssh -i your-key.pem ubuntu@<IP>` (AWS)  
  or `ssh root@<IP>` (Utho)

### Update + Install
- `sudo apt update && sudo apt upgrade -y`
- `sudo apt install -y docker.io`
- `sudo systemctl enable --now docker`
- `sudo apt install -y nginx`
- `sudo systemctl enable --now nginx`
- `sudo systemctl status nginx --no-pager`
- `sudo ss -lntp | grep :80`

### Logs
- `sudo tail -n 50 /var/log/nginx/access.log`
- `sudo tail -n 50 /var/log/nginx/error.log`
- `sudo bash -c 'echo "==== ACCESS LOG ====" > nginx-logs.txt'`
- `sudo bash -c 'tail -n 200 /var/log/nginx/access.log >> nginx-logs.txt'`
- `sudo bash -c 'echo -e "\n==== ERROR LOG ====" >> nginx-logs.txt'`
- `sudo bash -c 'tail -n 200 /var/log/nginx/error.log >> nginx-logs.txt'`
- `sudo chown $USER:$USER nginx-logs.txt`

### Download to Local
- `scp -i your-key.pem ubuntu@<IP>:~/nginx-logs.txt .` (AWS)  
  or `scp root@<IP>:~/nginx-logs.txt .` (Utho)

## Challenges Faced
- Example: Nginx page not opening because port 80 was not allowed in Security Group.
- Fix: Added inbound rule HTTP (80) from 0.0.0.0/0.

## What I Learned
- How to launch and access a cloud server via SSH
- Installing and managing services with `systemctl`
- Security group/firewall basics for web access (port 80)
- Where Nginx stores access/error logs
- Exporting logs to a file and downloading with SCP

## Why This Matters for DevOps
This is real production work: provisioning servers, remote access, deploying services, opening only required ports, and collecting logs for debugging and monitoring.
