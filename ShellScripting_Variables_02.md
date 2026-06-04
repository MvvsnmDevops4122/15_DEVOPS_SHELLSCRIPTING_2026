# Variables in Shell Scripting

* Variables are used to store data or values that can be accessed and manipulated throughout a shell script.

### Syntax

```bash
variable_name=value
```

### Example

```bash
name="Satya"
age=25

echo $name
echo $age
```

Output:

```bash
Satya
25
```

---

## Variable Naming and Assignment

### Variable Naming Rules

- Variable names can contain letters (`a-z`, `A-Z`), digits (`0-9`), and underscores (`_`).
- They **must start** with a letter or an underscore.
- Variable names are **case-sensitive** (`myVar` ≠ `MYVAR`).
- Variable names **cannot** start with a number.

### Variable Assignment
Assign values using `=` **without spaces**.

Example:
```bash
myVar="Hello, World!"
````

Quotes preserve spaces and special characters.

### Accessing Variables

Use `$` before variable name.

```bash
echo "The value of myVar is: $myVar"
```

### Variable Expansion

```bash
name="Alice"
echo "Hello, $name!"
```

### Concatenation

```bash
greeting="Hello"
target="World"
echo "$greeting, $target!"
```

---

## Types of Variables

### 1. Environment Variables (System Defined Variables)

* System-defined variables available to the current shell and child processes.

### Common Environment Variables

```bash
echo $USER
echo $HOME
echo $PATH
echo $SHELL
echo $PWD
```

### View All Environment Variables

```bash
env
printenv
```

Example:

```bash
echo "Current user: $USER"
```

### Setting Environment Variables

```bash
export NAME="Satya"

echo $NAME
```

### Making Environment Variables Permanent

```bash
vim ~/.bash_profile
```

Add:

```bash
export NAME="Satya"
```

Apply changes:

```bash
source ~/.bash_profile
```

---

### 2. Local Variables (User Defined Variables)

* Variables created inside a script and accessible only within that script.

Example:

```bash
a=10
b=90
name="kkfunda"

echo $a
echo $b
echo $name
```

---

### 3. Special Variables

* Special variables are predefined by the shell.

| Variable | Description                              |
| -------- | ---------------------------------------- |
| `$0`     | Script name                              |
| `$1`     | First argument                           |
| `$2`     | Second argument                          |
| `$#`     | Number of arguments passed to script     |
| `$@`     | All arguments individually               |
| `$*`     | All arguments as a single string         |
| `$$`     | Process ID (PID)                         |
| `$?`     | Exit status of previous command          |


---

# Exit Status Codes

Every command returns an exit status.

| Exit Code | Meaning           |
| --------- | ----------------- |
| 0         | Success           |
| 1         | General Error     |
| 126       | Permission Denied |
| 127       | Command Not Found |

### Example

```bash
pwd
echo $?
```

Output:

```bash
0
```

---

## Command Line Arguments in Shell Scripting

Used to pass values when running a script.

| Parameter | Meaning         |
| --------- | --------------- |
| `$0`      | Script name     |
| `$1`      | First argument  |
| `$2`      | Second argument |

For arguments beyond 9, use braces:

```
${10}
```

### Example Script

```bash
#!/bin/bash
echo "Script name: $0"
echo "First argument: $1"
echo "Second argument: $2"
```

Execution:

```bash
sh Demo.sh Prasanth reddy
```

# Command Line Arguments

Arguments passed while executing a script.

### Script

```bash
#!/bin/bash

echo "Script Name : $0"
echo "First Argument : $1"
echo "Second Argument : $2"
```

### Execution

```bash
sh demo.sh Satya DevOps
```

### Output

```bash
Script Name : demo.sh
First Argument : Satya
Second Argument : DevOps
```

### Accessing Arguments Greater Than 9

```bash
${10}
${11}
```

---

### 🧾 How to Read a Value at Runtime in Shell Scripting

# Reading User Input

## Basic Input

```bash
read name

echo "Hello $name"
```

---

## Input with Prompt

# What is read -p?

read = takes input from the user.

-p = displays a message (prompt) before taking input.

```bash
read -p "Enter your age: " age

echo $age
```

---

## Reading Multiple Inputs

```bash
read name age

echo "$name $age"
```

Input:

```bash
Satya 25
```

Output:

```bash
Satya 25
```

---

##  Reading Input with Timeout
```bash
#!/bin/bash

# Read user input with a timeout of 10 seconds
read -t 10 -p "Enter password: " password

echo

# Check if the user entered a value
if [ -z "$password" ]; then
    echo "No password entered within 10 seconds."
else
    echo "Password entered: $password"
fi
```
---

##  Reading Input Silently (Password Input - Secure)

```bash
#!/bin/bash

# Read password without displaying characters on the screen
read -s -p "Enter your password: " password

echo
echo "Password entered successfully."
```
---
# Real-Time DevOps Example

```bash
#!/bin/bash

server_name=$(hostname)
current_date=$(date)

echo "Server Name : $server_name"
echo "Date : $current_date"
```

### Use Case

Used in monitoring, automation, backup, deployment, and reporting scripts to dynamically capture system information.

---
