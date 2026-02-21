# Day 15 – Networking Concepts: DNS, IP, Subnets & Ports

## Task 1 – DNS

When typing google.com:
1. Browser checks cache
2. DNS resolver queries authoritative server
3. DNS returns IP
4. Browser connects via TCP

Record Types:
- A → IPv4
- AAAA → IPv6
- CNAME → Alias
- MX → Mail server
- NS → Name server

dig output:
A record IP: 142.250.206.142

TTL: 10

dig +noall +answer google.com
---

## Task 2 – IP Addressing

IPv4 = 32-bit address written as 4 octets.

Private IP ranges:
- 10.0.0.0/8
- 172.16.0.0/12
- 192.168.0.0/16

My private IP:
127.0.0.1/8

---

## Task 3 – CIDR & Subnetting

/24 → 255.255.255.0 → 254 usable hosts
/16 → 255.255.0.0 → 65,534 usable hosts
/28 → 255.255.255.240 → 14 usable hosts

Why subnet?
- Security
- Organization
- Traffic control

---

## Task 4 – Ports

Port = service endpoint.

Common ports:
22 SSH
80 HTTP
443 HTTPS
53 DNS
3306 MySQL
6379 Redis
27017 MongoDB

ss output:
ss -tulpn | grep 22
udp   UNCONN 0      0                            224.0.0.251:5353       0.0.0.0:*    users:(("brave",pid=4842,fd=109)) 
tcp   LISTEN 0      4096                             0.0.0.0:22         0.0.0.0:*                                      
tcp   LISTEN 0      4096                                [::]:22            [::]:* 
---

## Task 5 – Putting It Together

curl myapp.com:8080 uses:
DNS → TCP → IP → Port 8080

Database issue checks:
Ping
Port test
Firewall
Service status

---

## What I Learned
- DNS translates names to IP
- CIDR determines network size
- Ports allow multiple services on one IP
