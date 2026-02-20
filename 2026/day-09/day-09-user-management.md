# Day 09 Challenge – Linux User & Group Management

## Users & Groups Created
- Users: tokyo, berlin, professor, nairobi
- Groups: developers, admins, project-team

## Group Assignments
- tokyo → developers, project-team
- berlin → developers, admins
- professor → admins
- nairobi → project-team

## Directories Created
- /opt/dev-project → group: developers, perms: 2775 (drwxrwsr-x)
- /opt/team-workspace → group: project-team, perms: 2775 (drwxrwsr-x)

## Commands Used
```bash
# Users
sudo useradd -m -s /bin/bash tokyo
sudo useradd -m -s /bin/bash berlin
sudo useradd -m -s /bin/bash professor
sudo passwd tokyo
sudo passwd berlin
sudo passwd professor



# Groups
sudo groupadd developers
sudo groupadd admins
getent group developers admins

# Assign groups
sudo usermod -aG developers tokyo
sudo usermod -aG developers,admins berlin
sudo usermod -aG admins professor

# Verify group membership
id tokyo
id berlin
id professor

# Shared directory
sudo mkdir -p /opt/dev-project
sudo chgrp developers /opt/dev-project
sudo chmod 2775 /opt/dev-project
ls -ld /opt/dev-project

# Test file creation
sudo -u tokyo touch /opt/dev-project/tokyo-file.txt
sudo -u berlin touch /opt/dev-project/berlin-file.txt
ls -l /opt/dev-project

# Task 5
sudo useradd -m -s /bin/bash nairobi
sudo passwd nairobi
sudo groupadd project-team
sudo usermod -aG project-team nairobi
sudo usermod -aG project-team tokyo

sudo mkdir -p /opt/team-workspace
sudo chgrp project-team /opt/team-workspace
sudo chmod 2775 /opt/team-workspace
ls -ld /opt/team-workspace

sudo -u nairobi touch /opt/team-workspace/nairobi-note.txt
ls -l /opt/team-workspace

