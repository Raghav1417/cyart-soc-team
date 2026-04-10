# Threat Hunting Practice using Wazuh, Velociraptor & AlienVault OTX

## Objective
The objective of this project is to perform threat hunting to detect misuse of valid accounts using MITRE ATT&CK technique T1078.


##  Hypothesis
An attacker may use valid accounts to gain unauthorized privileged access on the system.


## Tools Used
- Wazuh (SIEM)
- Velociraptor (Endpoint Monitoring)
- AlienVault OTX (Threat Intelligence)


##  Log Analysis (Wazuh)

### Query Used:




### Findings:
- User `raghav` accessed root privileges using sudo (rule.id 5502)
- Indicates privilege usage activity
- Windows logs showed system activity (Event ID 16384)

---

##  Threat Intelligence (AlienVault OTX)

### IOC Identified:
- IP Address: 185.220.101.1  
- Activity: Web scanning, SSH brute-force  
- Technique: T1078 (Valid Accounts)

Additional indicators were found by searching T1078 in OTX pulses, which included multiple IPs associated with credential abuse and suspicious login activity.



## Endpoint Analysis (Velociraptor)

### Query Used:




This was used to inspect running processes and identify any suspicious activity.



##  Correlation

- Wazuh logs → Privileged access (sudo/root)
- OTX → Malicious IP activity (credential abuse)
- Velociraptor → Endpoint process monitoring

 Combined analysis suggests possible misuse of valid credentials.


##  Findings Summary

| Timestamp            | User   | Event / Rule | Source   | Notes                    |
|----------------------|--------|-------------|----------|--------------------------|
| 2026-04-10 02:03:58  | raghav | 5502        | Wazuh    | sudo root privilege used |
| 2026-04-09 02:32:23  | system | 16384       | Windows  | Defender activity        |



##  Conclusion

A threat hunting investigation was conducted based on MITRE ATT&CK T1078. While no confirmed attack was detected, privileged access activity was observed. Threat intelligence supported the possibility of credential abuse. Continuous monitoring and strict access control policies are recommended to mitigate risks.
