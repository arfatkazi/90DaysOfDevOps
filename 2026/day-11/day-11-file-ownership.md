# Day 11 – File Ownership Challenge (chown & chgrp)

## Task 1: Understanding Ownership
**Owner vs Group**
- **Owner**: the user account that owns the file (primary control).
- **Group**: a group of users that can share access based on group permissions.

Screenshot: (attach `ls -l` from home directory)

## Files & Directories Created
- devops-file.txt
- team-notes.txt
- project-config.yaml
- app-logs/
- heist-project/vault/gold.txt
- heist-project/plans/strategy.conf
- bank-heist/access-codes.txt
- bank-heist/blueprints.pdf
- bank-heist/escape-plan.txt

## Ownership Changes (Before → After)

### devops-file.txt
- Before: `<paste ls -l devops-file.txt>`
- After chown tokyo: `<paste>`
- After chown berlin: `<paste>`

### team-notes.txt
- Before: `<paste ls -l team-notes.txt>`
- After chgrp heist-team: `<paste>`

### project-config.yaml
- After chown professor:heist-team: `<paste ls -l project-config.yaml>`

### app-logs/
- After chown berlin:heist-team: `<paste ls -ld app-logs>`

### heist-project/ (recursive)
- After chown -R professor:planners:
  - `<paste ls -lR heist-project output>`

### bank-heist/
- After setting different ownership:
  - `<paste ls -l bank-heist output>`

## Commands Used
```bash
# Task 2
touch devops-file.txt
sudo chown tokyo devops-file.txt
sudo chown berlin devops-file.txt

# Task 3
touch team-notes.txt
sudo groupadd heist-team
sudo chgrp heist-team team-notes.txt

# Task 4
touch project-config.yaml
mkdir -p app-logs
sudo chown professor:heist-team project-config.yaml
sudo chown berlin:heist-team app-logs

# Task 5
mkdir -p heist-project/vault heist-project/plans
touch heist-project/vault/gold.txt
touch heist-project/plans/strategy.conf
sudo groupadd planners
sudo chown -R professor:planners heist-project
ls -lR heist-project

# Task 6
mkdir -p bank-heist
touch bank-heist/access-codes.txt bank-heist/blueprints.pdf bank-heist/escape-plan.txt
sudo groupadd vault-team
sudo groupadd tech-team
sudo chown tokyo:vault-team bank-heist/access-codes.txt
sudo chown berlin:tech-team bank-heist/blueprints.pdf
sudo chown nairobi:vault-team bank-heist/escape-plan.txt
ls -l bank-heist
