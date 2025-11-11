# 📘 Windows CMD Essential Study Guide

This guide summarizes key Windows Command Line (CMD) utilities essential for system administration, network troubleshooting, and basic security reconnaissance.

---

## 1. System & Reconnaissance Commands

These commands are crucial for initial system analysis and finding vulnerabilities.

| Command | Key Switches/Flags | Function (Simple) | Security Relevance |
| :--- | :--- | :--- | :--- |
| **`systeminfo`** | (None) | Lists system details, hardware, and OS information. | Essential for **vulnerability assessment** by checking the exact OS version and patch level. |
| **`ver`** | (None) | Displays the specific OS version number. | Quick check for known vulnerabilities tied to a specific Windows build. |
| **`set`** | (None) | Shows all system environment variables, including the **Path**. | Reveals the directories Windows searches for executables, useful for security auditing. |
| **`driverquery`** | (None) | Lists all installed device drivers. | Used by defenders to check for unauthorized or outdated drivers that could pose a risk. |
| **`chkdsk`** | (None) | Checks the disk for errors and bad sectors. | System health and reliability check. |

---

## 2. Process & Task Management

These commands allow you to view, stop, and manage running programs.

| Command | Key Switches/Flags | Function (Simple) | Security Relevance |
| :--- | :--- | :--- | :--- |
| **`tasklist`** | `/FI` (Filter) | Shows a list of all programs running on the system. | Used to quickly identify unexpected or malicious programs running in the background. |
| **`tasklist /FI ...`**| `imagename eq <name>` | Searches for a specific process (e.g., `sshd.exe`). | Speeds up the search for a target process during an investigation. |
| **`taskkill`** | `/PID <number>` | Terminates a process using its **Process ID (PID)**. | Crucial for **stopping suspicious or rogue processes** instantly. |
| **`taskkill`** | `/F` | Forces the process to close immediately. | Used when a suspicious process refuses to shut down normally. |

---

## 3. Networking & Connections

These commands are the foundation of network troubleshooting and security monitoring.

| Command | Key Switches/Flags | Function (Simple) | Security Relevance |
| :--- | :--- | :--- | :--- |
| **`ipconfig /all`** | `/all` | Shows full network details (IP, DNS Servers, MAC Address). | **Reconnaissance:** Identifies DNS servers and the network topology. |
| **`ping <target>`** | (None) | Checks if your computer can reach another server on the network or internet. | Basic **host discovery** and connectivity check. |
| **`tracert <target>`** | (None) | Maps the path your data takes to reach its destination. | Useful for network mapping and troubleshooting connection bottlenecks. |
| **`nslookup <target>`** | `<target> <DNS IP>` | Asks a DNS server for a website's IP address (can specify a server like `1.1.1.1`). | Used to verify DNS records, or to test resolution against specific, secure servers. |
| **`netstat`** | **`-abon`** | **The Best Combination:** Shows all connections, the program name, and the **PID**. | **Incident Response:** The primary command for finding **suspicious connections** and the program (PID) that created them. |
| **Connection Statuses**| `LISTENING`, `ESTABLISHED`, etc. | Shows a connection's current status. | **Security Audit:** Knowing a port is `LISTENING` helps find open services that could be attacked. |

---

## 4. File System & Utility Commands

These are essential for navigation and file management.

| Command | Key Switches/Flags | Function (Simple) | Utility Relevance |
| :--- | :--- | :--- | :--- |
| **`dir`** | `/s`, `/a` | Shows what's inside a folder (`/a` for hidden files, `/s` for subfolders). | Essential for file discovery and searching for hidden data. |
| **`cd <folder>`** | `..` | Navigates the file system (or `cd..` to go up one folder). | Basic system traversal. |
| **`type <file>`** | (None) | Views the contents of a text file. | Quick way to examine configuration or log files. |
| **`more <file>`** | (Piping: `| more`) | Displays long output/files one page at a time. | Improves readability of long files or command output (e.g., `driverquery | more`). |
| **`copy` / `move`** | `*.<ext>` | Duplicates or relocates files (e.g., `copy *.md C:\NewFolder`). | Standard file management. |
| **`del` / `erase`** | (None) | Deletes the specified file. | File management. |
| **`mkdir` / `rmdir`** | (None) | Creates or removes a folder. | Basic directory management. |
| **`cls` / `help`** | (None) | Clears the screen and provides command help. | Basic terminal maintenance. |

---
