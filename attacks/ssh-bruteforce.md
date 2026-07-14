# SSH Brute Force Detection

## Objective
Detect SSH brute-force attempts and trigger Active Response.

## Attacker
Kali Linux

## Target
Kali Linux Endpoint

## Command Used
hydra -l root -P /usr/share/wordlists/metasploit/unix_passwords.txt -t 6 ssh://<Target-IP>

## Detection
- Multiple failed SSH login attempts detected.
- Wazuh Rule 5710/5763/651 triggered.

## Response
- Active Response executed.
- firewall-drop blocked the attacker's IP.

## Result
Attacker IP was automatically blocked.

![BruteForce Alert](images/Active_response.png)
