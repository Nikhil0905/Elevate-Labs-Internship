# 🛡️ Task 4: Setup and Use a Firewall on Linux  
**Date:** 27th June, 2025

---

## 🎯 Task Objective  
Configure and test firewall rules using `ufw` (Uncomplicated Firewall) on Linux to block and allow specific types of network traffic.

---

## 🔧 System Configuration Summary

| Parameter            | Value                    |
|----------------------|--------------------------|
| OS                   | Parrot OS (Debian-based) |
| Firewall Tool        | UFW (CLI) + GUFW (GUI)   |
| Kernel Version       | Linux 6.x (Parrot Sec)   |
| Desktop Environment  | XFCE                     |
| Test Utility         | `telnet` (for verifying blocked ports) |

---

## 📋 Commands Executed

| Action                    | Command                    |
|---------------------------|----------------------------|
| Enable Firewall           | `sudo ufw enable`          |
| Disable Firewall          | `sudo ufw disable`         |
| Check Firewall Status     | `sudo ufw status verbose`  |
| Reload Rules              | `sudo ufw reload`          |
| Allow HTTP (port 80)      | `sudo ufw allow 80`        |
| Allow HTTPS (port 443)    | `sudo ufw allow 443`       |
| Block Telnet (port 23)    | `sudo ufw deny 23`         |
| Allow SSH (port 22)       | `sudo ufw allow 22`        |
| Check Numbered Rules      | `sudo ufw status numbered` |
| Delete Rule for Port 23   | `sudo ufw delete 1`        |
| Reset All Rules (optional)| `sudo ufw reset`           |

---

## 🚫 Blocked Port Test – Telnet on Port 23

### Command Used:
```bash
telnet localhost 23
```
### ✅ Expected Behavior:
Connection refused or timeout

### ✅ Observed Behavior:
Telnet connection was **blocked**, confirming that the firewall rule was applied successfully.

---

## 🖥️ GUI Firewall Configuration (GUFW)

Opened **GUFW** from system settings as superuser.

- **Status:** Enabled  
- **Default Policy:** Incoming = Deny, Outgoing = Allow

### 🔒 Custom Rules Visible:
- ❌ Blocked TCP port **23**  
- ✅ Allowed TCP ports **22**, **80**, **443**

### 📸 Screenshots:
- GUFW Dashboard with rule logs  
- GUFW Rules Table showing allowed and denied services

---

## 🔍 Key Concepts Demonstrated

| Concept                    | Observed |
|----------------------------|----------|
| Port-based Traffic Control | ✅       |
| SSH Whitelisting           | ✅       |
| Telnet Blacklisting        | ✅       |
| Resetting Firewall Rules   | ✅       |
| GUI vs Terminal Firewall Ops | ✅     |
| Packet Filtering Behavior  | ✅       |

---

## 🧠 Understanding Firewall Behavior

Firewalls inspect and filter **inbound** and **outbound** packets using predefined rule sets.

### In this lab:
- Inbound **Telnet (port 23)** was **blocked**, proving basic packet filtering.  
- **SSH (port 22)** was **allowed** to maintain remote access.  
- GUI and terminal configurations were **synchronized**.  
- **UFW** helped create and enforce rule sets with minimal complexity.

This exercise provided foundational experience in:

- Network security operations  
- Host-based intrusion prevention  
- Rule lifecycle management

---

## ✅ Deliverables

| Item                      | Attached |
|---------------------------|----------|
| UFW CLI Rule Status       | ✅       |
| Numbered Rule Screenshot  | ✅       |
| Telnet Output Screenshot  | ✅       |
| GUFW GUI Logs             | ✅       |
| Commands Log              | ✅       |
| Final Status After Reset  | ✅       |

---

## 🔗 Tools Used

- `ufw` (CLI-based firewall manager)  
- `gufw` (graphical frontend)  
- `telnet` (connection tester)  
- Parrot Terminal Emulator  
- Screenshot tool for GUI logs

---

## 🧾 Conclusion

This task demonstrated how to configure and test firewall behavior using both **CLI (`ufw`)** and **GUI (`gufw`)**.  
By simulating real-world configurations like **blocking Telnet** and **preserving SSH access**, I developed hands-on experience with:

- Host-based firewalls  
- Rule testing  
- Network service control

---

## 📩 Submission & Notes

This Markdown file and supporting screenshots have been added to the submission folder.  
This exercise is part of a broader **cybersecurity lab series**.

> 🔐 *Real-world security begins with mastering basic tools like firewalls. This was a critical foundational skill for both Red and Blue team operations.*

