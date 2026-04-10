#  Alert Triage with Automation using Wazuh, VirusTotal & TheHive

##  Objective
The objective of this project is to triage security alerts and automate validation using threat intelligence tools.



##  Tools Used
- Wazuh (SIEM for alert detection)
- VirusTotal (Threat Intelligence)
- TheHive (Incident Response Platform)



##  Alert Triage (Wazuh)

A suspicious alert was analyzed in Wazuh.

### Query Example:


### Findings:
A suspicious file download alert was detected from a local system.



##  Triage Table

| Alert ID | Description     | Source IP      | Priority | Status |
|----------|----------------|----------------|----------|--------|
| 005      | File Download  | 192.168.1.102  | High     | Open   |



##  Automated Validation (VirusTotal)

The file hash was checked using VirusTotal to determine if it is malicious.

### Result:
- The hash showed suspicious behavior
- Detected by multiple antivirus engines



##  TheHive Automation

TheHive was used to automate threat validation by integrating VirusTotal.

- Alerts were enriched with threat intelligence
- Hash lookup was automated
- Case created for investigation


##  Conclusion

The alert triage process identified a suspicious file download. Automated validation using VirusTotal confirmed potential malicious activity. Integration with TheHive improved response efficiency by automating threat intelligence checks.
