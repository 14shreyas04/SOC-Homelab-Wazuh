## Overview

Active Response enables Wazuh to automatically execute predefined actions when specific security events are detected. In this lab, it was configured to block SSH brute-force attacks using the built-in `firewall-drop` command.

---

## Configuration

**Response Command**
- `firewall-drop`

**Trigger**
- SSH brute-force detection (Rule ID: 651)

**Target**
- Kali Linux Endpoint

---

## Workflow

SSH Brute-force Attack
          │
          ▼
     Wazuh Agent
          │
          ▼
    Wazuh Manager
          │
  Detects Rule 651
          │
          ▼
Active Response
(firewall-drop)
          │
          ▼
Attacker IP Blocked

---

## Test Scenario

**Attacker**
- Kali Linux

**Target**
- Kali Linux Endpoint

**Tool Used**
- Hydra

**Attack Command**

```bash
hydra -l root -P /usr/share/wordlists/metasploit/unix_passwords.txt -t 6 ssh://192.168.x.y
```

---

## Detection

The SSH brute-force attempt generated security alerts in the Wazuh Dashboard.

---

## Automated Response

Once the configured rule was triggered:

- Wazuh executed the `firewall-drop` command.
- The attacker's IP address was automatically blocked.
- Further SSH connection attempts were denied until the timeout expired.

---

## Verification

The response was verified by:

- Viewing Active Response alerts in the Wazuh Dashboard.
- Confirming the attacker's IP was added to the firewall.
- Observing that subsequent SSH login attempts were blocked.

---

## Outcome

- Successfully detected SSH brute-force attacks.
- Automatically blocked the attacker's IP.
- Demonstrated automated incident response using Wazuh Active Response.