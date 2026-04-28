# Experiment 2

## Experiment Title
Exploring Linux System Commands, Run Levels (Targets), and Help Utilities

## Aim
To study and execute basic Linux system commands, understand Linux run levels (systemd targets), and use Linux help utilities such as `man`, `--help`, and tab auto-completion.

---

## Objective
- To understand the Linux Command Line Interface (CLI)
- To execute basic Linux system commands
- To explore Linux system run levels / systemd targets
- To learn how to access command documentation using help utilities

---

## Theory

### Linux Command Line Interface (CLI)
The Linux CLI allows users to interact with the operating system using text commands. It provides better control and flexibility compared to graphical interfaces and is widely used in system administration and cybersecurity tasks.

### System Run Levels / Targets
Modern Linux systems use **systemd**, where traditional run levels are replaced by **targets**.

Common systemd targets include:

- `graphical.target` – Multi-user mode with graphical interface
- `multi-user.target` – Multi-user mode without GUI
- `rescue.target` – Single-user rescue mode
- `poweroff.target` – Shutdown system
- `reboot.target` – Restart system

### Linux Help Utilities
Linux provides built-in tools for understanding commands:

- `man` – Displays detailed manual pages
- `--help` – Shows command usage and options
- **Tab Auto-Completion** – Automatically completes commands and file names

---

## Procedure

### Step 1: Login
Log in to the Linux virtual machine and open the **Terminal**.

### Step 2: Execute Basic Commands
Run the following commands:
 pwd
 ls
 whoami
 date
 uptime

### Step 3: Directory Navigation
 cd /home
 cd ~

### Step 4: Using Manual Pages
 man ls
 man cd

Press **q** to exit the manual page.

### Step 5: Using Help Option

 ls --help
 systemctl --help

### Step 6: Check System Target / Run Level

 runlevel
 systemctl get-default 

### Step 7: Clear Terminal

  clear 


---

## Observations / Results

The commands were executed successfully in the Linux terminal. The system displayed directory information, user details, system time, uptime, and documentation using manual pages.


## Conclusion

Basic Linux system commands, system run levels (targets), and help utilities were successfully explored. The experiment improved understanding of Linux command-line interaction and system documentation tools.
  
