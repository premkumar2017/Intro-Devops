
---

## **50 Linux Commands (Basic to Advanced)**

---

### **1. File and Directory Management**
1. **`pwd`** - Print the current working directory.
   ```bash
   pwd
   ```
2. **`ls`** - List files and directories.
   ```bash
   ls -l  # Long listing
   ls -a  # Include hidden files
   ```
3. **`cd`** - Change directory.
   ```bash
   cd /path/to/directory
   cd ..  # Move up one directory
   ```
4. **`mkdir`** - Create a directory.
   ```bash
   mkdir myfolder
   mkdir -p dir1/dir2/dir3  # Create nested directories
   ```
5. **`rmdir`** - Remove an empty directory.
   ```bash
   rmdir myfolder
   ```
6. **`touch`** - Create an empty file or update timestamps.
   ```bash
   touch file.txt
   ```
7. **`cp`** - Copy files or directories.
   ```bash
   cp file.txt /path/to/destination
   cp -r dir1/ dir2/  # Copy directories recursively
   ```
8. **`mv`** - Move or rename files or directories.
   ```bash
   mv file.txt /path/to/destination
   mv oldname.txt newname.txt  # Rename a file
   ```
9. **`rm`** - Remove files or directories.
   ```bash
   rm file.txt
   rm -r dir/  # Remove directories recursively
   ```
10. **`find`** - Search for files or directories.
    ```bash
    find /path -name "file.txt"
    find /path -type f -mtime +7  # Find files modified more than 7 days ago
    ```

---

### **2. Text Processing**
11. **`cat`** - Display file content.
    ```bash
    cat file.txt
    ```
12. **`more`** - View file content page by page.
    ```bash
    more file.txt
    ```
13. **`less`** - View file content with backward navigation.
    ```bash
    less file.txt
    ```
14. **`head`** - Display the beginning of a file.
    ```bash
    head -n 10 file.txt  # Show first 10 lines
    ```
15. **`tail`** - Display the end of a file.
    ```bash
    tail -n 10 file.txt  # Show last 10 lines
    tail -f logfile.log  # Follow real-time updates
    ```
16. **`grep`** - Search text using patterns.
    ```bash
    grep "pattern" file.txt
    grep -i "pattern" file.txt  # Case-insensitive search
    ```
17. **`awk`** - Pattern scanning and processing.
    ```bash
    awk '{print $1}' file.txt  # Print the first column
    ```
18. **`sed`** - Stream editor for text manipulation.
    ```bash
    sed 's/old/new/' file.txt  # Replace text
    sed -i 's/old/new/' file.txt  # Edit file in place
    ```
19. **`cut`** - Extract sections from lines of files.
    ```bash
    cut -d',' -f1 file.csv  # Extract the first field from a CSV
    ```
20. **`sort`** - Sort lines of text files.
    ```bash
    sort file.txt
    sort -r file.txt  # Sort in reverse order
    ```

---

### **3. System Information**
21. **`uname`** - Display system information.
    ```bash
    uname -a  # Show all system information
    ```
22. **`df`** - Display disk space usage.
    ```bash
    df -h  # Human-readable format
    ```
23. **`du`** - Display directory space usage.
    ```bash
    du -sh /path/to/directory  # Summarize directory size
    ```
24. **`top`** - Display system processes.
    ```bash
    top
    ```
25. **`htop`** - Interactive process viewer (install with `sudo apt install htop`).
    ```bash
    htop
    ```
26. **`ps`** - Display running processes.
    ```bash
    ps aux
    ```
27. **`free`** - Display memory usage.
    ```bash
    free -h  # Human-readable format
    ```
28. **`uptime`** - Show system uptime.
    ```bash
    uptime
    ```
29. **`who`** - Display logged-in users.
    ```bash
    who
    ```
30. **`w`** - Show who is logged in and what they are doing.
    ```bash
    w
    ```

---

### **4. Networking**
31. **`ping`** - Test network connectivity.
    ```bash
    ping google.com
    ```
32. **`ifconfig`** - Display network interfaces (use `ip` on newer systems).
    ```bash
    ifconfig
    ```
33. **`netstat`** - Display network connections.
    ```bash
    netstat -tuln  # Show listening ports
    ```
34. **`ssh`** - Connect to a remote server.
    ```bash
    ssh user@remote_host
    ```
35. **`scp`** - Securely copy files between hosts.
    ```bash
    scp file.txt user@remote_host:/path/to/destination
    ```
36. **`wget`** - Download files from the web.
    ```bash
    wget https://example.com/file.zip
    ```
37. **`curl`** - Transfer data from or to a server.
    ```bash
    curl -O https://example.com/file.zip
    ```
38. **`nslookup`** - Query DNS records.
    ```bash
    nslookup google.com
    ```
39. **`dig`** - DNS lookup utility.
    ```bash
    dig google.com
    ```
40. **`traceroute`** - Trace the path packets take to a network host.
    ```bash
    traceroute google.com
    ```

---

### **5. User and Group Management**
41. **`useradd`** - Add a user.
    ```bash
    useradd username
    ```
42. **`usermod`** - Modify a user.
    ```bash
    usermod -aG groupname username  # Add user to a group
    ```
43. **`userdel`** - Delete a user.
    ```bash
    userdel username
    ```
44. **`groupadd`** - Add a group.
    ```bash
    groupadd groupname
    ```
45. **`groupmod`** - Modify a group.
    ```bash
    groupmod -n newgroupname oldgroupname
    ```
46. **`groupdel`** - Delete a group.
    ```bash
    groupdel groupname
    ```
47. **`passwd`** - Change user password.
    ```bash
    passwd username
    ```
48. **`su`** - Switch user.
    ```bash
    su username
    ```
49. **`sudo`** - Execute commands as a superuser.
    ```bash
    sudo command
    ```
50. **`id`** - Display user and group information.
    ```bash
    id username
    ```

---

### **6. Advanced Commands**
- **`tar`** - Archive files.
  ```bash
  tar -cvf archive.tar /path/to/files  # Create archive
  tar -xvf archive.tar  # Extract archive
  ```
- **`cron`** - Schedule tasks.
  ```bash
  crontab -e  # Edit cron jobs
  ```
- **`systemctl`** - Manage system services.
  ```bash
  systemctl start servicename
  systemctl enable servicename
  ```

---

