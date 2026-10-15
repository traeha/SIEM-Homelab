# SIEM-Homelab

## Overview
- I built a small practice network using two virtual machines (VMs) in VirtualBox, with my laptop's command prompt acting as the attacker.
- This was my first cybersecurity project, and I was new to most of the tools I used. I used Claude LLM to guide me through the process while I ran the commands, generated the attacks, and analyzed and logged all of my findings.
- My goal was to gain hands on experience in cybersecurity beyond my coursework, specifically learning how a SIEM detects attacks and how to read its alerts. I learn best by doing, so this was a great starting project for me.


## Architecture
```
Attacker (Windows laptop)
   | runs the SSH login attempts
   v
Ubuntu VM (victim, runs Wazuh agent)
   | sends logs and file events
   v
Wazuh VM (manager + dashboard)
   | analyzes events and raises alerts
   v
Me, investigating the alerts in the dashboard
```

- **Wazuh VM:** the "security guard." It collects logs from other devices and raises alerts when something looks suspicious. This kind of tool is called a SIEM (Security Information and Event Management).
- **Ubuntu VM:** the "victim" computer being watched. The Wazuh agent on it reads its logs and watches files, then sends them to the Wazuh VM.
- **Windows laptop:** the "attacker," used to simulate attacks on the Ubuntu VM.
- **Networking:** the Ubuntu VM has two adapters, NAT for internet access and Bridged for lab traffic between the machines.
  
## Tools Used
- **Wazuh:** open-source SIEM (manager and dashboard) that collects logs and raises alerts
- **Ubuntu:** the monitored endpoint, running the Wazuh agent and an SSH server
- **VirtualBox:** runs both VMs on my laptop
- **SSH and Windows Command Prompt:** used to simulate the attacks
- **MITRE ATT&CK:** framework Wazuh uses to tag alerts by attacker technique
## What I Did
## Findings
## Problems I Solved
## What I Learned
## Next Steps
