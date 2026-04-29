# Experiment: Date Command & Execution Time Measurement in Linux

---

## 📌 Aim

To write and execute a Bash shell script that displays the system date and time in a customized format and measures the execution time of a script using the `date` and `time` commands.

---

## 🎯 Objective

- Display the current system date in `DD-MM-YYYY` format using the `date` command.
- Display the current system time in `HH:MM:SS` format.
- Measure the execution time of a script internally using `date +%s` timestamps.
- Measure the overall script execution time using the `time` command.
- Understand format specifiers supported by the `date` command.

---

## 📚 Theory

### Date Command in Linux

The `date` command in Linux is used to display or set the system date and time. It supports format specifiers that allow fully customized output.

**Common Format Specifiers:**

| Specifier | Description |
|-----------|-------------|
| `%d`      | Day of the month (01–31) |
| `%m`      | Month (01–12) |
| `%Y`      | Full Year (e.g., 2026) |
| `%H`      | Hour in 24-hour format (00–23) |
| `%M`      | Minutes (00–59) |
| `%S`      | Seconds (00–59) |

### Execution Time Measurement

The execution time of a command or script can be measured using two approaches:

- **`time` command** – Wraps around a command and reports real, user, and system time after execution.
- **Internal timestamps using `date +%s`** – Captures Unix epoch time (seconds since Jan 1, 1970) at the start and end of a block, and computes the difference to get elapsed time.

---

## 🛠️ Step-by-Step Procedure

1. Open the terminal.

2. Create a new shell script file:
   ```bash
   nano date_time.sh
   ```

3. Type the script content (see Configuration Commands below).

4. Save and exit:
   - Press `Ctrl + O` to save.
   - Press `Ctrl + X` to exit nano.

5. Make the script executable:
   ```bash
   chmod +x date_time.sh
   ```

6. Run the script with execution time measurement:
   ```bash
   time ./date_time.sh
   ```

---

## ⚙️ Configuration Commands

### Shell Script: `date_time.sh`

```bash
#!/bin/bash

echo "Current Date (DD-MM-YYYY):"
date +"%d-%m-%Y"

echo "Current Time (HH:MM:SS):"
date +"%H:%M:%S"

start_time=$(date +%s)
sleep 2
end_time=$(date +%s)

execution_time=$((end_time - start_time))
echo "Execution Time: $execution_time seconds"
```

### Commands Reference

| Command              | Description                                          |
|----------------------|------------------------------------------------------|
| `date +"%d-%m-%Y"`   | Display date in DD-MM-YYYY format                    |
| `date +"%H:%M:%S"`   | Display time in HH:MM:SS format                      |
| `date +%s`           | Get current Unix epoch time in seconds               |
| `sleep 2`            | Pause execution for 2 seconds                        |
| `$((end - start))`   | Arithmetic to calculate elapsed execution time       |
| `time ./script.sh`   | Measure total real/user/sys time of script execution |
| `chmod +x`           | Make the script file executable                      |
| `echo`               | Print output to the terminal                         |

---

## 📊 Observations / Results

```
Current Date (DD-MM-YYYY):
10-01-2026

Current Time (HH:MM:SS):
10:45:32

Execution Time: 2 seconds

real    0m2.01s
user    0m0.00s
sys     0m0.01s
```

**Observations:**
- The `date +"%d-%m-%Y"` command correctly displayed the system date in the requested format.
- The `date +"%H:%M:%S"` command displayed the current time accurately.
- The internal timestamp method using `date +%s` correctly calculated an elapsed time of **2 seconds** (due to `sleep 2`).
- The `time` command reported real execution time as approximately **2.01 seconds**, matching the expected delay.

> 📷 *(Attach terminal screenshots here showing script execution and output)*

---

## ✅ Conclusion

A Bash shell script was successfully written and executed to:

- Display the current system date and time using customized format specifiers with the `date` command.
- Measure internal script execution time using Unix epoch timestamps (`date +%s`).
- Measure the overall script runtime using the `time` command.

This experiment demonstrates how Linux provides flexible tools for date/time formatting and performance evaluation — both of which are essential in scripting, logging, and system administration tasks.
