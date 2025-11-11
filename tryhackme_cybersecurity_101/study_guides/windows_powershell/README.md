# 📘 Windows PowerShell Essential Study Guide

This guide summarizes key PowerShell cmdlets (commands) for system interaction, file management, security analysis, and remote administration. PowerShell is the modern, primary shell for Windows environments.

---

## 1. System, File Management, and Discovery

| Cmdlet | Syntax Example | Function (Simple) | Security Relevance |
| :--- | :--- | :--- | :--- |
| **`Get-Command`** | `Get-Command -CommandType Function` | Lists available commands; can filter by type. | Useful for **finding new or unusual commands** on a system during an audit. |
| **`Get-Alias`** | (No example needed) | Lists all command aliases (shortcuts). | Useful for understanding shortcuts used in custom scripts. |
| **`Get-ChildItem`** | `Get-ChildItem -path "C:\users..."` | Shows all files and folders in a location (like CMD's `dir`). | **Reconnaissance:** Enumerating files, especially system files or custom scripts. |
| **`Set-Location`** | `Set-Location -path ".\documents"` | Changes the current working directory (like CMD's `cd`). | Basic system traversal. |
| **`New-Item`** | `New-Item -ItemType "File"` | Creates a new file or folder. | Essential for creating working directories. |
| **`Remove-Item`** | `Remove-Item -path "..."` | Deletes files or folders. | File management, or removing malicious files during remediation. |
| **`Copy-Item` / `Move-Item`** | (Various paths) | Duplicates or relocates items. | Standard file management and evidence handling. |
| **`Get-Content`** | `Get-Content -path ".\file.txt"` | Views the contents of a text file (like CMD's `type`). | Quick check of configuration files or logs. |
| **`Select-String`** | `Select-String -path "..." -pattern "word"` | Searches for specific text inside a file. | **Forensics:** Used to search logs or config files for keywords. |
| **`Get-ComputerInfo`** | (No example needed) | Shows extensive information about the system. | **Reconnaissance:** Provides a quick, comprehensive system snapshot for auditing. |

---

## 2. Network, Process, and System Status

These cmdlets are essential for real-time monitoring and analysis.

| Cmdlet | Key Use | Function (Simple) | Security Relevance |
| :--- | :--- | :--- | :--- |
| **`Get-NetIPConfiguration`** | (No example needed) | Shows current network settings (IP, DNS, Gateway). | **Networking:** Foundation for troubleshooting and mapping local network setup. |
| **`Get-Process`** | (No example needed) | Shows all programs currently running (like CMD's `tasklist`). | **Monitoring:** Used to identify unexpected or high-resource consuming processes. |
| **`Get-Service`** | (No example needed) | Lists services and their status (running, stopped). | **Security Audit:** Used to check for unauthorized services that might be running unnecessarily. |
| **`Get-NetTCPConnection`** | (No example needed) | Shows all active network connections and ports (like CMD's `netstat`). | **Incident Response:** Critical for finding evidence of active, unauthorized communication. |
| **`Get-FileHash`** | `Get-FileHash -path .\file.txt` | Calculates the hash of a file's content. | **File Integrity:** Used to verify a file hasn't been tampered with or to check against malware hashes. |

---

## 3. Advanced Scripting and Remote Administration

These cmdlets demonstrate PowerShell's power for automation and control across a network.

| Cmdlet | Syntax Example | Function (Simple) | Security Relevance |
| :--- | :--- | :--- | :--- |
| **`Invoke-Command`** | `-ComputerName server01 -ScriptBlock {Get-Service}` | **Runs a command or script on a remote computer** over the network. | **Automation/IR:** Essential for quickly checking the status of multiple servers or deploying remote remediation scripts. |
| **`Invoke-Command`** | `-ComputerName server01 -FilePath c:\scripts\test.ps1` | **Runs an entire PowerShell script file** saved locally onto a remote computer. | **Administration:** Standard way to remotely manage systems and deploy configuration changes. |
