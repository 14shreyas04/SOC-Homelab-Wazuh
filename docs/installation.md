## Environment

| Machine           | Purpose 
|---------          |---------
| Ubuntu Server     | Wazuh Manager 
| Windows 11        | Wazuh Agent + Sysmon + FIM 
| Kali Linux 1      | Wazuh Agent + Suricata + auditd 
| Kali Linux 2      | Attacker 

---

## 1. Install Wazuh

- Install Ubuntu Server
- Install Wazuh Manager using the official installer
            curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh
            sudo bash wazuh-install.sh -a

- Verify:
```
systemctl status wazuh-manager
```

---

## 2. Configure Windows Endpoint

- Install Wazuh Agent
- Install Sysmon
            https://learn.microsoft.com/sysinternals/downloads/sysmon
            https://github.com/SwiftOnSecurity/sysmon-config
            cd Downloads\Sysmon
            Sysmon64.exe -accepteula -i sysmonconfig-export.xml

- Configure File Integrity Monitoring
- Restart the Wazuh Agent

---

## 3. Configure Kali Endpoint

- Install Wazuh Agent
- Install Suricata
            sudo apt install suricata -y
            sudo apt install suricata-update

- Configure auditd
            sudo apt install auditd audispd-plugins -y

- Forward logs to Wazuh

---

## 4. Configure VirusTotal

- Add VirusTotal API key
- Restart Wazuh Manager
- Verify enrichment

---

## 5. Configure Active Response

- Enable `firewall-drop`
- Restart Wazuh
- Verify automatic IP blocking

---

## Verification

- Windows Agent connected
- Kali Agent connected
- Sysmon events visible
- Suricata alerts visible
- auditd logs visible
- FIM alerts visible
- VirusTotal enrichment working
- Active Response blocking SSH brute-force