# File Integrity Monitoring

## Objective
Monitor critical files for unauthorized changes.

## Target
Windows 11 Endpoint

## Activity
- Created
- Modified
- Deleted
files inside the monitored directory.

## Detection
- Wazuh FIM generated alerts.
- Dashboard displayed file path and action.

## MITRE ATT&CK
- T1070.004 - File Deletion
- T1485     - Data Destruction
- T1565.001 - Stored Data Manipulation

## Result
File modifications were detected successfully.

![FIM Alert](https://github.com/14shreyas04/SOC-Homelab-Wazuh/blob/main/images/FIM(Windows)_alert.png)
