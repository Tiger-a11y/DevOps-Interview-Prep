### **System Information**
- **`uname`**: Print system information.
  - `uname -r`: Kernel version.
  - `uname -a`: All system information.
- **`hostname`**: Show or set the system's hostname.
- **`uptime`**: How long the system has been running.
- **`arch`**: Display machine architecture.
- **`lsb_release -a`**: Distribution-specific information.
- **`cat /etc/os-release`**: OS version information.
- **`top`**: Display running processes.
- **`htop`**: Interactive process viewer (requires installation).
- **`free`**: Display memory usage.
- **`df`**: Show disk space usage.
  - `df -h`: Human-readable format.
- **`du`**: Estimate file space usage.
  - `du -sh <dir>`: Total size of directory.
- **`dmesg`**: Kernel ring buffer messages.
- **`vmstat`**: System performance (CPU, memory, etc.).

---

### **User and Group Management**
- **`whoami`**: Display the current user.
- **`who`**: List who is logged in.
- **`id`**: Display user ID (UID) and group ID (GID).
- **`useradd <user>`**: Add a new user.
- **`usermod <user>`**: Modify user account.
- **`passwd <user>`**: Change user password.
- **`groupadd <group>`**: Add a new group.
- **`groups <user>`**: Show groups the user belongs to.
- **`chown <user>:<group> <file>`**: Change file owner and group.
- **`chmod`**: Change file permissions.
  - `chmod 755 <file>`: Owner can read/write/execute, others can read/execute.
- **`chgrp <group> <file>`**: Change group ownership of a file.

---

### **File and Directory Management**
- **`ls`**: List files and directories.
  - `ls -l`: Detailed listing.
  - `ls -a`: Include hidden files.
- **`cd`**: Change directory.
- **`pwd`**: Print working directory.
- **`cp <source> <destination>`**: Copy files/directories.
- **`mv <source> <destination>`**: Move/rename files/directories.
- **`rm <file>`**: Remove files.
  - `rm -r <dir>`: Remove directories recursively.
- **`mkdir <dir>`**: Create a new directory.
- **`rmdir <dir>`**: Remove an empty directory.
- **`touch <file>`**: Create an empty file.
- **`ln <target> <link>`**: Create a hard link.
  - `ln -s <target> <symlink>`: Create a symbolic link.
- **`find <dir> -name <filename>`**: Find files by name.
- **`locate <file>`**: Find files by name (using a pre-built database).
- **`updatedb`**: Update the database used by `locate`.
- **`stat <file>`**: Display file or file system status.
- **`file <file>`**: Determine file type.

---

### **File Compression/Archiving**
- **`tar -czvf <archive.tar.gz> <file>`**: Create a compressed archive.
- **`tar -xzvf <archive.tar.gz>`**: Extract a tar.gz archive.
- **`zip <archive.zip> <file>`**: Compress files into a zip archive.
- **`unzip <archive.zip>`**: Extract a zip archive.
- **`gzip <file>`**: Compress a file with gzip.
- **`gunzip <file.gz>`**: Decompress a gzipped file.
- **`bzip2 <file>`**: Compress a file with bzip2.
- **`bunzip2 <file.bz2>`**: Decompress a bzipped file.

---

### **Process Management**
- **`ps`**: View running processes.
  - `ps aux`: View all processes.
- **`top`**: Display and manage running processes.
- **`htop`**: Interactive process viewer (requires installation).
- **`kill <pid>`**: Kill a process by its PID.
- **`killall <process>`**: Kill processes by name.
- **`pkill <process>`**: Kill processes by name (more advanced).
- **`nice <command>`**: Run a command with a modified priority.
- **`renice <pid> <priority>`**: Change the priority of a running process.

---

