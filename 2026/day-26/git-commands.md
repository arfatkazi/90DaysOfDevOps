# Git Commands Reference (Living Document)

## Setup & Config
- `git --version` — Check installed Git version  
  Example: `git --version`

- `git config --global user.name "Name"` — Set global username  
  Example: `git config --global user.name "Arfat Kazi"`

- `git config --global user.email "email"` — Set global email  
  Example: `git config --global user.email "arfatkazi901@gmail.com"`

- `git config --global --list` — View current global config  
  Example: `git config --global --list`

---

## Basic Workflow
- `git init` — Initialize a new repo  
  Example: `git init`

- `git status` — Show working tree status (modified/untracked/staged)  
  Example: `git status`

- `git add <file>` — Stage a file  
  Example: `git add git-commands.md`

- `git add .` — Stage all changes in the current folder  
  Example: `git add .`

- `git commit -m "message"` — Create a commit from staged changes  
  Example: `git commit -m "Add initial git commands"`

---

## Viewing Changes & History
- `git diff` — Show unstaged changes  
  Example: `git diff`

- `git diff --staged` — Show staged changes  
  Example: `git diff --staged`

- `git log` — View full commit history  
  Example: `git log`

- `git log --oneline` — Compact history view  
  Example: `git log --oneline`
