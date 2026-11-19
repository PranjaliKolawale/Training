# Training

-h(human readable): Displays file sizes in easy-to-read format.<br>
-a(All): Displays all file files, including hidden files.

## Linux Commands 
### A.Basic Linux Commands & File and Directory Management
1. cd - Used to change or navigate between directories.
2. ls - Lists files and directories in the current directory.
3. mkdir - Creates new directory.
4. rmdir - Removes an empty directory.
5. touch - Creates a new empty file or updates its timestamps.
6. rm - Removes files or directories.
7. cp - Copy filesor directories.
8. mv - Move or rename files.
9. ln - Create links. *
10. tree - Show directory structure.
11. pwd - Displays the current working directory path.

### B. File Reading & Editing Commands
11. cat - Display the file content.
12. nano - Write and Edit the file.
13. vim - Write and Edit the file.
14. head - Displays beginning of a file(10 lines).
15. tail - Displays end of a file(10 lines).
16. less - Read files interactively.
17. more - Read files page by page.
18. echo - Displays text or variables in the terminal.
19. clear - Clear the terminal screen.
20. exit - Close the terminal session.

### C. Searching and Locating
21. find - Searches for files and directories.
22. locate - Quickly searches for files by name.
23. grep - Search for text patterns.

### D. Text Processing *
24. sed - Replace or modify text patterns.
25. awk - Process and analyze text.
26. sort - Sort file content.
27. cut - Extract sections of text.
28. diff - Compares two files.
29. tee - Output to terminal and file.

### E. Compression and Extraction
30. zip - Compress files into ZIP archives. (zip archive_name.zip file_name)
31. unzip - Extract ZIP archives. (unzip filename.zip)
32. tar - Create and extract archives. (tar -cvf name.tar file_name - Creating| tar -xvf filename.tar - Extracting)

### F. Permission and Ownership
33. sudo -	Run command as administrator.
34. chmod - Change file permissions.
35. chown - Change file ownership.

### G. User Management
36. su - Switch user account.
37. whoami - Show current user.
38. useradd - Creates new user.
39. userdel - Delete user account.
40. passwd - Set or change password.

### H. System Information and Disk management
41. df - Show disk space usage.
42. du - Show file and directory disk usage.
43. uname - Show kernel information.
44. hostname - Show or set hostname.
45. shutdown - Shut down or restart system.

### I. Networking and file transfer.
46. ping - Test network connectivity
47. wget - Download files from the web.
48. curl - transfer data via URL.
49. scp - Copy files over SSH.(scp source destination)
50. rsync - Synchronize files between locations. (rsync -av source destination)
51. ip - Manage network settings.
52. netstat - Show network connections.
53. traceroute - Trace network packet path. (traceroute hostname/IP)
54. nslookup - Query DNS records. (nslookup hostname/IP)
55. dig - Detailed DNS lookup. (dig [options] domain [record_type]) (example: dig google.com MX)

### J. Package management
56. apt - Manage packages on ubuntu and debian.
57. dnf - Manage packages on Fedora and RHEL-based distributions.

### K. General terminal utilities
58. history - Show command history.
59. man - Show command manual.
60. alias - Create command shortcut. (alias alias_name='command')
61. unalias - Remove command shortcut. (unalias alias_name)
62. cal - Display calender.

