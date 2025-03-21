Here’s a **simple and practical task list** for students based on the **50 Linux commands** provided. These tasks are designed to help students practice and reinforce their understanding of the commands.

---

## **Linux Command Tasks for Students**

---

### **1. File and Directory Management**
1. **`pwd`**: Print your current working directory.
2. **`ls`**: List all files and directories in your home folder.
3. **`cd`**: Navigate to the `/var/log` directory and then return to your home directory.
4. **`mkdir`**: Create a directory named `practice` in your home folder.
5. **`touch`**: Inside the `practice` directory, create a file named `test.txt`.
6. **`cp`**: Copy `test.txt` to a new file named `test_backup.txt`.
7. **`mv`**: Rename `test_backup.txt` to `renamed.txt`.
8. **`rm`**: Delete the file `renamed.txt`.
9. **`find`**: Search for all `.txt` files in your home directory.

---

### **2. Text Processing**
10. **`cat`**: Display the contents of `/etc/passwd`.
11. **`more`**: View the contents of `/etc/passwd` page by page.
12. **`less`**: Open `/etc/passwd` with `less` and practice scrolling.
13. **`head`**: Display the first 5 lines of `/etc/passwd`.
14. **`tail`**: Display the last 5 lines of `/etc/passwd`.
15. **`grep`**: Search for your username in `/etc/passwd`.
16. **`awk`**: Print the first column of `/etc/passwd`.
17. **`sed`**: Replace the word `root` with `admin` in a text file.
18. **`cut`**: Extract the first field (username) from `/etc/passwd`.
19. **`sort`**: Sort the contents of `/etc/passwd` alphabetically.

---

### **3. System Information**
20. **`uname`**: Display your system's kernel name and version.
21. **`df`**: Check the disk space usage of your system in a human-readable format.
22. **`du`**: Find the size of the `/var/log` directory.
23. **`top`**: Open the `top` command and observe the running processes.
24. **`ps`**: List all running processes on your system.
25. **`free`**: Check the memory usage of your system.
26. **`uptime`**: Find out how long your system has been running.
27. **`who`**: Display the list of users currently logged in.
28. **`w`**: Check what the logged-in users are doing.

---

### **4. Networking**
29. **`ping`**: Ping `google.com` to check your internet connectivity.
30. **`ifconfig`** or **`ip`**: Display your system's IP address.
31. **`netstat`**: List all listening ports on your system.
32. **`ssh`**: Connect to a remote server (if available) or try connecting to `localhost`.
33. **`scp`**: Copy a file from your local machine to a remote server (or vice versa).
34. **`wget`**: Download a file from the internet (e.g., `wget https://example.com/file.zip`).
35. **`curl`**: Fetch the HTML content of a website (e.g., `curl https://example.com`).
36. **`nslookup`**: Find the IP address of `google.com`.
37. **`dig`**: Query the DNS records of `google.com`.
38. **`traceroute`**: Trace the route to `google.com`.

---

### **5. User and Group Management**
39. **`useradd`**: Create a new user named `testuser`.
40. **`usermod`**: Add `testuser` to the `sudo` group.
41. **`userdel`**: Delete the `testuser` account.
42. **`groupadd`**: Create a new group named `testgroup`.
43. **`groupmod`**: Rename `testgroup` to `newgroup`.
44. **`groupdel`**: Delete the `newgroup`.
45. **`passwd`**: Change the password for your current user.
46. **`su`**: Switch to the `root` user (if permitted).
47. **`sudo`**: Run a command with superuser privileges (e.g., `sudo ls /root`).
48. **`id`**: Display your user and group information.

---

### **6. Advanced Tasks**
49. **`tar`**: Create a compressed archive of the `practice` directory.
   ```bash
   tar -cvzf practice.tar.gz practice/
   ```
50. **`cron`**: Schedule a task to run a script every day at 8 AM.
   ```bash
   crontab -e
   # Add: 0 8 * * * /path/to/script.sh
   ```
51. **`systemctl`**: Check the status of the `sshd` service.
   ```bash
   systemctl status sshd
   ```

---

### **Bonus Tasks**
- Create a script that automates the following:
  1. Creates a directory.
  2. Creates a file inside the directory.
  3. Adds some text to the file.
  4. Displays the file content.
  5. Deletes the directory and its contents.

- Use `awk` and `grep` together to extract specific information from a log file (e.g., `/var/log/syslog`).

---

These tasks are designed to be simple and practical, allowing students to gain hands-on experience with Linux commands. Let me know if you need further clarification or additional tasks!
