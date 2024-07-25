# Linux-Basics

# Linux Administration Guide

## Table of Contents

1. [Introduction to Linux Administration](#introduction-to-linux-administration)
2. [System Administration Basics](#system-administration-basics)
3. [Networking Essentials](#networking-essentials)
4. [File Systems and Storage](#file-systems-and-storage)
5. [User and Group Management](#user-and-group-management)
6. [Process Management](#process-management)
7. [Backup and Recovery](#backup-and-recovery)
8. [Security and Compliance](#security-and-compliance)
9. [Advanced Topics](#advanced-topics)

---

## Introduction to Linux Administration

Linux administration involves managing and maintaining Linux-based systems to ensure their smooth and efficient operation. This guide covers various aspects of Linux administration, including basic commands, networking, file systems, user management, process management, backup and recovery, and security.

## System Administration Basics

### Basic Commands
- **Navigating the File System**:
  - `cd [directory]`: Change directory
  - `ls [options] [directory]`: List directory contents
  - `pwd`: Print working directory
- **File Operations**:
  - `cp [source] [destination]`: Copy files or directories
  - `mv [source] [destination]`: Move or rename files or directories
  - `rm [file]`: Remove files
  - `mkdir [directory]`: Create a new directory

### Managing Packages
- **RPM (Red Hat Package Manager)**:
  - `rpm -i [package.rpm]`: Install a package
  - `rpm -e [package]`: Remove a package
  - `rpm -qa`: List all installed packages
- **APT (Advanced Package Tool)** (Debian/Ubuntu):
  - `apt-get update`: Update package index
  - `apt-get install [package]`: Install a package
  - `apt-get remove [package]`: Remove a package

## Networking Essentials

### Basic Networking Commands
- **`ifconfig`**: Display or configure network interface parameters
- **`ping [host]`**: Send ICMP ECHO_REQUEST to network hosts
- **`netstat -r`**: Display the kernel routing tables
- **`traceroute [host]`**: Print the route packets take to the network host

### Configuring Network Interfaces
- **Static IP Configuration**:
  - Edit `/etc/network/interfaces` (Debian/Ubuntu) or `/etc/sysconfig/network-scripts/ifcfg-[interface]` (Red Hat/CentOS)
- **Dynamic IP Configuration (DHCP)**:
  - Use `dhclient [interface]` to obtain an IP address from a DHCP server

## File Systems and Storage

### File System Management
- **Creating and Managing Partitions**:
  - `fdisk [device]`: Partition a hard drive
  - `mkfs -t [filesystem] [device]`: Create a file system on a partition
- **Mounting and Unmounting File Systems**:
  - `mount [device] [mount_point]`: Mount a file system
  - `umount [device]`: Unmount a file system

### Disk Usage
- **Checking Disk Usage**:
  - `df -h`: Display disk space usage in human-readable format
  - `du -sh [directory]`: Display the total disk usage of a directory

## User and Group Management

### Managing Users
- **Add a new user**:
  - `useradd [username]`
  - `passwd [username]`: Set user password
- **Delete a user**:
  - `userdel [username]`

### Managing Groups
- **Add a new group**:
  - `groupadd [groupname]`
- **Add a user to a group**:
  - `usermod -aG [groupname] [username]`

## Process Management

### Basic Process Commands
- **View running processes**:
  - `ps aux`: Display all running processes
  - `top`: Display real-time process information
- **Manage processes**:
  - `kill [PID]`: Terminate a process by PID
  - `killall [process_name]`: Terminate all processes with a specific name

### Scheduling Tasks
- **Using `cron`**:
  - Edit crontab file with `crontab -e`
  - Schedule tasks using the format: `* * * * * command`
  - `crontab -l`: List cron jobs

## Backup and Recovery

### Backup Tools
- **`tar`**: Archive files
  - `tar -cvf [archive.tar] [directory]`: Create an archive
  - `tar -xvf [archive.tar]`: Extract an archive
- **`rsync`**: Sync files and directories
  - `rsync -avz [source] [destination]`

### Restore Files
- **Using `tar`**:
  - `tar -xvf [archive.tar] -C [destination]`: Extract an archive to a destination
- **Using `rsync`**:
  - `rsync -avz [source] [destination]`: Restore files from a backup

## Security and Compliance

### Basic Security Measures
- **File Permissions**:
  - `chmod [permissions] [file]`: Change file permissions
  - `chown [owner]:[group] [file]`: Change file owner and group
- **Firewall Configuration**:
  - **`iptables`**: Manage firewall rules
    - `iptables -L`: List current rules
    - `iptables -A INPUT -p tcp --dport 22 -j ACCEPT`: Allow SSH connections
  - **`ufw`** (Ubuntu):
    - `ufw enable`: Enable the firewall
    - `ufw allow [port]`: Allow a specific port

### Advanced Security Tools
- **SELinux**:
  - `sestatus`: Check the status of SELinux
  - `setenforce [Enforcing|Permissive]`: Change SELinux mode
- **AppArmor**:
  - `aa-status`: Check the status of AppArmor
  - `aa-enforce [profile]`: Enforce a specific AppArmor profile

## Advanced Topics

### Virtualization
- **KVM**:
  - `virsh list --all`: List all virtual machines
  - `virsh start [vm_name]`: Start a virtual machine
- **Docker**:
  - `docker ps`: List running containers
  - `docker run -d [image]`: Run a container in detached mode

### Scripting and Automation
- **Bash Scripting**:
  - **Variables**:
    ```bash
    #!/bin/bash
    name="John"
    echo "Hello, $name"
    ```
  - **Loops**:
    ```bash
    for i in {1..5}
    do
      echo "Welcome $i times"
    done
    ```
  - **Conditional Statements**:
    ```bash
    if [ "$name" == "John" ]; then
      echo "Your name is John"
    else
      echo "Your name is not John"
    fi
    ```

## References
- "Command Line Kung Fu: Bash Scripting Tricks, Linux Shell Programming Tips, and Bash One-liners"
- "Linux Administration: A Beginner’s Guide"
- "Modern Linux Administration: How to Become a Cutting-Edge Linux Administrator"
- "Linux Command Line and Shell Scripting Bible"
- "Bash Cookbook: Solutions and Examples for Bash Users"
- "Linux Basics for Hackers: Getting Started with Networking, Scripting, and Security in Kali"
- "Mastering Bash: Automate Daily Tasks with Bash"
