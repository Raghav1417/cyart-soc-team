# Alert Triage with Automation

## Objective
Perform alert triage using Wazuh and validate using VirusTotal, TheHive, and OTX.

---

## Tools Used
- Wazuh
- TheHive
- VirusTotal
- AlienVault OTX

---

## Task Overview

### Alert Triage (Wazuh)

| Alert ID | Description              | Source IP     | Priority | Status |
|----------|--------------------------|---------------|----------|--------|
| 005      | Suspicious File Download | 192.168.56.1  | High     | Open   |

Wazuh logs show suspicious activity related to file operations and authentication.

---

### Automated Validation

- File hash checked in VirusTotal
- Case created in TheHive
- IP checked in OTX

---

## Conclusion

The alert was validated using threat intelligence tools. VirusTotal confirmed malicious file (EICAR), and OTX showed suspicious IP activity. The case was managed in TheHive successfully.












