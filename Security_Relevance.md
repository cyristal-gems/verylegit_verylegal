# Security Relevance

### Why IDS and IPS Tools Matter in Cyber Defense

Intrusion Detection Systems (IDS) and Intrusion Prevention Systems (IPS) are essential components in any secure network environment. These tools help monitor, detect, and sometimes prevent suspicious or malicious activity. In this lab, I used **Snort** as an IDS/IPS tool installed on the pfSense firewall to watch traffic between the attacker and the target machine.

**Snort** analyzes traffic in real time and can generate alerts for known attack patterns (like port scans or exploits). In real-world settings, this is how security teams catch early warning signs of cyberattacks. In my lab, Snort helped me understand how alerts work and gave visibility into my simulated attack, showing what an actual intrusion might look like to a network defender.

---

### How This Lab Simulates Real-World Security Environments

This lab setup is designed to mimic the segmentation and monitoring found in professional networks. With three key zones (attacker network, internal network, and external connection), I was able to simulate both offensive and defensive roles:

- **Kali Linux** represented a malicious outsider or ethical hacker.
- **Metasploitable 2** acted as a vulnerable internal server.
- **pfSense with Snort** stood in for a typical enterprise firewall and IDS/IPS combo.

The use of realistic tools like Metasploit, Netcat, and Nmap mirrors the techniques used in penetration testing, while pfSense and Snort offer experience with enterprise-grade defensive strategies. Practicing in this isolated virtual environment helped me understand not just how attacks happen, but also how to detect and prevent them.
