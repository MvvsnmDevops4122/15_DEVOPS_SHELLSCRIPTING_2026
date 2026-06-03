# Shell Scripting

## What is a Shell?

* A Shell is a command-line interpreter that acts as an interface between the user and the Linux operating system (Kernel).

* It accepts commands from the user, sends them to the Kernel for execution, and displays the results back to the user.

## How Shell Works

User
  ↓
Shell
  ↓
Kernel
  ↓
Hardware

## What is the difference between Shell and Kernel?

* Shell is the interface used by users to interact with the operating system, whereas the Kernel is the core component of the operating system that manages hardware and system resources.

## Functions of a Shell

* Executes commands
* Runs shell scripts
* Manages files and directories
* Supports variables and functions
* Supports automation through scripting
  

## Common Types of Shells

* Bash (Bourne Again Shell) - Most commonly used
* Sh (Bourne Shell)
* Ksh (Korn Shell)
* Csh (C Shell)
* Tcsh (TENEX C Shell)
* Zsh (Z Shell)


---

## How to Check Available Shells?

```bash
cat /etc/shells
````

---

## How to install csh?

```bash
sudo yum install csh -y
sudo yum install zsh -y
sudo yum install ksh -y
```

---

## How to Check Current Shell?

```bash
echo $SHELL
echo $0
ps -p $$
```

echo $SHELL

Example Output:  /bin/bash

---

## How switch to another shell?

Step 1: Check available shells:

```bash
cat /etc/shells
```

Step 2: Switch to another shell:

```bash
/bin/sh
ps -p $$
```

Step 3: Come back to bash:

```bash
/bin/bash
```

---

## What is shell scripting?

* Shell scripting is the process of writing a sequence of Linux commands in a file and executing them as a program.

* Commands are executed in the order they are written.

* Shell scripting is mainly used to automate repetitive and manual tasks.

---

## Extension of shell scripting

`.sh`

---

## Why we need to learn shell scripting?

* Shell scripting is mainly used to automate repetitive and manual tasks.
  
* To reduce manual effort.

* To save time and improve efficiency.

---

## Is it only for DevOps Engineers?

Ans: NO

Examples:

1. serverresourseutilization.sh
2. dbbackup.sh

---

## Prerequisites

1. Linux commands
2. Basic programming knowledge (depends)
3. Practice and Consistency
4. Problem solving skills

---

## How to write a shell script?

```bash
vi Demo.sh
```

Content:

```bash
#!/bin/bash  --> #! --> shebang line  ( tells the operating system which interpreter should execute the script.)
echo "Welcome to shellscript KK FUNDA"
echo "Today date is"
date
pwd
```

---

## Ways to run shell script

```bash
sh Demo.sh
./Demo.sh   # chmod u+x Demo.sh
. Demo.sh
bash Demo.sh
```

---

## Will the script work on Windows?

NO

Linux server → shell scripting (platform dependent)
Windows server → PowerShell (platform dependent)
Python → platform independent

---

## Debug Mode

Full script debug:

```bash
sh -x Demo.sh
```

Debug part of script:

```bash
set -x
echo "Welcome to shellscript KK FUNDA"
echo "Today date is"
set +x
date
```

---

## Shebang line

```bash
#!/bin/bash x
```

---

## Comments in Shell Scripting

* Improve code readability
* Documentation
* Explain commands

### Single-line comment:

```bash
# This is a single-line comment
```

### Inline comment:

```bash
command1  # This command does something
```

### Multi-line style comment:

```bash
# This is
# a multi-line
# comment
```

### Here Document:

```bash
<< satya
echo "Welcome to shellscript KK FUNDA"
echo "Today date is"
satya
```

---

## Comments in java/terraform/groovy

```
// single line
/*
 multi line
*/
```

---

## XML comments

```xml
<!-- comment -->
```
---

### Most Asked Interview Questions


#### Q. What is Shell Scripting?

```text
Shell scripting is the process of writing a sequence of Linux commands in a file and executing them as a program.
```

#### Q. What is the purpose of Shebang (#!)?

```text
The Shebang line specifies which interpreter should be used to execute the script.
```

#### Q. What is the extension of a shell script?

```text
.sh
```

#### Q. How do you debug a shell script?

```bash
sh -x script.sh
```

or

```bash
bash -x script.sh
```

#### Q. Is Shell Scripting platform independent?

```text
No.

Shell scripting is platform dependent and mainly works on Unix/Linux systems.

Python is platform independent.
```
