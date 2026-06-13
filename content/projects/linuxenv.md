---
title: "Project 1: Building My Linux Lab & Navigating the WSL 'Docker Trap'"
date: 2026-06-13T10:00:00+01:00
draft: false
tags: ["Linux", "WSL", "Ubuntu", "Docker", "SysAdmin"]
categories: ["IT Fundamentals"]
showToc: true
---

For the first project of my Linux journey, the goal was to "Build a Personal Linux Lab." While the prompt suggested a traditional VM, I opted for **WSL (Windows Subsystem for Linux)**. However, I immediately ran into a fascinating environment quirk that taught me my first real lesson in Linux distributions.

---

## 🛠 The Setup: Encountering the "Docker Trap"

Initially, when I launched my terminal, I noticed something odd. My prompt was `BENNANDO:~#` (indicating I was logged in as root), and basic commands like `sudo` were missing. 

To investigate, I ran:
```bash
cat /etc/os-release
```

**The Output:**
`PRETTY_NAME="Docker Desktop"`

**The Lesson:** I wasn't in a full Ubuntu OS; I was inside Docker Desktop's internal utility backend! This is a common pitfall when Docker is installed on Windows. To fix this, I had to pivot to a dedicated instance.

### How I Resolved It:
1. Opened Windows PowerShell.
2. Ran `wsl -l -v` to list all installed distros.
3. Installed a dedicated Ubuntu instance: `wsl --install -d Ubuntu`.
4. Launched the correct environment: `wsl -d Ubuntu`.

---

## Task 1: Navigation & System Literacy

Once inside the correct Ubuntu environment, I practiced "Core System Literacy"—moving through the filesystem without a GUI.

```bash
# Verify current location
pwd

# Create a project workspace
mkdir -p ~/linux_lab/week1
cd ~/linux_lab/week1
```

---

## Task 2: File Operations & Text Editing

Linux revolves around the concept that "everything is a file." I practiced creating metadata and editing content via the CLI.

```bash
# Create a new file
touch first_entry.txt

# Open the file in Nano (Command Line Editor)
nano first_entry.txt
```

**Inside the editor:** I typed *"Project 1: Linux environment successfully configured on dedicated Ubuntu WSL."* and saved using `Ctrl+O` followed by `Ctrl+X`.

---

## Task 3: User Management & Security

Operating as the `root` user is dangerous. I practiced creating a restricted user and granting them `sudo` privileges for specific administrative tasks.

```bash
# Add a new user
sudo adduser labuser

# Grant sudo access to the new user
sudo usermod -aG sudo labuser
```

> **Security Tip:** Using `usermod -aG sudo` adds the user to the "SuperUser Do" group, allowing them to run admin commands only when explicitly requested.

---

## Task 4: SSH Configuration (Remote Access)

SSH (Secure Shell) is the industry standard for managing remote servers. I configured my lab to accept local SSH connections to simulate remote management.

```bash
# Install and start the SSH service
sudo apt update && sudo apt install openssh-server -y
sudo service ssh start

# Test the connection to the local machine
ssh labuser@localhost
```

**Result:** Successful login! This confirms the machine is ready to be managed "headless" (without a direct monitor/GUI).

---

## 📖 Key Commands Mastered This Week

| Command | Purpose |
| :--- | :--- |
| `cat /etc/os-release` | Identify the Linux distribution and version. |
| `wsl -l -v` | List all WSL distros installed on the Windows host. |
| `pwd` | Print Working Directory (The "You Are Here" marker). |
| `ls -la` | List all files, including hidden system files. |
| `sudo` | Execute a command with administrative privileges. |
| `ssh` | Securely access a remote terminal. |

---

### Final Thoughts
This week taught me that the "environment" matters just as much as the "commands." Distinguishing between a Docker backend and a full Linux OS was a vital first step in my journey toward system administration. 

**Next Week:** Permissions, Ownership, and the Linux Security Model.