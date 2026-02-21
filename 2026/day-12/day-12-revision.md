# Day 12 – Breather & Revision (Days 01–11)

## Mindset Review
- I reviewed my Day 01 plan and confirmed my goal is to become strong in Linux fundamentals before moving deeper into DevOps tools.
- File permissions and ownership were slightly tricky but now much clearer.
- I will focus next on process management and service debugging.

---

## Commands I Re-Ran Today

### Process & Services
- ps aux
- systemctl status nginx
- journalctl -u nginx -n 10

Observation:
- I verified nginx service is active and saw recent log entries.
- Learned how to quickly check if a service is running and healthy.

### File & Permission Practice
- echo "revision test" >> revision.txt
- chmod 640 revision.txt
- sudo chown tokyo revision.txt
- ls -l revision.txt

Observation:
- I now understand how numeric permissions work.
- Ownership affects access more than I previously realized.

### User/Group Check
- id tokyo
- groups berlin

---

## Mini Self-Check

### 1) Which 3 commands save you the most time right now, and why?

- ls -l → instantly shows permissions and ownership.
- systemctl status → quickly checks if service is running.
- chmod → fixes permission issues immediately.

---

### 2) How do you check if a service is healthy?

First commands I run:

- systemctl status <service>
- systemctl is-enabled <service>
- journalctl -u <service> -n 20

---

### 3) How do you safely change ownership and permissions?

Example:

sudo chown user:group filename
sudo chmod 640 filename

Always verify using:

ls -l filename

---

### 4) What will I focus on improving in the next 3 days?

- Strong understanding of processes
- Better confidence with logs (journalctl)
- More comfort with recursive permissions and ownership

---

## Key Takeaways

- Permissions = rwx for owner/group/others
- Ownership controls access in multi-user systems
- systemctl + journalctl are critical in production debugging
- Small daily practice builds real confidence
