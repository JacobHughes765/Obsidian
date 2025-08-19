### File and Directory Management

1. **`ls`**: List files and directories.
    
    - Example: `ls -l` (detailed list), `ls -a` (include hidden files)
2. **`cd`**: Change the current directory.
    
    - Example: `cd /path/to/directory`
3. **`pwd`**: Print the current working directory.
    
4. **`cp`**: Copy files and directories.
    
    - Example: `cp source.txt destination.txt`
5. **`mv`**: Move or rename files and directories.
    
    - Example: `mv oldname.txt newname.txt`
6. **`rm`**: Remove files or directories.
    
    - Example: `rm file.txt`, `rm -r directory` (recursive)
7. **`mkdir`**: Create a new directory.
    
    - Example: `mkdir new_directory`
8. **`rmdir`**: Remove an empty directory.
    
9. **`touch`**: Create an empty file or update the timestamp of an existing file.
    
    - Example: `touch newfile.txt`
10. **`find`**: Search for files in a directory hierarchy.
    
    - Example: `find /path -name "*.txt"`

### File Content Manipulation

11. **`cat`**: Concatenate and display file content.
    
    - Example: `cat file.txt`
12. **`less`**: View file content one screen at a time.
    
    - Example: `less file.txt`
13. **`head`**: Display the first few lines of a file.
    
    - Example: `head -n 10 file.txt`
14. **`tail`**: Display the last few lines of a file.
    
    - Example: `tail -n 10 file.txt`
15. **`grep`**: Search for a specific pattern in a file.
    
    - Example: `grep "search_term" file.txt`

### System Information

16. **`top`**: Display running processes and system resource usage.
    
17. **`htop`**: An improved version of `top` (may need to be installed).
    
18. **`df`**: Display disk space usage.
    
    - Example: `df -h` (human-readable format)
19. **`du`**: Estimate file and directory space usage.
    
    - Example: `du -sh /path/to/directory`
20. **`free`**: Display memory usage.
    
    - Example: `free -h` (human-readable format)

### User Management

21. **`whoami`**: Display the current logged-in user.
    
22. **`sudo`**: Execute a command with superuser privileges.
    
    - Example: `sudo apt update` (for Debian-based systems)
23. **`passwd`**: Change user password.
    

### Networking

24. **`ping`**: Check connectivity to a host.
    
    - Example: `ping google.com`
25. **`ifconfig`** or **`ip`**: Display network interface configuration.
    
    - Example: `ip addr show`
26. **`netstat`**: Display network connections, routing tables, etc. (use `ss` for a more modern alternative).
    
27. **`curl`**: Transfer data from or to a server using various protocols.
    
    - Example: `curl http://example.com`

### Package Management (Debian-based)

28. **`apt update`**: Update package lists.
    
29. **`apt upgrade`**: Upgrade installed packages.
    
30. **`apt install package_name`**: Install a new package.
    

### Miscellaneous

31. **`man`**: Display the manual for a command.
    
    - Example: `man ls`
32. **`history`**: Show command history.
    
33. **`clear`**: Clear the terminal screen.
    
34. **`echo`**: Display a line of text.
    
    - Example: `echo "Hello, World!"`
35. **`chmod`**: Change file permissions.
    
    - Example: `chmod +x script.sh` (make a script executable)