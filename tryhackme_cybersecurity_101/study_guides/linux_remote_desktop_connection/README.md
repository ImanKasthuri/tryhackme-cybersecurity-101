# 🖥️ Linux Remote Desktop Connection Guide

This guide details the **`xfreerdp`** command, the standard utility on Linux for initiating a Remote Desktop Protocol (RDP) connection to a Windows host.

## **xfreerdp Syntax and Use**

| Command Component | Description | Function |
| :--- | :--- | :--- |
| **`xfreerdp`** | The main utility (client) that initiates the RDP session. | Establishes the connection from the Linux machine. |
| **`/u: <username>`** | Specifies the **username** for logging into the Windows host. | Authenticates the user. |
| **`/p: <password>`** | Specifies the **password** for the given user. | Authenticates the user. |
| **`/v: <IP address>`** | Specifies the **IP address** or **hostname** of the target Windows machine. | Directs the connection to the correct host. |

### **Example Syntax**

```bash
xfreerdp /u:user_name /p:P@ssw0rd! /v:192.168.1.10
