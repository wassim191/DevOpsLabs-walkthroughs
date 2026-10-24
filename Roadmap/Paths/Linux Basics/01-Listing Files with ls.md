# What is Linux?

**Room:** [Listing files with ls](https://devopslabs.dev/room/linux-01-listing-files)  
**Path:** Linux Basics  
**Difficulty:** Easy  
**Estimated time:** 30 min  
**Room:** 2 of 31  
**Points:** 110  
**Date completed:** 10/25/26(MM/DD/YY) 

---

## Room Overview

ls is usually the first command you type on any server, and the one you'll type most often after that. In this room you'll use it to explore the media store of a small video platform under /srv/media.

Press **Launch VM**. A terminal opens on the right, logged in as `root` on a fresh Ubuntu server.

---

## Task 1 — What ls can show you

On its own, ls prints the names in the current directory. Give it a path to look somewhere else, and options to change what you see:

```bash
ls /srv/media
ls -l /srv/media
```

The long format (-l) shows one entry per line: permissions, link count, owner, group, size in bytes, modification time and name. A leading d in the permissions means directory.

Options you'll use every day:

| Option       | effect                          |
|--------------------|-----------------------------------------------|
| -l     | long format  |
| -a  | include hidden entries (names starting with .), plus . and ..                       |
| -A             | hidden entries, without . and ..                       |
| -h       | sizes like 2.3M instead of bytes (use with -l)                                           |
| -t 	| sort by modification time, newest first |
| -S 	| sort by size, largest first |
| -r 	| reverse the sort order |
| -R 	| also list every subdirectory, recursively |

Options combine: ls -lhS is a long, human-readable listing sorted by size.

### Questions

1. Which option gives the long listing with permissions, owner, size and date?  
   **Answer:-l**  

2. Which option shows sizes as K, M and G in a long listing? 
   **Answer:-h**  

3. Which option sorts entries by modification time, newest first?  
   **Answer:-t**
   
4. Which option lists subdirectories recursively?
   **Answer:-r**
   
---


## Task 2 — Explore the media store

Use ls with the options from the last task to answer these questions about /srv/media. You only need ls (and wc -l to count lines, if you like).

### Questions

1. How many hidden entries are directly inside /srv/media? 
   **Answer:2**  
<img width="729" height="81" alt="image" src="https://github.com/user-attachments/assets/553f3a37-4731-4b72-a8f2-45bf6d23bed8" />

2. Which file in /srv/media/uploads/2026 is the largest?
   **Answer:launch-video.mp4**  
<img width="679" height="152" alt="image" src="https://github.com/user-attachments/assets/b8a99612-f12d-46ad-96aa-2637bae5efcb" />

3. Which file in /srv/media/uploads/2026 was modified most recently?
   **Answer:banner.png**  
<img width="677" height="152" alt="image" src="https://github.com/user-attachments/assets/e95a6cab-6e2d-4b16-84c6-058802523ec7" />

4. What size does ls -lh show for launch-video.mp4? 
   **Answer:2.3M**

5. How many files are in /srv/media/thumbs?
   **Answer:12**
<img width="568" height="44" alt="image" src="https://github.com/user-attachments/assets/5e23201a-60bc-463e-92f1-83f0495b5cb6" />


---


## Task 3 — Save a listing

Anything a command prints can be saved to a file with >:

```bash
ls -l /etc > /root/etc-listing.txt
```
Save a long listing of /srv/media/uploads/2026, sorted largest first, to /root/uploads.txt.

### Questions

1. Create /root/uploads.txt as described, then press Check.
   **Answer:** ```bash  ls -lS /srv/media/uploads/2026 > /root/uploads.txt```

<img width="1905" height="727" alt="image" src="https://github.com/user-attachments/assets/7191b775-da63-43a5-9329-d8bfe56af447" />



---



## References
- Room: https://devopslabs.dev/room/linux-01-listing-files