### **Networking Commands**
- **`ping <host>`**: Test network connectivity to a remote host.
- **`ifconfig`**: View and configure network interfaces (deprecated in favor of `ip`).
- **`ip addr show`**: Show IP addresses assigned to interfaces.
- **`ip link show`**: List network interfaces and their statuses.
- **`ip route show`**: Show the routing table.
- **`traceroute <host>`**: Trace the route packets take to a remote host.
- **`netstat -tulnp`**: View active ports and their processes.
- **`ss -tulnp`**: More advanced alternative to `netstat`.
- **`nslookup <domain>`**: Query DNS for a domain's IP address.
- **`dig <domain>`**: Advanced DNS lookup.
- **`ifup <interface>`**: Bring up a network interface.
- **`ifdown <interface>`**: Bring down a network interface.
- **`ip addr add <ip>/24 dev <interface>`**: Assign an IP address to an interface.
- **`route`**: Show or manipulate the system's routing table (deprecated).
- **`nmap <host>`**: Scan for open ports on a host.
- **`tcpdump`**: Capture network packets.
- **`wget <url>`**: Download files from the web.
- **`curl <url>`**: Transfer data from or to a server.

---

### **Disk Management**
- **`df`**: Show disk space usage.
- **`du`**: Show file and directory space usage.
- **`lsblk`**: List block devices (disks and partitions).
- **`fdisk -l`**: List all disk partitions.
- **`mount`**: Mount a file system.
- **`umount`**: Unmount a file system.
- **`mkfs.ext4 <device>`**: Format a partition with ext4 file system.
- **`fsck <device>`**: Check and repair a file system.

---

### **Package Management (Debian/Ubuntu-based)**
- **`apt update`**: Update package list.
- **`apt upgrade`**: Upgrade installed packages.
- **`apt install <package>`**: Install a package.
- **`apt remove <package>`**: Remove a package.
- **`apt search <package>`**: Search for a package.
- **`apt show <package>`**: Show information about a package.

### **Package Management (RedHat/CentOS-based)**
- **`yum update`**: Update package list and install upgrades.
- **`yum install <package>`**: Install a package.
- **`yum remove <package>`**: Remove a package.
- **`yum search <package>`**: Search for a package.
- **`dnf update`**: Update packages (for newer RedHat/CentOS systems).
- **`dnf install <package>`**: Install a package.

---

### **File Permissions and Ownership**
- **`chmod <permissions> <file>`**: Change file permissions.
  - `chmod 755 <file>`: Full permissions for owner, read and execute for others.
  - `chmod +x <file>`: Make a file executable.
- **`chown <user>:<group> <file>`**: Change file owner and group.
- **`chgrp <group> <file>`**: Change group ownership of a file.

---

### **Text Processing and Manipulation**
- **`cat <file>`**: Display file contents.
- **`more <file>`**: View file contents one page at a time.
- **`less <file>`**: View file contents with navigation (better than `more`).
- **`head <file>`**: Show the first 10 lines of a file.
- **`tail <file>`**: Show the last 10 lines of a file.
  - `tail -f <file>`: Continuously watch a file for changes.
- **`grep <pattern> <file>`**: Search for a pattern in a file.
- **`sed 's/old/new/g' <file>`**: Stream editor to replace text.
- **`awk`**: Text processing tool for pattern scanning and processing.
- **`cut -d <delimiter> -f <fields>`**: Cut specific fields from a file.
- **`sort <file>`**: Sort lines in a file.
- **`uniq <file>`**: Remove duplicate lines from a file.
- **`wc <file>`**: Count lines, words, and characters in a file.

---

### **Log Management**
- **`journalctl`**: View system logs.
- **`tail -f /var/log/syslog`**: Continuously monitor system logs.
- **`dmesg`**: Display kernel messages.

---

### **System Shutdown and Reboot**
- **`shutdown`**: Shut down the system.
  - `shutdown now`: Shut down immediately.
  - `shutdown -h +5`: Shut down after 5 minutes.
- **`reboot`**: Reboot the system.
- **`halt`**: Stop all processes and halt the system.

---

### **Archiving/Backup**
- **`rsync -av <source> <destination>`**: Sync files and directories.
- **`tar -czvf <archive.tar.gz> <directory>`**: Create a compressed archive.
- **`tar -xzvf <archive.tar.gz>`**: Extract a compressed archive.

---

### **Cron Jobs and Scheduling**
- **`crontab -e`**: Edit the cron jobs for the current user.
- **`crontab -l`**: List cron jobs for the current user.
- **`at`**: Schedule one-time tasks (e.g., `at 12:00`).
- **`atq`**: View scheduled `at` jobs.
- **`batch`**: Schedule jobs for execution when the system is idle.