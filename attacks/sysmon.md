# Sysmon Process Monitoring

## Objective
Detect suspicious process creation using Sysmon.

## Target
Windows 11 Endpoint

## Activity
Executed PowerShell, creation and deletion of application and files in the endpoint.

## Detection
- Sysmon generated Windows Event Logs.
- Wazuh parsed and displayed the alerts.
- MITRE ATT&CK mapping was available.

## MITRE ATT&CK
- T1059.003 - Execution [Windows command prompt started by an abnormal process]
- T1087     - Discovery [Suspicious Windows cmd shell execution]
- T1105     - Command and Control [Scripting file created under Windows Temp or User folder]

## Result
Process execution events were successfully monitored.

![Sysmon Alert](https://github.com/14shreyas04/SOC-Homelab-Wazuh/blob/main/images/Sysmon_alert.png)
