### File and Directory Management:
1. **List files and directories:**
   ```bash
   ls
   ```

2. **Change directory:**
   ```bash
   cd <directory-path>
   ```

3. **Create a directory:**
   ```bash
   mkdir <directory-name>
   ```

4. **Create a file:**
   ```bash
   touch <file-name>
   ```

5. **Remove a file:**
   ```bash
   rm <file-name>
   ```

6. **Remove a directory:**
   ```bash
   rmdir <directory-name>
   ```
   Or, to remove a directory and its contents:
   ```bash
   rm -r <directory-name>
   ```

7. **Copy a file or directory:**
   ```bash
   cp <source> <destination>
   ```

8. **Move or rename a file or directory:**
   ```bash
   mv <source> <destination>
   ```

9. **Display the contents of a file:**
   ```bash
   cat <file-name>
   ```

10. **View the contents of a file page by page:**
    ```bash
    less <file-name>
    ```

11. **Search for text in a file:**
    ```bash
    grep "<text-to-search>" <file-name>
    ```

### File Permissions:
1. **Change file permissions:**
   ```bash
   chmod <permissions> <file-name>
   ```
   Example:
   ```bash
   chmod 755 <file-name>
   ```

2. **Change file owner:**
   ```bash
   chown <user>:<group> <file-name>
   ```

3. **Change group of a file:**
   ```bash
   chgrp <group> <file-name>
   ```

### System Information:
1. **Display the current working directory:**
   ```bash
   pwd
   ```

2. **Display system information:**
   ```bash
   uname -a
   ```

3. **Display disk space usage:**
   ```bash
   df -h
   ```

4. **Display memory usage:**
   ```bash
   free -h
   ```

5. **Display running processes:**
   ```bash
   ps aux
   ```

6. **Monitor system processes:**
   ```bash
   top
   ```

7. **Search for a running process:**
   ```bash
   pgrep <process-name>
   ```

8. **Show all open ports and associated processes:**
   ```bash
   netstat -tuln
   ```

### Network Commands:
1. **Display IP address information:**
   ```bash
   ifconfig
   ```

2. **Check the status of a network connection:**
   ```bash
   ping <hostname-or-ip>
   ```

3. **Trace the route packets take to a network host:**
   ```bash
   traceroute <hostname-or-ip>
   ```

4. **Display active network connections:**
   ```bash
   ss -tuln
   ```

### Package Management (for Debian-based systems like Ubuntu):
1. **Install a package:**
   ```bash
   sudo apt-get install <package-name>
   ```

2. **Remove a package:**
   ```bash
   sudo apt-get remove <package-name>
   ```

3. **Update package list:**
   ```bash
   sudo apt-get update
   ```

4. **Upgrade installed packages:**
   ```bash
   sudo apt-get upgrade
   ```

### Process Management:
1. **Start a process in the background:**
   ```bash
   <command> &
   ```

2. **Stop a running process:**
   ```bash
   kill <process-id>
   ```

3. **Stop a running process by name:**
   ```bash
   pkill <process-name>
   ```

4. **Terminate a process by ID:**
   ```bash
   kill -9 <process-id>
   ```

### User Management:
1. **Add a new user:**
   ```bash
   sudo adduser <username>
   ```

2. **Delete a user:**
   ```bash
   sudo deluser <username>
   ```

3. **Change the user password:**
   ```bash
   sudo passwd <username>
   ```

4. **List all users:**
   ```bash
   cut -d: -f1 /etc/passwd
   ```

### Archive and Compression:
1. **Create a tar archive:**
   ```bash
   tar -cvf <archive-name>.tar <file-or-directory>
   ```

2. **Extract a tar archive:**
   ```bash
   tar -xvf <archive-name>.tar
   ```

3. **Create a gzipped tar archive:**
   ```bash
   tar -czvf <archive-name>.tar.gz <file-or-directory>
   ```

4. **Extract a gzipped tar archive:**
   ```bash
   tar -xzvf <archive-name>.tar.gz
   ```

### Searching and Finding Files:
1. **Find a file by name:**
   ```bash
   find / -name <file-name>
   ```

2. **Find a file by type (e.g., directories):**
   ```bash
   find / -type d -name <directory-name>
   ```

3. **Search for files containing a specific text:**
   ```bash
   grep -r "<text-to-search>" <directory>
   ```

### Miscellaneous:
1. **Redirect output to a file:**
   ```bash
   <command> > <file-name>
   ```

2. **Append output to a file:**
   ```bash
   <command> >> <file-name>
   ```

3. **Display the contents of a file with line numbers:**
   ```bash
   nl <file-name>
   ```
