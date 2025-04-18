# Bash Scripting Basics: A Beginner's Guide

This document provides an introduction to foundational topics in Bash scripting. Each topic is explained with examples to help beginners understand and practice Bash scripting.



---

## **Bash Scripting in DevOps**  
**Why Bash is a DevOps Essential**  
Bash (Bourne Again Shell) remains a go-to scripting language for DevOps engineers due to its direct control over Unix/Linux systems, lightweight footprint, and seamless integration with system-level commands. Its simplicity and ubiquity make it perfect for automating routine tasks, scripting deployment pipelines, and managing infrastructure.

---

### **Four Pillars of Any Scripting Language (Bash Edition):**
- **Keywords** – `if`, `then`, `else`, `while`, `for`, `function`, etc.  
- **Data Types** – Strings, Integers (via command line interpretation), Arrays  
- **Operators** – Arithmetic (`+`, `-`, `*`, `/`), Logical (`&&`, `||`), Comparison (`-eq`, `-ne`, `-lt`, `-gt`)  
- **Logic & Reasoning** – Loops, conditional branching, and shell decision-making

---

### **Key Advantages of Bash in DevOps**

- **System-Level Control:** Bash directly interacts with Unix/Linux OS, allowing deep automation of system processes.  
- **Lightweight and Fast:** No interpreter or dependencies required—Bash is available by default on most servers.  
- **Ideal for Quick Scripts:** Perfect for short tasks, such as backups, service checks, and deployment triggers.  
- **Easily Integrates with Other Tools:** Can be used within CI/CD tools (Jenkins, GitHub Actions) and combined with Python, Ansible, etc.  
- **Scripting Standards in Linux Servers:** Bash is the default go-to for scripting in most Linux environments.

---

### **Core Use Cases of Bash in DevOps**

- **CI/CD Pipeline Scripting**  
  Automate build, test, and deploy phases directly in tools like Jenkins or GitLab using Bash.

- **Server Provisioning and Configuration**  
  Automate the installation of software, updates, and configuration setups on virtual machines or containers.

- **Log Monitoring and System Health Checks**  
  Create custom scripts to parse logs, check disk usage, CPU load, memory consumption, etc.

- **Backup and Restore Automation**  
  Bash is widely used for creating scheduled backup jobs and disaster recovery tasks.

- **User and Permission Management**  
  Automate tasks like user creation, permission updates, and SSH configuration.

- **Scripted Alerts and Notifications**  
  Use Bash to monitor services and send alerts (email, Slack, SMS) when something fails.

- **Docker and Kubernetes Commands**  
  Wrap `docker` and `kubectl` commands in Bash scripts to automate image builds, deployments, and health checks.


---

## 1. Variables: Assigning and Accessing Variables

Variables in Bash are used to store data. You can assign a value to a variable and access it later in your script.

### Example:
```bash
#!/bin/bash

# Assigning a value to a variable
name="John Doe"

# Accessing the variable
echo "Hello, $name!"
```

**Output:**
```
Hello, John Doe!
```

---

## 2. Input and Output: Using `read` and `echo`

- `read`: Used to take input from the user.
- `echo`: Used to display output.

### Example:
```bash
#!/bin/bash

# Taking input from the user
echo "What is your name?"
read name

# Displaying output
echo "Nice to meet you, $name!"
```

**Output:**
```
What is your name?
[User enters: Alice]
Nice to meet you, Alice!
```

---

## 3. Conditionals: `if`, `else`, `elif`, and File Testing

Conditionals allow you to make decisions in your script based on certain conditions.

### Example:
```bash
#!/bin/bash

# Checking if a number is positive, negative, or zero
echo "Enter a number:"
read num

if [ $num -gt 0 ]; then
    echo "$num is positive."
elif [ $num -lt 0 ]; then
    echo "$num is negative."
else
    echo "$num is zero."
fi
```

**Output:**
```
Enter a number:
[User enters: 5]
5 is positive.
```

### File Testing:
You can also check if a file exists or has certain permissions.

```bash
#!/bin/bash

# Checking if a file exists
file="example.txt"

if [ -f "$file" ]; then
    echo "$file exists."
else
    echo "$file does not exist."
fi
```

**Output:**
```
example.txt exists.
```

