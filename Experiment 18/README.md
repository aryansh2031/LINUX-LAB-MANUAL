## Experiment Title / Aim

**Reading and Displaying Glossary File Entries in Reverse Order Using Bash Arrays**

To write a Bash shell script that reads the last few lines of a glossary file, stores them in an array, and prints them in reverse order — demonstrating the use of arrays and reverse traversal in Bash scripting.

---

## Objective

- To read file content line by line and store it in a Bash array.
- To access and manipulate indexed array elements in Bash.
- To print file content in reverse order using a reverse loop.
- To apply array-based scripting logic to a real-world text processing task.

---

## Theory

### Arrays in Bash
A Bash array stores multiple values under a single variable name, each accessed by a numeric index. Arrays are declared using `declare -a` and elements are assigned as `array[index]=value`.

```bash
declare -a array_name     # Declare an array
array[0]="value"          # Assign element
echo ${array[@]}          # Access all elements
echo ${#array[@]}         # Get array length
```

### The `tail` Command
The `tail` command outputs the last N lines of a file. Using `tail -n 5 filename` fetches the last 5 lines, which are then fed into a loop via process substitution.

### Reverse Traversal
Reverse traversal accesses array elements from the last index down to zero using a C-style `for` loop:

```bash
for ((i=index-1; i>=0; i--)); do
    echo "${array[$i]}"
done
```

### Process Substitution
The syntax `< <(command)` redirects the output of a command as input to a `while` loop, enabling line-by-line reading without spawning a subshell — this ensures array assignments persist after the loop.

---

## Step-by-Step Procedure

### Step 1 — Open the Terminal
Launch the Linux terminal from the applications menu or press `Ctrl + Alt + T`.

### Step 2 — Create the Glossary File
```bash
nano glossary.txt
```
Enter the following content:
```
Linux: Open-source operating system
Bash: Shell scripting language
Kernel: Core of operating system
File System: Structure for storing data
Networking: Communication between systems
```
Save and exit: `Ctrl + O` → `Enter` → `Ctrl + X`

### Step 3 — Create the Shell Script
```bash
nano reverse_glossary.sh
```
Enter the following script:
```bash
#!/bin/bash

declare -a lines
index=0

while read line
do
    lines[$index]="$line"
    index=$((index + 1))
done < <(tail -n 5 glossary.txt)

echo "Glossary entries in reverse order:"

for ((i=index-1; i>=0; i--))
do
    echo "${lines[$i]}"
done
```
Save and exit: `Ctrl + O` → `Enter` → `Ctrl + X`

### Step 4 — Make the Script Executable
```bash
chmod +x reverse_glossary.sh
```

### Step 5 — Run the Script
```bash
./reverse_glossary.sh
```

---

## Configuration Commands

| Command | Purpose |
|---|---|
| `nano glossary.txt` | Create and edit the glossary input file |
| `nano reverse_glossary.sh` | Create and edit the shell script |
| `chmod +x reverse_glossary.sh` | Grant execute permission to the script |
| `./reverse_glossary.sh` | Execute the shell script |
| `tail -n 5 glossary.txt` | Fetch the last 5 lines of the glossary file |
| `declare -a lines` | Declare an indexed Bash array |
| `index=$((index + 1))` | Increment index counter using arithmetic expansion |

---

## Observations / Results

On executing the script `./reverse_glossary.sh`, the following output was observed:

```
Glossary entries in reverse order:
Networking: Communication between systems
File System: Structure for storing data
Kernel: Core of operating system
Bash: Shell scripting language
Linux: Open-source operating system
```

**Observations:**
- The script successfully read the last 5 lines of `glossary.txt` using the `tail` command.
- All 5 lines were stored correctly in the Bash array `lines[]` with indices 0 through 4.
- The reverse `for` loop traversed the array from index 4 down to 0.
- Each glossary entry was printed in reverse order without any errors.
- The output was clean, correctly formatted, and matched the expected result.

---

## Conclusion

The experiment was completed successfully. A Bash shell script was written and executed to read the last few entries of a glossary file, store them in an indexed array, and display them in reverse order. The experiment demonstrated the practical use of Bash arrays for storing file content, the `tail` command for extracting the last N lines, process substitution for line-by-line reading, and C-style reverse loop traversal for accessing array elements from last to first. This approach can be directly applied to real-world tasks such as reversing log file entries, displaying recent records in descending order, and processing structured text files programmatically.
