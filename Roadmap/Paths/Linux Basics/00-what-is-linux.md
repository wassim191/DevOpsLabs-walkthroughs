# What is Linux?

**Room:** [What is Linux?](https://devopslabs.dev/room/linux-00-what-is-linux)  
**Path:** Linux Basics  
**Difficulty:** Easy  
**Estimated time:** 20 min  
**Room:** 1 of 31  
**Points:** 80  
**Date completed:** 10/25/26(MM/DD/YY) 

---

## Room Overview

Every lab on DevOpsLabs runs on a real Linux server. Before you start typing commands, it helps to know what you're talking to: what "Linux" actually means, why DevOps work happens on it, and where things live on a server.

Press **Launch VM**. A terminal opens on the right, logged in as `root` on a fresh Ubuntu server.

---

## Task 1 — Kernel, distributions and you

Strictly speaking, **Linux is a kernel**: the core program that manages the CPU, memory, disks and network, and lets every other program use them safely. What people call "Linux" day to day is that kernel plus tools and libraries, packaged together as a **distribution**.

| Distribution       | Where you'll meet it                          |
|--------------------|-----------------------------------------------|
| Ubuntu, Debian     | cloud servers, CI runners, developer laptops  |
| RHEL, Rocky, Alma  | enterprise data centres                       |
| Alpine             | small container images                        |
| Amazon Linux       | AWS                                           |

Distributions differ mostly in their package manager (`apt`, `dnf`, `apk`) and how often they release. The kernel, the shell and the everyday commands are the same everywhere, so what you learn here works on all of them.

### Why DevOps happens on Linux
- Production servers almost always run Linux, usually with no desktop at all. You manage them over SSH, in a terminal.
- Containers are Linux processes with some walls around them, and every Kubernetes node is a Linux machine.
- Scripts, CI pipelines and configuration tools are all built on the commands you'll learn in this path.

### Ask the server what it is

```bash
cat /etc/os-release
uname -a
```
<img width="1908" height="855" alt="image" src="https://github.com/user-attachments/assets/879bb1e8-a5e1-45fd-8ba0-250cc63ca843" />

- `/etc/os-release` describes the distribution.
- `uname -a` prints details about the running kernel: its version, the machine's hostname and the CPU architecture.

### Questions

1. What is the core part of the operating system that manages the hardware called?  
   **Answer:Kernal**  

2. Which distribution is this machine running? (name only, as in `/etc/os-release`)  
   **Answer:Ubuntu**  

3. Which command prints information about the running kernel?  
   **Answer:uname**  

---


## Task 2 — One tree, starting at /

Linux has **one** directory tree, and it starts at /, called root. There are no drive letters: extra disks, USB sticks and network shares are mounted somewhere inside the same tree.

Every distribution lays the tree out the same way, so once you know where things go, you can find your way around any server:

| Directory       | What lives there                        |
|--------------------|-----------------------------------------------|
| /etc     | configuration files  |
| /var  | data that changes: logs in /var/log, caches, queues                       |
| /home/<user>, /root             | users' home directories (/root is root's)                        |
| /usr/bin     | programs, including the commands you type  |
| /tmp  | temporary files, cleared on reboot                       |
| /opt, /svr             | add-on software, and data that services serve                        |
| /proc, /sys             | not real files: a live view into the kernel                        |


This server runs a small service called orbit. Like most services, it spreads its files across the tree by type: settings in /etc, logs in /var/log, and the program itself in /opt.

```bash
ls /
ls /etc/orbit /var/log/orbit /opt/orbitcat /etc/os-release
uname -a
```
<img width="1908" height="843" alt="image" src="https://github.com/user-attachments/assets/eb99ca7f-a084-4819-8186-a91e91809589" />


When something breaks on a server, this map tells you where to look first: the config in /etc, then the logs in /var/log.

### Questions

1. Which top-level directory holds system-wide configuration?  
   **Answer:/etc**  

2. The orbit service keeps its configuration under /etc/orbit. Which port does orbit.conf set? Use cat to print the file. 
   **Answer:8443**  
<img width="1908" height="847" alt="image" src="https://github.com/user-attachments/assets/41b37f91-56d9-44e2-9df2-f4f1a664140c" />

3. Where do services write their logs? (the directory under /var) 
   **Answer:/var/log**  

4. How many log files has orbit written in its log directory? 
   **Answer:/usr/bin**  


---

## References
- Room: https://devopslabs.dev/room/linux-00-what-is-linux
