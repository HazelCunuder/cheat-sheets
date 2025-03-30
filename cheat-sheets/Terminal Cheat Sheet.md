# Terminal Cheat Sheet

The terminal, also known as the command line or shell, is a powerful tool that allows users to interact with the operating system through text-based commands. It provides direct access to system functions, file management, package installation, networking, and process control. Mastering the terminal can greatly enhance efficiency and automation.

## Table of Content

* [Basic Commands](#basic-commands)
* [File Permission](#file-permissions)
* [Proccess Management](#process-management)
* [Networking](#networking)
* [Package Management](#package-management)
* [System Management](#package-management)
* [Shortcuts](#shortcuts)

## Basic Commands

| Command | Description |
|---------|-------------|
| `pwd` | Print working directory |
| `ls` | List directory contents |
| `cd <dir>` | Change directory to `<dir>` |
| `mkdir <dir>` | Create a new directory `<dir>` |
| `rm <file>` | Remove a file |
| `rm -r <dir>` | Remove a directory and its contents |
| `cp <src> <dest>` | Copy file or directory |
| `mv <src> <dest>` | Move (rename) a file or directory |
| `touch <file>` | Create an empty file |
| `cat <file>` | Display file contents |
| `less <file>` | View file contents page by page |
| `head <file>` | Display the first 10 lines of a file |
| `tail <file>` | Display the last 10 lines of a file |
| `echo <text>` | Print text to the terminal |
| `clear` | Clear the terminal screen |

## File Permissions

| Command | Description |
|---------|-------------|
| `chmod 755 <file>` | Change file permissions |
| `chown user:group <file>` | Change file ownership |
| `ls -l` | List files with permissions |

## Process Management

| Command | Description |
|---------|-------------|
| `ps aux` | Show all running processes |
| `top` | Display real-time process info |
| `htop` | Interactive process viewer (install with `sudo apt install htop`) |
| `kill <PID>` | Terminate a process by ID |
| `kill -9 <PID>` | Force terminate a process |
| `pkill <name>` | Kill a process by name |
| `jobs` | List background jobs |
| `fg %<job>` | Bring a background job to foreground |

## Networking

| Command | Description |
|---------|-------------|
| `ping <host>` | Check connectivity to a host |
| `curl <URL>` | Fetch data from a URL |
| `wget <URL>` | Download files from a URL |
| `nmcli dev status` | Show network device status |
| `ip a` | Show IP addresses |
| `netstat -tulnp` | Show active network connections (install with `sudo apt install net-tools`) |

## Package Management

| Command | Description |
|---------|-------------|
| `sudo apt update` | Update package lists |
| `sudo apt upgrade` | Upgrade installed packages |
| `sudo apt install <package>` | Install a package |
| `sudo apt remove <package>` | Remove a package |
| `sudo apt autoremove` | Remove unnecessary dependencies |
| `sudo apt search <package>` | Search for a package |

## System Management

| Command | Description |
|---------|-------------|
| `df -h` | Show disk space usage |
| `du -sh <dir>` | Show size of a directory |
| `free -h` | Show memory usage |
| `uptime` | Show system uptime |
| `uname -a` | Show system information |
| `lsb_release -a` | Show  version |

## Shortcuts

| Shortcut | Description |
|----------|-------------|
| `Ctrl + C` | Kill the current process |
| `Ctrl + Z` | Suspend the current process |
| `Ctrl + D` | Logout or send EOF |
| `Ctrl + A` | Move cursor to the beginning of the line |
| `Ctrl + E` | Move cursor to the end of the line |
| `Ctrl + U` | Clear text before cursor |
| `Ctrl + K` | Clear text after cursor |
| `Ctrl + L` | Clear the terminal screen |
| `!!` | Repeat last command |
| `!<cmd>` | Run last command starting with `<cmd>` |
