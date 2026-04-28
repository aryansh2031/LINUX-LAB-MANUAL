# Experiment 4: 

Title :
File Management and Input/Output Redirection in Linux

## Aim
To study and practice essential Linux file management commands such as creating, copying, moving, renaming, viewing, and deleting files, and to understand the use of input and output redirection.

## Theory
Linux provides commands like touch, cp, mv, rm, cat and redirection operators >, >>, < for efficient file operations and automation.

## Commands Used
| Command | Description |
|---------|-------------|
| touch   | Create empty files |
| cp      | Copy files |
| mv      | Move/rename |
| rm      | Delete |
| cat     | View content |
| echo >  | Output redirection (overwrite) |
| echo >> | Append |

## Step-by-Step Procedure
1. `mkdir file_ops && cd file_ops`
2. `touch file1.txt file2.txt`
3. `echo "This is file1" > file1.txt`
4. `echo "This is file2" > file2.txt`
5. `cat file1.txt`
6. `cp file1.txt copy_file1.txt`
7. `mv file2.txt renamed_file2.txt`
8. `mkdir backup && mv copy_file1.txt backup/`
9. `echo "Additional content" >> file1.txt`
10. `rm renamed_file2.txt`
11. `ls`

## Configuration Commands
mkdir file_ops
cd file_ops
touch file1.txt file2.txt
echo "This is file1" > file1.txt
echo "This is file2" > file2.txt
cat file1.txt
cp file1.txt copy_file1.txt
mv file2.txt renamed_file2.txt
mkdir backup
mv copy_file1.txt backup/
echo "Additional content" >> file1.txt
rm renamed_file2.txt
ls

Outcomes:  
 • Create, delete, copy, move, and rename files using Linux commands such as touch, rm, 
   cp, and mv. 
 • Display and examine file contents using commands like cat, less, more, and head/tail. 
 • Apply input (<) and output (>, >>) redirection to manage command outputs efficiently. 
 • Use file management commands safely and effectively in real-world scenarios. 
 • Automate file operations using basic shell scripting techniques. 
 • Understand the importance of file management in system administration and 
   cybersecurity tasks.

Result:  
 • Files are successfully created, copied, moved, renamed, and deleted as instructed. 
 • File contents are displayed correctly using appropriate commands. 
 • Output redirection (>, >>) creates or appends to files as expected. 
 • Input redirection (<) correctly supplies data to commands. 
 • No unintended data loss occurs during file operations when proper options are used.
