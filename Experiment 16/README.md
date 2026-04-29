# Experiment: File Timestamps & Programmatic File Listing in Linux

---

## 📌 Aim

To write and execute a Bash shell script that lists files in a directory along with their serial numbers and modification timestamps, demonstrating file metadata extraction using `stat` and formatted output in Bash scripting.

---

## 🎯 Objective

- Understand the different types of file timestamps maintained by Linux (`atime`, `mtime`, `ctime`).
- Extract file modification timestamps programmatically using the `stat` command.
- List files with serial numbers and formatted dates using a Bash loop.
- Use `cut` to parse and clean timestamp output.
- Display structured tabular output from within a shell script.

---

## 📚 Theory

### File Timestamps in Linux

Linux maintains three types of timestamps for every file:

| Timestamp | Full Name          | Description                                      |
|-----------|--------------------|--------------------------------------------------|
| `atime`   | Access Time        | Last time the file was read or accessed          |
| `mtime`   | Modification Time  | Last time the file's content was modified        |
| `ctime`   | Change Time        | Last time the file's metadata/permissions changed|

> **Note:** Traditional Linux file systems do not always store true creation time. Therefore, `mtime` or `ctime` is commonly used to represent file creation or update information.

### Listing Files Programmatically

Using commands such as `ls`, `stat`, and shell loops, file information can be extracted and formatted within shell scripts. The `stat` command provides detailed metadata about a file, and the `-c` flag allows custom format output (e.g., `%y` for modification time).

---

## 🛠️ Step-by-Step Procedure

1. Open the terminal.

2. Create a new shell script file:
   ```bash
   nano file_info.sh
   ```

3. Type the script content (see Configuration Commands below).

4. Save and exit:
   - Press `Ctrl + O` to save.
   - Press `Ctrl + X` to exit nano.

5. Make the script executable:
   ```bash
   chmod +x file_info.sh
   ```

6. Navigate to a directory containing files, then run the script:
   ```bash
   ./file_info.sh
   ```

---

## ⚙️ Configuration Commands

### Shell Script: `file_info.sh`

```bash
#!/bin/bash

count=1
echo "S.No  File Name       Date"

for file in *
do
    if [ -f "$file" ]; then
        mod_date=$(stat -c %y "$file" | cut -d'.' -f1)
        echo "$count  $file  $mod_date"
        count=$((count + 1))
    fi
done
```

### Commands Reference

| Command                    | Description                                              |
|----------------------------|----------------------------------------------------------|
| `ls`                       | List files in the current directory                      |
| `stat -c %y "$file"`       | Display modification time (`mtime`) of a file            |
| `cut -d'.' -f1`            | Remove fractional seconds from the timestamp             |
| `for file in *`            | Loop through all items in the current directory          |
| `if [ -f "$file" ]`        | Check if the item is a regular file (not a directory)    |
| `count=$((count + 1))`     | Increment serial number counter using arithmetic         |
| `echo`                     | Print formatted output to the terminal                   |
| `chmod +x file_info.sh`    | Make the script executable                               |
| `awk`                      | Text processing utility for structured data formatting   |
| `date`                     | Display or format system date and time                   |

---

## 📊 Observations / Results

```
S.No  File Name       Date
1     file1.txt       2026-01-10 10:30:12
2     report.doc      2026-01-09 14:20:05
3     script.sh       2026-01-08 18:10:44
```

**Observations:**
- The script successfully iterated over all regular files in the directory using a `for` loop.
- The `if [ -f "$file" ]` condition correctly skipped subdirectories and listed only files.
- The `stat -c %y` command accurately retrieved the last modification time (`mtime`) for each file.
- The `cut -d'.' -f1` command cleanly removed the fractional seconds from the timestamp output.
- Each file was displayed with a proper serial number, file name, and formatted modification date.

> 📷 *(Attach terminal screenshots here showing script execution and output)*

---

## ✅ Conclusion

A Bash shell script was successfully written and executed to:

- Iterate through all regular files in a directory using a `for` loop.
- Extract each file's modification timestamp using the `stat` command.
- Display a neatly formatted table with serial numbers, file names, and modification dates.

This experiment demonstrates how Linux file metadata can be accessed and presented programmatically using Bash scripting — a useful skill in file auditing, logging, and system administration tasks.
