# Nmap Network Scan Detection 

## Objective
Detect network reconnaissance using "Suricata" integrated with wazuh

## Attacker
Kali Linux, using GUI based namp: zenmap

## Target
Kali linux Endpoint (Wazuh Agent + Suricata)

## Command used
nmap -T4 -A -v <Target-IP>

## Detection
- Suricata generated IDS alerts
- Alerts were forwarded to wazuh using the agent
- Events appeared in the Wazuh Dashboard

## Result
Network scanning was successfully detected

![Nmap Alert](https://github.com/14shreyas04/SOC-Homelab-Wazuh/blob/main/images/Suricata_alert.png)
