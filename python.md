# Python in DevOps

Highlight why Python has become a go-to scripting language for DevOps
engineers. Its simplicity, flexibility, and vast ecosystem of libraries make it ideal for
DevOps automation and integrations

## Four Pillers of Any Programming Language:
- Keywords
- Data Types
- Operators
- Logic Reasoning Skills
  
## Key Advantages of Python in DevOps

- Ease of Use:
    Python’s readable syntax and ease of learning make it accessible for both
    beginner and experienced DevOps engineers
- Cross-Platform Compatibility:
    Python scripts run on multiple operating systems, including Linux,
    Windows, and macOS, ensuring consistency across environments.
- Rich Library Ecosystem:
    Python has extensive libraries for interacting with APIs, automating
    infrastructure, and working with data, making it suitable for various DevOps use cases.
- Community and Support:
    Python’s strong community support ensures fast problem-solving and
    access to many resources and tools.

## Core Use Cases of Python in DevOps
1. Automation of CI/CD Pipelines -
    Automating deployment, testing, and version control using tools like
    Jenkins, GitLab CI, or CircleCI with Python scripts.
2. Infrastructure as Code (IaC) -
    Provisioning and managing cloud resources and infrastructure using
    Python with tools like Terraform and AWS Boto3 SDK.
3. Configuration Management -
    Managing configurations across different environments using Python to
    ensure uniformity in deployment pipelines.
4. System Monitoring & Alerts -
    Creating monitoring scripts for logging, alerting, and integrating with
    platforms like Nagios, Prometheus, or Grafana.
5. Log Management and Analysis - 
    Parsing and analyzing logs with Python for real-time monitoring and error
    tracking.
6. API Integration - 
    Utilizing Python for interacting with external services via REST APIs, like
    integrating with cloud providers (AWS, Azure) or monitoring services (DataDog,
    Splunk).
7. Cloud Automation - 
    Using Python scripts to automate tasks in AWS, Google Cloud, and Azure
    like resource provisioning, scaling, and managing deployments.
8. Container Management and Orchestration: - 
    Automating the management of Docker containers and Kubernetes
    clusters through Python scripts and API integrations.
---

## 🔧 **Tools and Libraries for Python in DevOps**

Python offers powerful libraries that make DevOps automation efficient, scalable, and cloud-ready. Below are some essential tools—with real-world usage examples:

---

### 🟡 **Boto3** – AWS Automation with Python  
**Use Case:** Provisioning an EC2 instance on AWS  
```python
import boto3

ec2 = boto3.resource('ec2')
instance = ec2.create_instances(
    ImageId='ami-0abcdef1234567890',
    MinCount=1,
    MaxCount=1,
    InstanceType='t2.micro'
)
print("EC2 Instance Created:", instance[0].id)
```

---

### 🔵 **Ansible (Python-Based)** – Configuration Management & Automation  
**Use Case:** Triggering a playbook using Python’s subprocess module  
```python
import subprocess

subprocess.run(["ansible-playbook", "deploy_app.yml"])
```

> Note: Ansible is written in Python and can be extended using Python modules or executed via scripts.

---

### 🟢 **Requests** – API Automation  
**Use Case:** Check application health from a monitoring endpoint  
```python
import requests

response = requests.get("http://myapp.com/health")
if response.status_code == 200:
    print("App is Healthy")
else:
    print("App check failed:", response.status_code)
```

---

### 🔴 **Kubernetes Python Client** – Manage Kubernetes Resources  
**Use Case:** List all pods in a Kubernetes namespace  
```python
from kubernetes import client, config

config.load_kube_config()
v1 = client.CoreV1Api()
pods = v1.list_namespaced_pod(namespace="default")

for pod in pods.items:
    print(pod.metadata.name)
```

Here's a clean and simple sample Python script to demonstrate basic functionality:

---

### 📝 **Sample Python Script**

#### ✅ **Filename:** `test.py`

```python
# test.py
print("Hello, World!")
```

#### ▶️ **To run the script:**

```bash
python test.py
```

#### 🖨️ **Output:**

