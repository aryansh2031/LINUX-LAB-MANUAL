# Experiment Title / Aim
**Title:** Implementation of Bash Shell Scripts for Automation Using Input, Conditions, and Loops  
**Aim:** To write and execute Bash shell scripts that automate basic tasks by using interactive user input, positional parameters, arithmetic operations, conditional statements, and loop constructs.

## Objective
- Learn to write interactive shell scripts that accept user input during execution.
- Understand positional parameters and how they are used in shell scripts.
- Implement arithmetic operations in Bash.
- Use conditional statements (`if`, `if-else`, `elif`) to make decisions in scripts.
- Implement loops (`for`, `while`, `until`) for repeating tasks.

## Theory
### Shell Programming
Shell scripting is a method of automating tasks by writing a sequence of Linux commands in a script file that is executed by the shell.

### Interactive Scripts
Interactive scripts accept input from the user during execution using the `read` command.

### Positional Parameters
Shell scripts accept command-line arguments using:
- `$0` – Script name
- `$1`, `$2`, ... – Positional parameters

### Arithmetic Operations
Arithmetic can be performed using:
- `$((expression))`

### Conditional Statements
Decision-making constructs include:
- `if`
- `if-else`
- `elif`

### Loops
Loops such as `for`, `while`, and `until` are used to repeat tasks.


## Step-by-step Procedure

### A. Writing a Simple Interactive Script:
1. **Create a new script file** using:
   ```bash
   nano simple_script.sh
- Write a simple interactive script like:
  ```bash
  #!/bin/bash
  echo "Enter your name:"
  read name
  echo "Hello, $name!"

2. **Make the script executable** using:
   ```bash
   chmod +x simple_script.sh
3. Execute the script using:
   ```bash
   ./simple_script.sh

### B. Using Positional Parameters:
4. **Create a script that uses positional parameters**:
     ```bash
      #!/bin/bash
      echo "Script name: $0"
      echo "First parameter: $1"
      echo "Second parameter: $2"
   Run it with parameters: 
     ./param_script.sh param1 param2

### C. Performing Arithmetic Operations:
5. **Create a script for arithmetic**:
   ```bash
    #!/bin/bash
   num1=5
   num2=10
   result=$((num1 + num2))
   echo "Result of addition: $result"

6. **Execute the script**:
   ```bash
    ./arithmetic_script.sh

### D. Using Conditional Statements:
7. **Create a script with conditional logic:**
   ```bash
   #!/bin/bash
   echo "Enter your age:"
   read age
   if [ $age -ge 18 ]; then
      echo "You are an adult."
   else
     echo "You are a minor."
   fi

8. **Execute the script**:
   ```bash
   ./conditional_script.sh

### E. Using Loop:
9. ** Create a script with a loop:**
   ```bash
   #!/bin/bash
   for i in {1..5}
   do
    echo "Iteration $i"
   done
10. **Execute the script**:
    ```bash
    ./loop_script.sh

Configuration Commands:

- nano simple_script.sh - Opens the Nano editor to create the script.
- chmod +x simple_script.sh - Makes the script executable.
- ./simple_script.sh - Executes the script.
- ./param_script.sh param1 param2 - Runs the script with positional parameters.
- ./arithmetic_script.sh - Executes the arithmetic script.
- ./conditional_script.sh - Executes the script with conditional logic.
- ./loop_script.sh - Executes the script with loops.

Observations / Results:

The interactive script successfully accepts user input.
Positional parameters can be accessed within a script.
Arithmetic operations in Bash are executed using $((expression)).
Conditional statements work as expected to make decisions.
Loops allow repeated tasks based on a condition.

Conclusion:

This experiment helped in understanding how to automate tasks in Linux using Bash scripts. The use of user input, positional parameters, arithmetic, conditional statements, and loops is crucial for building efficient and dynamic shell scripts.

 