---

## 4. Loops: `for`, `while`, `until`

Loops allow you to repeat a set of commands multiple times.

### `for` Loop Example:
```bash
#!/bin/bash

# Looping through a list of items
for fruit in apple banana cherry; do
    echo "I like $fruit"
done
```

**Output:**
```
I like apple
I like banana
I like cherry
```

### `while` Loop Example:
```bash
#!/bin/bash

# Looping while a condition is true
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    count=$((count + 1))
done
```

**Output:**
```
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

### `until` Loop Example:
```bash
#!/bin/bash

# Looping until a condition is true
count=1
until [ $count -gt 5 ]; do
    echo "Count: $count"
    count=$((count + 1))
done
```

**Output:**
```
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

---

## 5. Exit Status (`$?`): Checking the Success or Failure of Commands

The exit status of a command is stored in the `$?` variable. A value of `0` indicates success, while a non-zero value indicates failure.

### Example:
```bash
#!/bin/bash

# Running a command and checking its exit status
ls /nonexistent_directory

if [ $? -eq 0 ]; then
    echo "Command succeeded."
else
    echo "Command failed."
fi
```

**Output:**
```
ls: cannot access '/nonexistent_directory': No such file or directory
Command failed.
```

---

## 6. Simple Functions: Writing and Calling Functions

Functions allow you to group commands together and reuse them.

### Example:
```bash
#!/bin/bash

# Defining a function
greet() {
    echo "Hello, $1!"
}

# Calling the function
greet "Alice"
greet "Bob"
```

**Output:**
```
Hello, Alice!
Hello, Bob!
```

---

## 7. Comments: Single-line (`#`) Comments

Comments are used to add notes or explanations to your script. They are ignored by the Bash interpreter.

### Example:
```bash
#!/bin/bash

# This is a single-line comment
echo "This is a Bash script."

# You can also add comments after a command
echo "Hello, World!"  # This prints a greeting
```

**Output:**
```
This is a Bash script.
Hello, World!
```

---

These topics are excellent for leveling up your scripting and programming skills, especially in shell scripting (e.g., Bash). Below is a breakdown of each topic with key concepts and examples to help you deepen your understanding:

---

### **1. Arrays: Defining, Accessing, and Iterating Over Arrays**
- **Defining Arrays**:  
  ```bash
  fruits=("Apple" "Banana" "Cherry")
  ```
- **Accessing Elements**:  
  ```bash
  echo ${fruits[0]}  # Output: Apple
  echo ${fruits[@]}  # Output: All elements
  echo ${#fruits[@]} # Output: Number of elements
  ```
- **Iterating Over Arrays**:  
  ```bash
  for fruit in "${fruits[@]}"; do
      echo $fruit
  done
  ```

---

### **2. String Manipulation: Substring Extraction, Replacement, and Length**
- **Substring Extraction**:  
  ```bash
  str="Hello World"
  echo ${str:6:5}  # Output: World (start at index 6, length 5)
  ```
- **Replacement**:  
  ```bash
  echo ${str/World/Universe}  # Output: Hello Universe
  ```
- **Length**:  
  ```bash
  echo ${#str}  # Output: 11
  ```

---

### **3. Arithmetic Operations: Using `expr` and `$(( ))`**
- **Using `expr`**:  
  ```bash
  result=$(expr 5 + 3)  # Output: 8
  ```
- **Using `$(( ))`**:  
  ```bash
  result=$((5 * 3))  # Output: 15
  ```
- **Combining Operations**:  
  ```bash
  echo $(( (5 + 3) * 2 ))  # Output: 16
  ```

---

### **4. Logical Operators: `&&`, `||`, and `!`**
- **`&&` (AND)**:  
  ```bash
  [ -f file.txt ] && echo "File exists"
  ```
- **`||` (OR)**:  
  ```bash
  [ -f file.txt ] || echo "File does not exist"
  ```
- **`!` (NOT)**:  
  ```bash
  if ! [ -d dir ]; then
      echo "Directory does not exist"
  fi
  ```

---

### **5. File Handling: Creating, Reading, Writing, and Appending Files**
- **Creating a File**:  
  ```bash
  touch newfile.txt
  ```
- **Reading a File**:  
  ```bash
  cat file.txt
  ```
