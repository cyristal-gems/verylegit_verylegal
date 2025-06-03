# Very Legit, Very Legal: A Noob’s First Cybersecurity Lab

Welcome to my first cybersecurity lab! This project was built as part of a
 Cybersecurity Fellowship to simulate a realistic, beginner-friendly environment for learning offensive and defensive security techniques.  

The lab uses VirtualBox to create a segmented network with the following components:  
- **pfSense Firewall/IDS/IPS**: Acts as the firewall and traffic controller. Snort is installed for intrusion detection.  
- **Kali Linux Attacker Machine**: Simulates an external attacker using tools like Metasploit, Nmap, Nikto, and Netcat.  
- **Metasploitable 2 Vulnerable Target**: A deliberately insecure Linux machine for testing attacks.  

---

## 📂 Lab Sections

This repository is organized into the following sections:  

- [Lab Setup & Configuration](Lab-Setup-and-Configuration.md)  
- [Tool & System Analysis](Tool-and-System-Analysis.md)  
- [Security Relevance](Security-Relevance.md)  
- [Reflection](Reflection.md)  

Each section is written in Markdown for easy reading and includes commands, explanations, and insights from my beginner perspective.

---

## 🖥️ Screenshots & Diagrams

- 📷 **Screenshots**: Stored in the `/screenshots` folder (e.g., pfSense setup, terminal output, Snort alerts).  
- 🗺 **Network Diagram**: Stored in the `/diagram` folder as a `.drawio` file, showing the lab's network topology, VM names, IPs, and interfaces.  

---

## 🎯 Learning Goals

- Understand the basics of **network segmentation**, **firewalls**, and **IDS/IPS**.  
- Explore common attacker tools (Metasploit, Nmap, Nikto, Netcat) and practice basic **penetration testing**.  
- Simulate real-world cybersecurity scenarios in a safe, isolated environment.  

---

## 📖 Disclaimer

This lab is for educational purposes only. All tools and techniques used here are intended for learning, not for unauthorized use.  

---

Thanks for checking out my lab! 🚀  
