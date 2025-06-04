# Lab Setup & Configuration

This section describes how I built my virtual cybersecurity lab, including the setup of VirtualBox, pfSense, Kali Linux, and Metasploitable 2. This lab simulates a realistic network where an attacker tries to breach a vulnerable system, and a firewall and IDS/IPS protect the internal network.  

---

## Virtualization Platform

I used **VirtualBox** as the virtualization platform. VirtualBox is free, beginner-friendly, and allows me to create multiple virtual machines (VMs) that act like real computers. This made it safe to practice hacking and defending without risking my actual computer or network.  

---

## Virtual Machines & Networks

Here’s a table summarizing the virtual machines in my lab:  

| VM Name         | Role                     | Network(s) Connected              | IP Address(es)                  |
|-----------------|--------------------------|----------------------------------|---------------------------------|
| pfSense         | Firewall, IDS/IPS (Snort) | WAN (NAT), AttackerNet, ServerNet, MgmtNet | 192.168.11.1 (AttackerNet), 192.168.12.1 (ServerNet), 192.168.13.1 (MgmtNet) |
| Kali Linux      | Attacker Machine         | AttackerNet, ServerNet           | 192.168.11.14 (AttackerNet), 192.168.12.13 (ServerNet) |
| Metasploitable 2| Vulnerable Target        | ServerNet                        | 192.168.12.14                   |

---

## Network Configuration

### pfSense Interface Setup

- `em0` (WAN): NAT (external connection for updates)  
- `em1` (LAN - AttackerNet): 192.168.11.1/24  
- `em2` (OP1 - ServerNet): 192.168.12.1/24  
- `em3` (OP2 - MgmtNet): 192.168.13.1/24  

### DHCP Settings

| Network         | DHCP Range                |
|-----------------|--------------------------|
| AttackerNet     | 192.168.11.200-210       |
| ServerNet       | 192.168.12.1-25          |
| MgmtNet         | Static only (no DHCP)    |

---

This lab setup provided a safe and controlled space to practice offensive and defensive security techniques using common industry tools.  
