# 📋 Command Cheatsheet

## Your Quick Reference Guide

Print this out or keep it handy! These are all the commands you learned.

---

## 🧭 Navigation (Getting Around)

| Command | What It Does | Example |
|---------|--------------|---------|
| `pwd` | "Where am I?" (Print Working Directory) | `pwd` → `/home/pedro` |
| `ls` | "What's here?" (List files) | `ls` |
| `ls -la` | "Show me EVERYTHING" (including hidden files) | `ls -la` |
| `cd folder` | "Go to this folder" | `cd /home` |
| `cd ..` | "Go back one level" | `cd ..` |
| `cd ~` | "Go to my home folder" | `cd ~` |

**Memory trick:** Think of `cd` as "Change Directory"

---

## 📖 Reading Files

| Command | What It Does | When to Use |
|---------|--------------|-------------|
| `cat file` | Show entire file | Small files |
| `less file` | Scroll through file (press `q` to quit) | Large files |
| `head file` | Show first 10 lines | Quick peek at beginning |
| `tail file` | Show last 10 lines | Log files |
| `grep "text" file` | Find specific text in file | Searching |

---

## 👤 User Management

| Task | Command |
|------|---------|
| Create user | `sudo useradd -m -c "Full Name" username` |
| Give admin access | `sudo usermod -aG wheel username` |
| Set password | `sudo passwd username` |
| Check user info | `id username` |
| Lock account | `sudo usermod -L username` |
| Unlock account | `sudo usermod -U username` |
| Delete user (keep files) | `sudo userdel username` |
| Delete user + files | `sudo userdel -r username` |

**Quick reference:**
- `-m` = make home folder
- `-c` = comment (full name)
- `-aG` = add to Group
- `-L` = Lock
- `-r` = remove (delete files too)

---

## ⚙️ Service Management

| Task | Command |
|------|---------|
| Check status | `sudo systemctl status httpd` |
| Start service | `sudo systemctl start httpd` |
| Stop service | `sudo systemctl stop httpd` |
| Restart service | `sudo systemctl restart httpd` |
| Enable auto-start | `sudo systemctl enable httpd` |
| Disable auto-start | `sudo systemctl disable httpd` |

**Status meanings:**
| Status | Meaning |
|--------|---------|
| `active (running)` | ✅ Working |
| `inactive (dead)` | ⏹️ Stopped |
| `failed` | ❌ Crashed |
| `not found` | ❓ Not installed |

---

## 📦 Package Management

| Task | Command |
|------|---------|
| Install package | `sudo dnf install httpd -y` |
| Remove package | `sudo dnf remove httpd` |
| Update all packages | `sudo dnf update` |
| Search for package | `dnf search keyword` |

---

## 🤖 Ansible Commands

| Task | Command |
|------|---------|
| Check version | `ansible --version` |
| Test connection | `ansible all -i inventory.ini -m ping` |
| Run playbook | `ansible-playbook -i inventory.ini playbook.yml` |
| Run playbook with sudo password | `ansible-playbook -i inventory.ini playbook.yml --ask-become-pass` |
| Run command on all servers | `ansible all -i inventory.ini -m command -a "your command"` |

---

## 📦 Container Commands (Podman)

| Task | Command |
|------|---------|
| Run container | `podman run -d --name NAME -p PORT:PORT IMAGE` |
| List running containers | `podman ps` |
| List ALL containers | `podman ps -a` |
| Stop container | `podman stop NAME` |
| Start container | `podman start NAME` |
| Remove container | `podman rm NAME` |
| View logs | `podman logs NAME` |
| List images | `podman images` |

**Example:**
```bash
podman run -d --name myweb -p 8080:80 docker.io/library/httpd
```

---

## 🌐 Network Commands

| Task | Command |
|------|---------|
| Show IP addresses | `ip addr show` |
| Test connectivity | `ping -c 3 192.168.56.10` |
| Check open ports | `ss -tlnp` |
| Set static IP | `sudo nmcli con mod "Wired connection 2" ipv4.addresses 192.168.56.10/24` |

---

## 🔐 SSH Commands

| Task | Command |
|------|---------|
| Connect to server | `ssh user@192.168.56.10` |
| Generate SSH key | `ssh-keygen -t rsa -b 4096` |
| Copy key to server | `ssh-copy-id user@192.168.56.10` |
| Run command remotely | `ssh user@192.168.56.10 "hostname"` |

---

## 📁 File Operations

| Task | Command |
|------|---------|
| Create folder | `mkdir foldername` |
| Create file | `touch filename` |
| Copy file | `cp file1 file2` |
| Move/rename | `mv oldname newname` |
| Delete file | `rm filename` |
| Delete folder | `rm -r foldername` |
| Create backup | `tar -czvf backup.tar.gz /folder` |

---

## 🆘 Getting Help

| Command | What It Does |
|---------|--------------|
| `man command` | Full manual (press `q` to quit) |
| `command --help` | Quick help |
| `which command` | Where is this program? |

---

## 💡 Pro Tips

### 1. Tab Completion
Press `Tab` to auto-complete commands and filenames!
```bash
sys[TAB] → systemctl
```

### 2. Command History
Press `↑` arrow to see previous commands.

### 3. Cancel Command
Press `Ctrl + C` to stop a running command.

### 4. Clear Screen
Press `Ctrl + L` or type `clear`.

### 5. Exit
Type `exit` or press `Ctrl + D`.

---

## 🔧 Common Fixes

### "Permission denied"
Add `sudo` in front of the command.

### "Command not found"
The program isn't installed. Try:
```bash
sudo dnf install program-name
```

### "No such file or directory"
Check your spelling and path. Use `ls` to see what's available.

### Nothing happens after command
That usually means success! Linux is quiet when things work.

---

## 📊 Quick Reference: Our Lab IPs

| Machine | IP Address | Username |
|---------|------------|----------|
| Controller | 192.168.56.30 | controller |
| Server | 192.168.56.10 | pedro |
| Client | 192.168.56.20 | client |

---

*Keep this cheatsheet handy as you practice! 📋*