- **Writing to a File**:  
  ```bash
  echo "Hello" > file.txt  # Overwrites
  ```
- **Appending to a File**:  
  ```bash
  echo "World" >> file.txt  # Appends
  ```

---

### **6. Loops with Conditions: Nested Loops and Conditional Break/Continue**
- **Nested Loops**:  
  ```bash
  for i in {1..3}; do
      for j in {1..2}; do
          echo "i=$i, j=$j"
      done
  done
  ```
- **Break**:  
  ```bash
  for i in {1..10}; do
      if [ $i -eq 5 ]; then
          break
      fi
      echo $i
  done
  ```
- **Continue**:  
  ```bash
  for i in {1..5}; do
      if [ $i -eq 3 ]; then
          continue
      fi
      echo $i
  done
  ```

---

### **7. Basic Debugging: Using `set -x` and `set +x`**
- **Enable Debugging**:  
  ```bash
  set -x  # Prints each command before execution
  ```
- **Disable Debugging**:  
  ```bash
  set +x  # Stops printing commands
  ```
- **Example**:  
  ```bash
  set -x
  echo "Debugging started"
  var=10
  echo $var
  set +x
  ```

---

### **8. Scheduling with Cron: Automating Script Execution**
- **Cron Syntax**:  
  ```
  * * * * * command_to_execute
  | | | | |
  | | | | +-- Day of the Week (0 - 6) (Sunday=0)
  | | | +---- Month (1 - 12)
  | | +------ Day of the Month (1 - 31)
  | +-------- Hour (0 - 23)
  +---------- Minute (0 - 59)
  ```
- **Example**:  
  ```bash
  # Run a script every day at 5 AM
  0 5 * * * /path/to/script.sh
  ```
- **Edit Crontab**:  
  ```bash
  crontab -e
  ```

---

### **9. Environment Variables: Accessing and Setting Variables Like `$PATH`**
- **Accessing Variables**:  
  ```bash
  echo $PATH
  ```
- **Setting Variables**:  
  ```bash
  export MY_VAR="Hello"
  echo $MY_VAR
  ```
- **Adding to `$PATH`**:  
  ```bash
  export PATH=$PATH:/new/directory
  ```

---

These advanced topics are perfect for mastering Bash scripting and taking your skills to the next level. Below is a detailed breakdown of each topic, along with examples and key concepts:

---

### **1. Regular Expressions: Pattern Matching Using `grep`, `awk`, and `sed`**
- **`grep`**:  
  ```bash
  grep "pattern" file.txt  # Basic search
  grep -E "regex_pattern" file.txt  # Extended regex
  grep -o "pattern" file.txt  # Only matching part
  ```
- **`awk`**:  
  ```bash
  awk '/pattern/ {print $1}' file.txt  # Print first column of matching lines
  awk -F: '{print $1}' /etc/passwd  # Split by delimiter (e.g., colon)
  ```
- **`sed`**:  
  ```bash
  sed 's/foo/bar/' file.txt  # Replace first occurrence
  sed 's/foo/bar/g' file.txt  # Replace all occurrences
  sed '/pattern/d' file.txt  # Delete matching lines
  ```

---

### **2. Advanced File Operations: Parsing and Manipulating Large Files**
- **Reading Large Files**:  
  ```bash
  while IFS= read -r line; do
      echo "$line"
  done < largefile.txt
  ```
- **Splitting Files**:  
  ```bash
  split -l 1000 largefile.txt part_  # Split into 1000-line chunks
  ```
- **Merging Files**:  
  ```bash
  cat file1.txt file2.txt > merged.txt
  ```

---

### **3. Error Handling: Using `trap` to Manage Script Errors**
- **Basic `trap`**:  
  ```bash
  trap "echo 'Error occurred'; exit 1" ERR
  ```
- **Cleanup on Exit**:  
  ```bash
  trap "rm -f tempfile.txt" EXIT
  ```
- **Ignoring Signals**:  
  ```bash
  trap "" SIGINT  # Ignore Ctrl+C
  ```

---

### **4. Process Management: Running Background Processes, Using `&`, `jobs`, and `kill`**
- **Background Processes**:  
  ```bash
  sleep 10 &
  ```