```
Hello, World!
```

# **Python Data Types**  

Python is a **dynamically typed** language, meaning you don’t need to declare data types explicitly.  

### **Basic Data Types in Python:**  

1. **Numeric Types**  
   - `int` – Whole numbers (e.g., `10`, `-5`)  
   - `float` – Decimal numbers (e.g., `10.5`, `-3.14`)  
   - `complex` – Complex numbers (e.g., `2 + 3j`)  

2. **Sequence Types**  
   - `str` – Text (e.g., `"Hello"`, `'Python'`)  
   - `list` – Ordered, mutable collection (e.g., `[1, "apple", True]`)  
   - `tuple` – Ordered, immutable collection (e.g., `(10, "banana")`)  

3. **Mapping Type**  
   - `dict` – Key-value pairs (e.g., `{"name": "John", "age": 30}`)  

4. **Set Types**  
   - `set` – Unordered, unique elements (e.g., `{1, 2, 3}`)  
   - `frozenset` – Immutable set (e.g., `frozenset({1, 2, 3})`)  

5. **Boolean Type**  
   - `bool` – `True` or `False`  

6. **Binary Types**  
   - `bytes` – Immutable binary data (e.g., `b"hello"`)  
   - `bytearray` – Mutable binary data (e.g., `bytearray(5)`)  

7. **None Type**  
   - `None` – Represents no value (e.g., `x = None`)  

---

### **1. Numeric Types**  
```python
# Integer (int)  
age = 25  
print(age, type(age))  # Output: 25 <class 'int'>  

# Float  
price = 19.99  
print(price, type(price))  # Output: 19.99 <class 'float'>  

# Complex  
z = 3 + 4j  
print(z, type(z))  # Output: (3+4j) <class 'complex'>  
```

---

### **2. Sequence Types**  
```python
# String (str)  
name = "Alice"  
print(name, type(name))  # Output: Alice <class 'str'>  

# List (mutable, ordered)  
fruits = ["apple", "banana", "cherry"]  
print(fruits, type(fruits))  # Output: ['apple', 'banana', 'cherry'] <class 'list'>  

# Tuple (immutable, ordered)  
coordinates = (10, 20)  
print(coordinates, type(coordinates))  # Output: (10, 20) <class 'tuple'>  
```

---

### **3. Dictionary (Mapping Type)**  
```python
# Dictionary (dict) – Key-value pairs  
person = {"name": "Bob", "age": 30}  
print(person, type(person))  # Output: {'name': 'Bob', 'age': 30} <class 'dict'>  
```

---

### **4. Set Types**  
```python
# Set (unordered, unique)  
unique_numbers = {1, 2, 2, 3}  
print(unique_numbers, type(unique_numbers))  # Output: {1, 2, 3} <class 'set'>  

# FrozenSet (immutable set)  
frozen_set = frozenset({1, 2, 3})  
print(frozen_set, type(frozen_set))  # Output: frozenset({1, 2, 3}) <class 'frozenset'>  
```

---

### **5. Boolean Type**  
```python
# Boolean (bool) – True or False  
is_active = True  
print(is_active, type(is_active))  # Output: True <class 'bool'>  
```

---

### **6. Binary Types**  
```python
# Bytes (immutable binary)  
byte_data = b"hello"  
print(byte_data, type(byte_data))  # Output: b'hello' <class 'bytes'>  

# ByteArray (mutable binary)  
byte_array = bytearray(5)  
print(byte_array, type(byte_array))  # Output: bytearray(b'\x00\x00\x00\x00\x00') <class 'bytearray'>  
```

---

### **7. None Type**  
```python
# None (no value)  
result = None  
print(result, type(result))  # Output: None <class 'NoneType'>  
```

---

### **Summary Table**  
| **Data Type**  | **Example** | **Mutable?** |
|--------------|------------|------------|
| `int` | `x = 10` | ❌ |
| `float` | `y = 3.14` | ❌ |
| `str` | `name = "Python"` | ❌ |
| `list` | `nums = [1, 2, 3]` | ✔️ |
| `tuple` | `point = (4, 5)` | ❌ |
| `dict` | `user = {"name": "Alice"}` | ✔️ |
| `set` | `unique = {1, 2, 3}` | ✔️ |
| `bool` | `flag = True` | ❌ |
| `bytes` | `data = b"abc"` | ❌ |
| `None` | `val = None` | ❌ |

