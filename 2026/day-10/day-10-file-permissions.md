# Day 10 – File Permissions & File Operations Challenge

## Files Created
- devops.txt (empty file)
- notes.txt (with content)
- script.sh (bash script)
- project/ (directory)

## Commands Used
```bash
# Task 1
touch devops.txt
echo "My devops imp  notes " > notes.txt
echo "Learning chmod, rwx, and basic file ops" >> notes.txt

cat > script.sh <<'EOF'
#!/bin/bash
echo "hello Devops"
EOF

ls -l devops.txt notes.txt script.sh

# Task 2
cat notes.txt
vim -R script.sh
head -n 5 /etc/passwd
cat /etc/passwd | head -n 5
tail -n 5 /etc/passwd
cat /etc/passwd | tail -n 5

# Task 4
chmod +x script.sh
./script.sh

chmod a-w devops.txt
chmod 640 notes.txt

mkdir -p project
chmod 755 project
ls -ld project

# Task 5
echo "try write" >> devops.txt
chmod -x script.sh
./script.sh
chmod +x script.sh
