# Day 14 – Networking Fundamentals & Hands-on Checks

## OSI vs TCP/IP

### OSI Model
1. Physical
2. Data Link
3. Network
4. Transport
5. Session
6. Presentation
7. Application

### TCP/IP Model
1. Link
2. Internet
3. Transport
4. Application

TCP/IP merges multiple OSI layers.

---

## Where Protocols Sit

- IP → Network layer
- TCP/UDP → Transport layer
- HTTP/HTTPS → Application layer
- DNS → Application layer

Example:
curl https://google.com  
Application (HTTP) → TCP → IP → Link

---

## Hands-on Results

### Identity
Command: hostname -I  
Output: <paste your IP>

### Reachability
Command: ping -c 4 google.com  
Observation: 0% packet loss, ~20ms latency average.

### Path
Command: traceroute google.com  
Observation: ~8–15 hops before reaching destination.

### Listening Ports
Command: ss -tulpn  
Found: SSH running on port 22.

### DNS Check
Command: dig google.com  
Resolved IP: <paste IP>

### HTTP Check
Command: curl -I https://google.com  
Status: 200 OK

### Connection Snapshot
Command: netstat -an | head  
Observed both LISTEN and ESTABLISHED states.

---

## Mini Port Probe

Port tested: 22 (SSH)

Command:
nc -zv localhost 22

Result: Connection succeeded.

If failed:
Next check would be:
- systemctl status ssh
- sudo ufw status

---

## Reflection

### Fastest signal when broken?
ping or curl -I — immediate connectivity signal.

### If DNS fails?
Inspect Application layer → check /etc/resolv.conf, dig, nslookup.

### If HTTP 500 shows?
Application layer issue → check service logs (journalctl -u nginx).

### Two follow-up checks in real incident:
- Check firewall (ufw / security group)
- Check service status (systemctl)