These examples cover the most common Python data types with simple usage. 🚀

# **Understanding Python Keywords**

Let me explain Python keywords in a simpler way with clear examples.

## **What are Keywords?**
Keywords are special reserved words in Python that have specific meanings. You **cannot** use them as variable names or function names because Python uses them for its own operations.

### **Example of Invalid Usage**
```python
# This will give an error because 'if' is a keyword
if = 10  # ❌ Wrong!
```

---

## **Categories of Keywords with Simple Examples**

### 1️⃣ **True/False/None Keywords**
```python
# Boolean values
is_active = True  # ✅ Correct
is_blocked = False  # ✅ Correct

# None represents "no value"
result = None  # ✅ Correct
```

### 2️⃣ **Loop Keywords (`for`, `while`, `break`, `continue`)**
```python
# for loop
for i in [1, 2, 3]:
    print(i)  # Prints 1, 2, 3

# while loop
count = 0
while count < 3:
    print(count)
    count += 1  # Prints 0, 1, 2

# break exits the loop
for num in range(5):
    if num == 3:
        break  # Stops at 3
    print(num)  # Prints 0, 1, 2

# continue skips current iteration
for num in range(5):
    if num == 2:
        continue  # Skips 2
    print(num)  # Prints 0, 1, 3, 4
```

### 3️⃣ **Conditional Keywords (`if`, `elif`, `else`)**
```python
age = 18

if age < 13:
    print("Child")
elif age < 18:
    print("Teen")
else:
    print("Adult")  # Prints "Adult"
```

### 4️⃣ **Function Keywords (`def`, `return`, `lambda`)**
```python
# def creates a function
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))  # Prints "Hello, Alice!"

# lambda makes small anonymous functions
square = lambda x: x * x
print(square(5))  # Prints 25
```

### 5️⃣ **Class Keywords (`class`)**
```python
class Dog:
    def bark(self):
        print("Woof!")

my_dog = Dog()
my_dog.bark()  # Prints "Woof!"
```

### 6️⃣ **Exception Handling (`try`, `except`, `finally`, `raise`)**
```python
# try-except handles errors
try:
    print(10 / 0)
except ZeroDivisionError:
    print("Can't divide by zero!")  # Prints this

# finally always runs
try:
    file = open("test.txt")
except:
    print("Error occurred")
finally:
    print("This always runs")

# raise creates custom errors
if age < 0:
    raise ValueError("Age can't be negative!")
```

### 7️⃣ **Variable Scope (`global`, `nonlocal`)**
```python
x = 10  # Global variable

def change_x():
    global x  # Allows modifying global x
    x = 20

change_x()
print(x)  # Now prints 20
```

### 8️⃣ **Import Keywords (`import`, `from`, `as`)**
```python
import math  # Imports entire math module
print(math.sqrt(16))  # Prints 4.0

from datetime import datetime as dt  # Imports with alias
print(dt.now())  # Prints current time
```

### 9️⃣ **Other Important Keywords**
```python
# in checks membership
if "a" in "apple":
    print("Found 'a'")  # Prints this

# is checks identity (same object)
x = [1, 2]
y = [1, 2]
print(x == y)  # True (same values)
print(x is y)  # False (different objects)

# del deletes variables
nums = [1, 2, 3]
del nums[1]  # Removes 2
print(nums)  # [1, 3]
```

---

## **How to See All Keywords?**
```python
import keyword
print(keyword.kwlist)
```
This prints all Python keywords like `['False', 'None', 'True', 'and', 'as', ...]`

---

## **Key Points to Remember**
1. Keywords are **reserved** - you can't use them as variable names
2. Each keyword has a **specific purpose** in Python
3. They help control program flow (`if`, `for`), define functions (`def`), handle errors (`try`), etc.




