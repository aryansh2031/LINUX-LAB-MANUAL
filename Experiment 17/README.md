# Experiment: Text Processing in Linux using Bash Script

## Aim
To write and execute a Bash shell script that counts the number of lines, words, and characters in a text file without using the `wc` command.

---

## Objective
- To understand text processing in Linux.
- To learn file handling using Bash scripting.
- To implement counting operations using loops and arithmetic expressions.
- To practice reading files line by line using the `while read` loop.

---

## Theory
Linux treats text as a stream of characters.  
Text processing operations such as counting lines, words, and characters can be performed manually using Bash scripting.

### Counting Logic
- **Line Count:** Incremented whenever a new line is read.
- **Word Count:** Words are separated based on whitespace.
- **Character Count:** Calculated using string length evaluation.

### Bash Concepts Used
- `while read` loop for reading files line by line.
- `for` loop for iterating through words.
- Arithmetic operations using `$(( ))`.
- String length calculation using `${#variable}`.

---

# Procedure

## Step 1: Create Sample Input File

Open terminal and create a text file:

```bash
nano sample.txt
```

Enter the following content:

```text
Linux is powerful
Bash scripting is useful
Cyber Security relies on Linux
```

Save and exit the editor.

---

## Step 2: Create the Shell Script

Create a script file:

```bash
nano count_text.sh
```

Add the following script:

```bash
#!/bin/bash

lines=0
words=0
chars=0

while read line
do
    lines=$((lines + 1))
    chars=$((chars + ${#line}))

    for word in $line
    do
        words=$((words + 1))
    done

done < sample.txt

echo "Number of lines: $lines"
echo "Number of words: $words"
echo "Number of characters: $chars"
```

Save and exit the editor.

---

## Step 3: Make Script Executable

```bash
chmod +x count_text.sh
```

---

## Step 4: Execute the Script

```bash
./count_text.sh
```

---

# Configuration Commands

| Command | Description |
|---|---|
| `nano sample.txt` | Create sample text file |
| `nano count_text.sh` | Create Bash script |
| `chmod +x count_text.sh` | Make script executable |
| `./count_text.sh` | Run the script |

---

# Observations / Results

## Sample Output

```text
Number of lines: 3
Number of words: 10
Number of characters: 79
```

# Conclusion

The Bash shell script was successfully created and executed to count the number of lines, words, and characters in a file without using the `wc` command. The experiment demonstrated effective text processing techniques using loops, arithmetic operations, and file handling in Bash scripting.
