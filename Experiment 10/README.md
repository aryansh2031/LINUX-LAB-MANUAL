Experiment 10: Exploring Linux Inodes, I/O Redirection, Piping, and Process Control

Aim:
  To understand the concept of inodes in Linux, practice input/output (I/O) redirection and piping, and use process control commands to manage running processes in a Linux environment.

Objective:
  - Learn about inodes and their role in the Linux filesystem.  
  - Apply I/O redirection to save and read command outputs.  
  - Use pipes to chain commands efficiently.  
  - Monitor and control Linux processes using process control commands.

Step-by-Step Procedure:

 A. Understanding Inodes:
  1. Log in to the Linux virtual machine and open the Terminal.  
  2. Create a test file: `touch inode_test.txt`  
  3. Display inode number: `ls -i inode_test.txt`  
  4. View inode details: `stat inode_test.txt`  

 B. Input / Output Redirection:
  5. Redirect output to a file: `ls > file_list.txt`  
  6. Append output: `date >> file_list.txt`  
  7. Redirect input: `wc -l < file_list.txt`  

 C. Using Pipes:
  8. Combine commands with pipe: `ls -l | grep ".txt"`  
  9. Count number of text files: `ls | grep ".txt" | wc -l`  

 D. Process Control Commands:
  10. Display running processes: `ps`  
  11. Monitor processes in real-time: `top`  
  12. Run a command in background: `sleep 60 &`  
  13. List background jobs: `jobs`  
  14. Bring job to foreground: `fg`  
  15. Terminate a process: `kill <PID>`  

Results:
  - Each file in Linux has a unique inode containing metadata such as file type, permissions, owner, size, and timestamps.  
  - I/O redirection stores or reads data from files effectively.  
  - Pipes allow chaining commands for efficient data processing.  
  - Process control commands help monitor, suspend, resume, and terminate processes.

Conclusion:
  This experiment enhanced understanding of Linux file management via inodes, efficient input/output redirection, command chaining using pipes, and process management. These skills are essential for automation, scripting, and system administration.
