# Day 02 — Linux Architecture, Processes, and systemd (My Notes)

## 1) Core parts of Linux (simple)

- **Kernel** (the brain)

  - Talks to hardware (CPU, RAM, disk, network)
  - Controls memory, processes, files, networking
  - When we run commands, the kernel actually does the real work behind the scenes


- **User Space** (where we work)

  - Shell (bash), commands (ls, ps, top), programs (nginx, docker)
  - User space cannot directly control hardware, so it requests the kernel using system calls

- **Init / systemd** (the manager)

  - After boot, Linux starts a main process called **PID 1** (mostly `systemd`)
  - systemd starts services, keeps them running, restarts them if needed, and manages logs

## 2) How processes are created and managed

- A **process** = a running program
- Every process has:
  - **PID** (process ID)
  - **PPID** (parent process ID)
  - CPU and memory usage

- When I run a command in terminal:
  - the shell creates a new process (child)
  - the child runs the command
  - when it finishes, it exits and returns an exit code

## 3) Process states (meaning in real life)

- **Running (R)**: currently using CPU
- **Sleeping (S)**: waiting (very common) – like waiting for input, network, timer
- **Disk sleep / Uninterruptible (D)**: waiting for disk I/O (can look “stuck”)
- **Stopped (T)**: paused/stopped by a signal (like Ctrl+Z)
- **Zombie (Z)**: process finished but parent didn’t clean it properly
  - zombies don’t use much CPU, but many zombies means a problem in the parent process

## 4) What systemd does and why it matters (DevOps use)

- Starts services during boot (ssh, nginx, docker, etc.)
- Checks service status (running / failed)
- Restarts crashed services (if configured)
- Manages logs using `journalctl`
- Helps in troubleshooting because everything is controlled in one place

## 5) 5 commands I will use daily

- `ps aux` → see all running processes
- `top` (or `htop`) → live CPU/memory usage, find heavy process
- `systemctl status <service>` → check if service is running or failed
- `journalctl -u <service> -e` → see latest logs for a service
- `kill <PID>` → stop a bad process (use `kill -9 <PID>` only if normal kill doesn’t work)

