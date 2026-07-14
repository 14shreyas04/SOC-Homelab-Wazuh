## Overview

This SOC Homelab simulates a Security Operations Center (SOC) using Wazuh as the central SIEM platform. Security events generated from Windows and Linux endpoints are collected, analyzed, enriched with threat intelligence, and displayed on the Wazuh Dashboard.

---

## Lab Components

| Machine                           | Purpose 
|---------                          |---------
| Ubuntu Server                     | Wazuh Manager, Indexer, Dashboard 
| Windows 11                        | Wazuh Agent, Sysmon, File Integrity Monitoring
| Kali Linux (Agent)                | Wazuh Agent, Suricata IDS, auditd 
| Kali Linux (Attacker)             | Attack simulation (Nmap, Hydra, etc.) 

---

## Security Components

### Wazuh Manager
- Collects logs from all agents
- Correlates security events
- Generates alerts
- Executes Active Response

### Windows Endpoint
- Sysmon for process and system monitoring
- File Integrity Monitoring (FIM)
- Wazuh Agent for log forwarding

### Kali Endpoint
- Suricata Network IDS
- auditd for Linux audit logging
- Wazuh Agent for log forwarding

### VirusTotal
- Enriches supported alerts with threat intelligence.

### Active Response
- Automatically blocks SSH brute-force attacks using the `firewall-drop` command.

---

## Data Flow

![Architecture](https://github.com/14shreyas04/SOC-Homelab-Wazuh/blob/main/images/Wazuh_SOC_Architecture.jpg)

Attacker
    │
    ▼
Windows / Kali Endpoint
    │
(Sysmon / FIM / Suricata / auditd)
    │
    ▼
Wazuh Agent
    │
    ▼
Wazuh Manager
    │
 ┌── Alert Correlation
 ├── MITRE ATT&CK Mapping
 ├── VirusTotal Enrichment
 └── Active Response
    │
    ▼
Wazuh Dashboard

---

## Attack Scenarios Tested

- Process execution monitoring (Sysmon)
- File Integrity Monitoring (FIM)
- Network reconnaissance using Nmap
- SSH brute-force using Hydra
- Linux command monitoring using auditd
- Automated IP blocking using Active Response

---

## Technologies Used

- Wazuh
- Sysmon
- Suricata
- auditd
- VirusTotal
- VMware Workstation
- Ubuntu Server
- Windows 11
- Kali Linux
