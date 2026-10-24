# What is Linux?

**Room:** [What is Linux?](https://devopslabs.dev/room/linux-00-what-is-linux)  
**Path:** Linux Basics  
**Difficulty:** Easy  
**Estimated time:** 20 min  
**Room:** 1 of 31  
**Points:** 0 / 80  
**Date completed:**  

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

- `/etc/os-release` describes the distribution.
- `uname -a` prints details about the running kernel: its version, the machine's hostname and the CPU architecture.

### Questions

1. What is the core part of the operating system that manages the hardware called?  
   **Answer:**  

2. Which distribution is this machine running? (name only, as in `/etc/os-release`)  
   **Answer:**  

3. Which command prints information about the running kernel?  
   **Answer:**  

---

## Task 2

*(Complete Task 1 first – content / questions will appear after launching the VM and answering Task 1)*

### Questions
1.  
   **Answer:**  

2.  
   **Answer:**  

---

## Notes / Screenshots

*(Add your notes and screenshots here)*

---

## References
- Room: https://devopslabs.dev/room/linux-00-what-is-linux
