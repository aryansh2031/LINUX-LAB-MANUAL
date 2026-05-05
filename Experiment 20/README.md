## Experiment Title / Aim

**Computing GCD, LCM, and Prime Number Check Using Bash Scripting**

To write a Bash shell script that accepts user input to compute the Greatest Common Divisor (GCD) and Least Common Multiple (LCM) of two numbers, and checks whether a given number is prime — demonstrating arithmetic operations, looping constructs, and decision-making in Bash scripting.

---

## Objective

- To accept numerical input from the user in a shell script.
- To compute the GCD of two numbers using an iterative (Euclidean) method.
- To compute the LCM using the mathematical relationship between GCD and LCM.
- To determine whether a given number is prime using loop-based divisibility logic.

---

## Theory

### Greatest Common Divisor (GCD)
The GCD of two integers is the largest positive integer that divides both numbers without leaving a remainder. It is computed using the **Euclidean algorithm**, which repeatedly replaces the larger number with the remainder of dividing the two numbers until the remainder becomes zero.

```
GCD(12, 18):
  18 % 12 = 6  →  GCD(12, 6)
  12 % 6  = 0  →  GCD = 6
```

### Least Common Multiple (LCM)
The LCM of two integers is the smallest positive integer divisible by both. It is derived from the GCD using the formula:

```
LCM(a, b) = (a × b) / GCD(a, b)
```

This avoids iterative multiples and computes the result directly in one step.

### Prime Number
A prime number is a natural number greater than 1 that has exactly two distinct divisors: 1 and itself. To check primality, the script tests divisibility of the number by every integer from 2 up to `n/2`. If any divisor is found, the number is not prime.

```
13 → not divisible by 2, 3, 4, 5, 6  →  Prime
12 → divisible by 2                   →  Not Prime
```

### Arithmetic in Bash
Bash performs integer arithmetic using the `$(( ))` construct:

```bash
result=$((a * b))       # Multiplication
remainder=$((x % y))    # Modulo
quotient=$((a / b))     # Division
```

---

## Step-by-Step Procedure

### Step 1 — Open the Terminal
Launch the Linux terminal from the applications menu or press `Ctrl + Alt + T`.

### Step 2 — Create the Shell Script
```bash
nano math_ops.sh
```

### Step 3 — Enter the Script
Type the following script into the editor:

```bash
#!/bin/bash

echo "Enter first number:"
read a

echo "Enter second number:"
read b

x=$a
y=$b

# GCD calculation using Euclidean algorithm
while [ $y -ne 0 ]
do
    temp=$y
    y=$((x % y))
    x=$temp
done

gcd=$x
lcm=$(( (a * b) / gcd ))

echo "GCD of $a and $b is: $gcd"
echo "LCM of $a and $b is: $lcm"

echo "Enter a number to check for prime:"
read n

flag=0

if [ $n -le 1 ]; then
    flag=1
fi

for ((i=2; i<=n/2; i++))
do
    if [ $((n % i)) -eq 0 ]; then
        flag=1
        break
    fi
done

if [ $flag -eq 0 ]; then
    echo "$n is a Prime Number"
else
    echo "$n is NOT a Prime Number"
fi
```

Save and exit: `Ctrl + O` → `Enter` → `Ctrl + X`

### Step 4 — Make the Script Executable
```bash
chmod +x math_ops.sh
```

### Step 5 — Run the Script
```bash
./math_ops.sh
```

### Step 6 — Enter Input When Prompted
Provide two numbers for GCD/LCM computation, then a third number for the prime check.

---

## Configuration Commands

| Command | Purpose |
|---|---|
| `nano math_ops.sh` | Create and edit the shell script |
| `chmod +x math_ops.sh` | Grant execute permission to the script |
| `./math_ops.sh` | Execute the shell script |
| `read a` / `read b` / `read n` | Accept numerical input from the user |
| `while [ $y -ne 0 ]` | Loop until remainder becomes zero (Euclidean algorithm) |
| `y=$((x % y))` | Compute modulo for GCD step |
| `lcm=$(( (a * b) / gcd ))` | Calculate LCM using the GCD formula |
| `for ((i=2; i<=n/2; i++))` | Loop to test divisibility for prime check |
| `[ $((n % i)) -eq 0 ]` | Check if `n` is divisible by `i` |
| `break` | Exit the loop early when a divisor is found |

---

## Observations / Results

On executing `./math_ops.sh` with inputs `12`, `18`, and `13`, the following output was observed:

```
Enter first number:
12
Enter second number:
18
GCD of 12 and 18 is: 6
LCM of 12 and 18 is: 36
Enter a number to check for prime:
13
13 is a Prime Number
```

**Observations:**
- The script correctly accepted three separate numerical inputs from the user.
- The Euclidean `while` loop computed GCD of 12 and 18 as **6** accurately.
- The LCM was correctly calculated as **(12 × 18) / 6 = 36** using the formula.
- The prime-checking loop tested divisibility of 13 from 2 to 6 and found no divisors, correctly identifying it as a **Prime Number**.
- The `flag` variable effectively tracked divisibility state and drove the final `if-else` decision.
- The script executed without any errors and produced correctly formatted output.

---

## Conclusion

The experiment was completed successfully. A Bash shell script was written and executed to compute the GCD and LCM of two numbers and to check whether a given number is prime. The experiment demonstrated the use of the Euclidean algorithm implemented via a `while` loop for GCD computation, the mathematical LCM formula using arithmetic expansion `$(( ))`, a `for` loop with divisibility checks for prime detection, a `flag` variable combined with `if-else` logic for conditional decision-making, and `break` for early loop termination. These techniques form the foundation of computational scripting and can be extended to more complex mathematical automation tasks in Linux environments.
