## Experiment Title / Aim

**Monitoring User Login Status at Regular Intervals Using Bash Scripting**

To write a Bash shell script that checks whether a specified user is logged in to the system and continues checking at regular intervals of 30 seconds until the user logs in — demonstrating looping, conditional checks, and time-based execution in Bash scripting.

---

## Objective

- To check the login status of a specific user using built-in Linux commands.
- To implement conditional logic to evaluate whether a user is currently logged in.
- To use looping constructs for repeated, automated checks.
- To introduce controlled time delays in scripts using the `sleep` command.

---

## Theory

### User Login Monitoring in Linux
Linux provides several commands to display information about currently logged-in users:

| Command | Description |
|---|---|
| `who` | Lists all users currently logged into the system along with terminal and login time |
| `users` | Displays only the usernames of currently logged-in users |
| `w` | Shows who is logged in and what they are doing |

By piping the output of `who` into `grep`, a script can filter and detect whether a specific username is active on the system.

```bash
who | grep -w "username"
```

The `-w` flag ensures an exact whole-word match, preventing false positives (e.g., matching `student1` when searching for `student`).

### Looping with Delay
A `while true` loop runs indefinitely until a `break` statement is reached. Combined with the `sleep` command, it enables periodic checks at fixed time intervals — a pattern widely used in monitoring scripts, health checks, and security automation.

```bash
while true
do
    # check condition
    sleep 30   # wait 30 seconds before next check
done
```

### Redirecting to /dev/null
Redirecting command output to `/dev/null` suppresses it from the terminal. This is used when only the exit status of a command matters, not its output.

```bash
who | grep -w "$username" > /dev/null
```

---

## Step-by-Step Procedure

### Step 1 — Open the Terminal
Launch the Linux terminal from the applications menu or press `Ctrl + Alt + T`.

### Step 2 — Create the Shell Script
```bash
nano check_login.sh
```

### Step 3 — Enter the Script
Type the following script into the editor:

```bash
#!/bin/bash

echo "Enter the username to check:"
read username

while true
do
    if who | grep -w "$username" > /dev/null
    then
        echo "User $username is now logged in."
        break
    else
        echo "User $username is not logged in. Checking again in 30 seconds..."
        sleep 30
    fi
done
```

Save and exit: `Ctrl + O` → `Enter` → `Ctrl + X`

### Step 4 — Make the Script Executable
```bash
chmod +x check_login.sh
```

### Step 5 — Run the Script
```bash
./check_login.sh
```

### Step 6 — Enter the Username When Prompted
Type a valid system username and press `Enter`.

### Step 7 — Trigger a Login to Observe Behavior
Open a second terminal and log in as the specified user to observe the script detect the login and terminate automatically.

---

## Configuration Commands

| Command | Purpose |
|---|---|
| `nano check_login.sh` | Create and edit the shell script |
| `chmod +x check_login.sh` | Grant execute permission to the script |
| `./check_login.sh` | Execute the shell script |
| `who` | Display all currently logged-in users |
| `grep -w "$username"` | Search for an exact whole-word username match |
| `> /dev/null` | Suppress command output; retain only exit status |
| `sleep 30` | Pause script execution for 30 seconds |
| `break` | Exit the `while` loop once the condition is met |

---

## Observations / Results

On executing the script `./check_login.sh` and entering the username `student`, the following output was observed:

```
Enter the username to check:
student
User student is not logged in. Checking again in 30 seconds...
User student is not logged in. Checking again in 30 seconds...
User student is now logged in.
```

**Observations:**
- The script prompted the user to enter a username and accepted it via standard input.
- The `while true` loop repeatedly checked the login status at 30-second intervals.
- The `who | grep -w` pipeline correctly identified when the target user logged in.
- A status message was printed during each check cycle, confirming the script was active.
- The script terminated automatically with a confirmation message as soon as the user logged in.

---

## Conclusion

The experiment was completed successfully. A Bash shell script was written and executed to monitor the login status of a specified user and recheck every 30 seconds until the user logged in. The experiment demonstrated the effective use of `while true` loops for continuous monitoring, `if-else` conditional logic for evaluating login status, the `who` and `grep` commands for filtering active user sessions, the `sleep` command for introducing timed delays, and `break` for controlled loop termination. This scripting pattern has direct real-world applications in system administration, automated security monitoring, and event-driven task scheduling in multi-user Linux environments.
