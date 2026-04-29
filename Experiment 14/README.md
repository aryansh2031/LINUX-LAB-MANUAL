# Experiment: User Login Monitoring, File Listing & Job Control in Linux

---

## 📌 Aim

To write and execute a Bash shell script that monitors logged-in users, lists files in column format, and manages job execution using priority control and background processing.

---

## 🎯 Objective

- Monitor the number of users currently logged into the Linux system.
- List files in the home directory using a column display format.
- Run processes in the background with adjusted priority using `nice`.
- Keep background jobs alive after logout using `nohup`.
- Understand foreground/background job control with `jobs`, `fg`, and `bg`.

---

## 📚 Theory

Linux is a multi-user operating system that allows several users to be logged in simultaneously. Administrators use commands like `who` and `users` to monitor active sessions.

The `ls` command supports multiple display formats. The `-C` flag organizes files into neat columns, making output easier to read.

**Job Control** in Linux allows processes to run either in the foreground (interactively) or in the background (independently). Key tools include:

- **`nice`** – Adjusts the CPU scheduling priority of a process (values range from -20 to 19; higher value = lower priority).
- **`nohup`** – Prevents a process from being terminated when the user logs out by ignoring the hangup signal.
- **`jobs`** – Lists all active background jobs in the current shell session.
- **`fg` / `bg`** – Brings a background job to the foreground or resumes a stopped job in the background.

---

## 🛠️ Step-by-Step Procedure

1. Open the terminal.

2. Create a new shell script file:
   ```bash
   nano system_info.sh
   ```

3. Type the script content (see Configuration Commands below).

4. Save and exit:
   - Press `Ctrl + O` to save.
   - Press `Ctrl + X` to exit nano.

5. Make the script executable:
   ```bash
   chmod +x system_info.sh
   ```

6. Run the script:
   ```bash
   ./system_info.sh
   ```

7. Verify background jobs are running:
   ```bash
   jobs
   ```

8. To bring a background job to foreground:
   ```bash
   fg %1
   ```

9. To send a foreground job back to background:
   - Press `Ctrl + Z` to pause it, then:
   ```bash
   bg %1
   ```

---

## ⚙️ Configuration Commands

### Shell Script: `system_info.sh`

```bash
#!/bin/bash

echo "Number of users currently logged in:"
who | wc -l

echo "Files in home directory (column format):"
ls -C $HOME

echo "Running a job with lower priority:"
nice -n 10 sleep 60 &

echo "Running a background job that survives logout:"
nohup sleep 120 &
```

### Commands Reference

| Command        | Description                                      |
|----------------|--------------------------------------------------|
| `who`          | Display currently logged-in users                |
| `who \| wc -l` | Count the number of logged-in users              |
| `ls -C $HOME`  | List home directory files in column format       |
| `nice -n 10`   | Run a process with lower CPU priority (value 10) |
| `nohup`        | Keep process running after user logout           |
| `jobs`         | List all current background jobs                 |
| `fg %n`        | Bring job number n to the foreground             |
| `bg %n`        | Resume job number n in the background            |
| `chmod +x`     | Make a script file executable                    |

---

## 📊 Observations / Results

```
Number of users currently logged in:
2

Files in home directory:
Desktop   Documents   Downloads

[1] 3456   (nice -n 10 sleep 60 running in background)
[2] 3457   (nohup sleep 120 running in background)
```

**Observations:**
- The `who | wc -l` command correctly counted and displayed the number of active user sessions.
- The `ls -C $HOME` command listed all files in the home directory in a clean column layout.
- The `nice -n 10 sleep 60 &` command launched a background process with reduced CPU priority, assigned Job ID `[1]`.
- The `nohup sleep 120 &` command launched a background process immune to logout, assigned Job ID `[2]`.
- Both background jobs were visible using the `jobs` command.

> 📷 *(Attach terminal screenshots here showing script execution and job output)*

---

## ✅ Conclusion

A Bash shell script was successfully written and executed to perform the following tasks:

- Displayed the count of users currently logged into the system using `who | wc -l`.
- Listed the home directory contents in column format using `ls -C`.
- Launched a background process with lower CPU scheduling priority using `nice -n 10`.
- Launched a background process that persists after logout using `nohup`.

This experiment demonstrates how Linux provides powerful tools for user session monitoring, process priority management, and job control — all essential skills for system administration.