- **Listing Jobs**:  
  ```bash
  jobs
  ```
- **Killing Processes**:  
  ```bash
  kill %1  # Kill job 1
  kill 1234  # Kill process with PID 1234
  ```

---

### **5. Script Arguments: Handling `$1`, `$2`, `$@`, `$*`, and `$#`**
- **Accessing Arguments**:  
  ```bash
  echo "First argument: $1"
  echo "All arguments: $@"
  echo "Number of arguments: $#"
  ```
- **Iterating Over Arguments**:  
  ```bash
  for arg in "$@"; do
      echo "$arg"
  done
  ```
- **Shifting Arguments**:  
  ```bash
  shift  # Shift arguments to the left
  echo "New first argument: $1"
  ```
  The `shift` command in a shell script is used to **shift the positional parameters** (`$1`, `$2`, `$3`, etc.) to the left. That means `$2` becomes `$1`, `$3` becomes `$2`, and so on. This is useful when you're processing arguments in a loop.

---

### 🔹 Syntax:
```bash
shift [n]
```
- `n` is the number of positions to shift. If not specified, the default is `1`.

---

### 🔸 Simple Example:
```bash
#!/bin/bash

echo "All arguments: $@"

while [[ $# -gt 0 ]]
do
  echo "Processing argument: $1"
  shift
done
```

### 🔸 Usage Example:
Run this script like:
```bash
./script.sh apple banana cherry
```

**Output:**
```
All arguments: apple banana cherry
Processing argument: apple
Processing argument: banana
Processing argument: cherry
```

Each time `shift` is called, the script moves to the next argument by shifting them to the left.

---

### 🔹 Example with `shift 2`:
```bash
#!/bin/bash

echo "Before shift: $1 $2 $3"

shift 2

echo "After shift: $1 $2"
```

Run it with:
```bash
./script.sh one two three four
```

**Output:**
```
Before shift: one two three
After shift: three four
```

Let me know if you want a version that includes flags (like `-f`, `-d`, etc.) with shift logic too.

---

### **6. Custom Libraries: Creating Reusable Functions**
- **Defining Functions**:  
  ```bash
  my_function() {
      echo "Hello, $1"
  }
  ```
- **Sourcing Libraries**:  
  ```bash
  source mylib.sh  # Load functions from mylib.sh
  ```
- **Example Library**:  
  ```bash
  # mylib.sh
  greet() {
      echo "Hello, $1"
  }
  ```

---

### **7. Networking Commands: Using `curl`, `wget`, and Network Utilities**
- **`curl`**:  
  ```bash
  curl -o file.txt https://example.com/file.txt  # Download file
  curl -X POST -d "param=value" https://example.com/api  # POST request
  ```
- **`wget`**:  
  ```bash
  wget https://example.com/file.txt  # Download file
  ```
- **Network Diagnostics**:  
  ```bash
  ping example.com
  netstat -tuln  # List open ports
  ```

---

### **8. Parallel Execution: Running Commands in Parallel for Performance**
- **Using `&`**:  
  ```bash
  command1 &
  command2 &
  wait  # Wait for all background jobs to finish
  ```
- **Using `xargs`**:  
  ```bash
  echo -e "1\n2\n3" | xargs -n 1 -P 3 sleep  # Run 3 sleep commands in parallel
  ```


---

### **9. Advanced Debugging: Using `bash -x script.sh` and Logging**
- **Debugging with `bash -x`**:  
  ```bash
  bash -x script.sh  # Print each command before execution
  ```
- **Logging**:  
  ```bash
  exec > >(tee -a script.log) 2>&1  # Log all output to a file
  ```
- **Debugging Specific Sections**:  
  ```bash
  set -x
  # Debug code here
  set +x
  ```

---

### **10. Interaction with Other Programs: Integrating with Python, Perl, or System APIs**
- **Calling Python**:  
  ```bash
  python3 -c "print('Hello from Python')"
  ```
- **Calling Perl**:  
  ```bash
  perl -e 'print "Hello from Perl\n"'
  ```
- **Using System APIs**:  
  ```bash
  curl -X GET "https://api.example.com/data"  # Interact with REST APIs
  ```

---


Example Scripts

https://github.com/ruanyf/simple-bash-scripts?tab=readme-ov-file
