# Bash Scripting Basics: A Beginner's Guide

This document provides an introduction to foundational topics in Bash scripting. Each topic is explained with examples to help beginners understand and practice Bash scripting.

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

