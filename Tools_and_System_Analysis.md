# Tool & System Analysis

In this section, I explore the tools used in my cybersecurity lab. These tools were essential for both attacking and defending the virtual environment. Each tool listed below played a specific role in simulating a real-world penetration testing workflow, allowing me to learn about their capabilities and how they work together in practice.

---

### 🔧 Metasploit Framework
**Command:** `msfconsole`

Metasploit is a powerful tool used for developing and executing exploit code against a target system. I used it to run the Samba exploit (`exploit/multi/samba/usermap_script`) against Metasploitable 2. It allowed me to deliver a payload to open a remote shell. This helped me understand how attackers use known vulnerabilities to gain unauthorized access.

---

### 🌐 Nmap
**Command:** `nmap -sV 192.168.12.14`

Nmap is a network scanning tool used to discover hosts and services. I used it to scan the Metasploitable 2 machine and identify open ports and running services. This information helped me choose the Samba service on port 139 as the attack vector for Metasploit.

---

### 🕵️ Nikto
**Command:** `nikto -h http://192.168.12.14`

Nikto is a web vulnerability scanner that checks for outdated software and insecure configurations on web servers. I used it on Metasploitable 2 to find vulnerabilities in the default Apache setup. This showed me how easily automated tools can identify weaknesses in public-facing applications.

---

### 💻 Netcat
**Command:** `nc 192.168.12.14 4444`

Netcat is a simple networking utility used for reading and writing data across network connections. I used it with Metasploit’s bind shell payload (`cmd/unix/bind_netcat`) to connect back to the target once the shell was opened. It demonstrated how a reverse or bind shell connection allows remote interaction with a compromised system.

---

### 🧠 Snort (IDS/IPS)
**Location:** Installed on pfSense

Snort is an intrusion detection and prevention system (IDS/IPS). It was installed on the pfSense firewall to monitor and analyze traffic between the attacker and target. During my attacks, Snort generated alerts about suspicious activity like port scans and shell access, showing how a properly configured IDS can detect malicious behavior in real time.

---

### 🛡️ pfSense
**Purpose:** Firewall & IDS/IPS Host

pfSense served as both a firewall and the platform for Snort. It segmented the network and controlled traffic between internal and external environments. This simulated a real-world network security architecture and emphasized the importance of traffic filtering and threat monitoring.

---

### 🐧 Linux Commands
**Commands Used:**
- `id`: Displays user ID info.
- `whoami`: Shows current username.
- `uname -a`: Displays OS and kernel version.
- `hostname`: Displays system hostname.
- `ifconfig`: Lists network interfaces and IP addresses.
- `netstat -antp`: Shows active network connections.
- `ps aux`: Lists running processes.
- `cat /etc/passwd`: Lists all user accounts.
- `ls /home`: Shows home directories.

These commands were run after gaining shell access to the target. They helped me learn about privilege escalation, system enumeration, and post-exploitation techniques used by attackers to explore compromised systems.

---

This combination of tools gave me a full view of how cybersecurity tools interact in a real environment, from initial scanning and exploitation to detection and response.
