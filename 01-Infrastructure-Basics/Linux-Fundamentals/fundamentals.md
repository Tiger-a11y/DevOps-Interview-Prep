# Linux Fundamentals

## Table of Contents

1. [Introduction to Linux](#introduction-to-linux)
2. [Linux Architecture](#linux-architecture)
3. [Distributions and Package Management](#distributions-and-package-management)
4. [Linux File System](#linux-file-system)
5. [User and Group Management](#user-and-group-management)
6. [File Permissions and Security](#file-permissions-and-security)
7. [Process Management](#process-management)
8. [Networking in Linux](#networking-in-linux)
9. [System Monitoring and Performance Tuning](#system-monitoring-and-performance-tuning)
10. [Essential Linux Commands](#essential-linux-commands)
11. [Shell Scripting Basics](#shell-scripting-basics)

---

## Introduction to Linux

Linux is an open-source operating system based on the UNIX architecture. It powers servers, cloud environments, embedded systems, and even personal computers. Understanding Linux fundamentals is crucial for DevOps engineers, system administrators, and developers.

### Why Learn Linux?
- **Widely Used**: Essential for managing cloud platforms and on-prem infrastructure.
- **High Performance**: Lightweight and optimized for scalability.
- **Security**: Built-in permissions and access control.
- **Customization**: Can be tailored for various use cases.

---

## Linux Architecture

Linux follows a layered architecture:
- **Kernel**: The core that interacts with hardware.
- **Shell**: Interface for users to interact with the system.
- **System Libraries**: Provide necessary functions to applications.
- **System Utilities**: Basic commands and utilities.

---

## Distributions and Package Management

Popular distributions:
- **Debian-based** (Ubuntu, Kali, Mint) - Uses `apt` package manager.
- **Red Hat-based** (RHEL, CentOS, Fedora) - Uses `yum` or `dnf`.
- **Arch-based** (Manjaro, EndeavourOS) - Uses `pacman`.

### Package Management Commands
#### Debian-based (Ubuntu):
```bash
sudo apt update
sudo apt install <package>
sudo apt remove <package>
```

#### Red Hat-based:
```bash
sudo yum update
sudo yum install <package>
sudo yum remove <package>
```

---

## Linux File System

### Important Directories:
- `/bin` – Essential binaries.
- `/etc` – System configuration files.
- `/home` – User home directories.
- `/var` – Logs and variable files.
- `/tmp` – Temporary files.

### File System Navigation:
```bash
ls -l   # List files with details
cd /etc # Change directory
pwd     # Print working directory
```

---

## User and Group Management

### User Commands:
```bash
sudo useradd <username>
sudo passwd <username>
sudo userdel <username>
```

### Group Commands:
```bash
groupadd <groupname>
groupdel <groupname>
usermod -aG <groupname> <username>
```

---

## File Permissions and Security

### Permission Types:
- Read (r) - `4`
- Write (w) - `2`
- Execute (x) - `1`

### Changing Permissions:
```bash
chmod 755 file.sh
chown user:group file.sh
```

---

## Process Management

### Process Monitoring:
```bash
top  # Live process monitoring
ps aux | grep <process>
pkill <process>
```

### Background and Foreground:
```bash
<command> &  # Run in background
fg <jobID>   # Bring to foreground
```

---

## Networking in Linux

### Check Network Interface:
```bash
ip a
```

### Ping a Host:
```bash
ping google.com
```

### Check Open Ports:
```bash
netstat -tulnp
```

---

## System Monitoring and Performance Tuning

### CPU and Memory Usage:
```bash
htop
free -m
```

### Disk Usage:
```bash
df -h
du -sh *
```

---

## Essential Linux Commands

### File Operations:
```bash
touch file.txt
rm file.txt
cp file1.txt file2.txt
```

### Searching Files:
```bash
find / -name file.txt
grep 'pattern' file.txt
```

### Archiving and Compression:
```bash
tar -cvf archive.tar file.txt
gzip file.txt
```

---

## Shell Scripting Basics

### Writing a Simple Script:
```bash
#!/bin/bash
echo "Hello, Linux!"
```

### Making It Executable:
```bash
chmod +x script.sh
./script.sh
```
