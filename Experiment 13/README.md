Experiment 13: 

Experiment Title:
File Operations and Automation Using Bash Scripting in Linux

Aim:
To write and execute a Bash shell script that automates file and directory operations in Linux, including creating directories and files, copying content between files, displaying file contents from a specific line, and comparing two files.

Theory:
Linux allows automation of repetitive file operations through Bash scripting. Shell scripts use standard Linux commands such as mkdir, cp, tail, and diff to manage files programmatically. This reduces manual effort and minimizes human errors in tasks like log management, data processing, and system maintenance. File redirection operators (> and >>) are used to write and append content to files respectively.
Commands Used
Command	Description
mkdir	Create directories
cd	Change to a directory
echo	Write or append text to a file
cp	Copy file contents to another file
tail	Display file contents from a specified line onward
diff	Compare two files and show differences
chmod	Change script file permissions
nano	Create and edit the shell script

Step-by-Step Procedure
1.	Open the terminal on Kali Linux.
2.	Create the script file: nano file_ops.sh
3.	Enter the following script:

#!/bin/bash
mkdir -p $HOME/class/batch
cd $HOME/class/batch
echo "This is the original file." > profile.txt
echo "Welcome to Linux Bash Scripting Lab." >> profile.txt
cp profile.txt copy_profile.txt
echo "Printing file content from line 2:"
tail -n +2 profile.txt
echo "Differences between Files:"
diff profile.txt copy_profile.txt
4.	Save and exit: Ctrl+O → Enter → Ctrl+X
5.	Make the script executable: chmod +x file_ops.sh
6.	Run the script: ./file_ops.sh

Screenshots
Step 1 – Creating the script file using nano file_ops.sh


Step 2 – Script content written in nano editor
 

Step 3 – Making script executable with chmod +x
 

Step 4 – Running the script and viewing output
 

Configuration Commands:
 nano file_ops.sh
 chmod +x file_ops.sh
 ./file_ops.sh
 tail -n +2 profile.txt
 diff profile.txt copy_profile.txt

Outcomes:
 Directory class/batch successfully created inside the home directory
 Files profile.txt and copy_profile.txt created and populated with content
 File content displayed from line 2 onward using tail
 File comparison performed using diff (no differences found — files are identical)

Result:
 Thus, a shell script was successfully written and executed to automate file creation,
 content copying, selective printing, and file comparison operations in Linux.
 The student learned to use Bash scripting for file manipulation and automation of
 directory operations using standard Linux commands.
