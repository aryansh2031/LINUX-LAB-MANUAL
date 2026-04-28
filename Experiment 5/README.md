# Experiment 5: 

Title:
Text Pattern Searching and Log Analysis in Linux Using grep

## Aim
To understand and implement Linux text-searching commands such as grep, fgrep and related options for log analysis and troubleshooting.

## Theory
grep searches patterns in files. Options like -i, -n, -r, -v make it powerful for log analysis.

## Commands Used
| Command       | Description |
|---------------|-------------|
| grep          | Search pattern |
| grep -i       | Case insensitive |
| grep -n       | Show line numbers |
| grep -v       | Invert match |
| fgrep / grep -F | Fixed string search |
| grep -r       | Recursive |

## Step-by-Step Procedure
1. `mkdir grep_lab && cd grep_lab`
2. Create `sample.txt` with content
3. `cat sample.txt`
4. `grep Linux sample.txt`
5. `grep -i linux sample.txt`
6. `grep -n Linux sample.txt`
7. `grep -v Linux sample.txt`
8. `fgrep "Bash scripting" sample.txt`
9. `grep -r Linux` (if multiple files)

## Configuration Commands
mkdir grep_lab
cd grep_lab
# nano sample.txt (add lines)
cat sample.txt
grep Linux sample.txt
grep -i linux sample.txt
grep -n Linux sample.txt
grep -v Linux sample.txt
fgrep "Bash scripting" sample.txt

Outcomes:  
 • Use grep, fgrep, and related commands to search for specific patterns in text files. 
 • Apply various search options such as case-insensitive search (-i), recursive search (-r), 
   inverted match (-v), line numbers (-n), and count (-c). 
 • Analyze log files to identify errors, warnings, and important system events. 
 • Combine search commands with other Linux utilities using pipes (|) for advanced filtering. 
 • Automate pattern-search tasks in scripts for efficient system administration. 
 • Understand the role of text-searching tools in troubleshooting and cybersecurity 
   monitoring. 
   
Result:  
 • Lines matching the specified search pattern are correctly displayed. 
 • Line numbers are shown when the appropriate option is used. 
 • Case-insensitive searches return accurate results. 
 • Inverted searches successfully display non-matching lines. 
 • Recursive searches correctly scan directories and subdirectories. 
 • The count option accurately displays the number of matching lines. 
