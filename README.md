# SOC Homelab with Wazuh

A Security Operations Center (SOC) Homelab built using **Wazuh** to simulate real-world threat detection, monitoring, and automated incident response across Windows and Linux endpoints.

## Overview

This project demonstrates how a SIEM platform can collect, analyze, and respond to security events generated from multiple endpoints.

The lab includes:

- Windows endpoint monitoring with Sysmon
- Linux monitoring with auditd
- Network Intrusion Detection using Suricata
- File Integrity Monitoring (FIM)
- VirusTotal threat intelligence integration
- Automated incident response using Wazuh Active Response

---

## Architecture

![Architecture](images/architecture.png)

---

## Lab Environment

| Machine                       | Role 
|---------                      |------
| Ubuntu Server                 | Wazuh Manager, Indexer, Dashboard 
| Windows 11                    | Wazuh Agent, Sysmon, FIM 
| Kali Linux (Agent)            | Wazuh Agent, Suricata, auditd 
| Kali Linux (Attacker)         | Attack Simulation 

---

## Features

- Windows endpoint monitoring using Sysmon
- Linux command monitoring using auditd
- Network attack detection using Suricata IDS
- Real-time File Integrity Monitoring
- VirusTotal threat intelligence integration
- Active Response using `firewall-drop`
- Custom Wazuh detection rules
- MITRE ATT&CK mapping (where applicable)

---

## Attack Scenarios

| Scenario                          | Detection 
|----------                         |-----------
| PowerShell Execution              | Sysmon 
| Command Prompt Execution          | Sysmon 
| File Modification                 | File Integrity Monitoring 
| Nmap Network Scan                 | Suricata 
| SSH Brute Force (Hydra)           | Wazuh + Active Response 
| Linux Command Execution           | auditd 

Detailed walkthroughs are available in the **attacks/** folder.

---

## Repository Structure

SOC-Homelab-Wazuh/
│
├── README.md
├── LICENSE
├── images/
├── configs/
├── docs/
└── attacts/

---

## Technologies Used

- Wazuh
- Sysmon
- Suricata
- auditd
- VirusTotal API
- VMware Workstation
- Ubuntu Server
- Windows 11
- Kali Linux

---

## Documentation

Additional documentation is available in the **docs/** directory.

- Installation Guide
- Architecture
- Active Response

---

## Acknowledgements

- Wazuh
- Microsoft Sysinternals
- Suricata
- MITRE ATT&CK
- VirusTotal

---

## Author

**Shreyas R**

Cybersecurity | SOC | SIEM | Network Security