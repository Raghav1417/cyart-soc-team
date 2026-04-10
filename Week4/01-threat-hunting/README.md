#  Alert Triage with Automation

##  Objective

To perform alert triage using Wazuh and validate suspicious activity using TheHive and VirusTotal.

---

##  Tools Used

* Wazuh (SIEM)
* TheHive (Incident Response Platform)
* VirusTotal (Threat Intelligence)

---

##  Step 1: Alert Triage (Wazuh)

Alerts were analyzed using the **Discover module** in Wazuh (`wazuh-alerts-*` index).

* Investigated logs related to file activity
* Observed security event:

  * Rule ID: 52004
  * Description: AppArmor denied operation
  * Severity Level: 4

### Triage Table (Mock Simulation)

| Alert ID | Description   | Source IP     | Priority | Status |
| -------- | ------------- | ------------- | -------- | ------ |
| 005      | File Download | 192.168.1.102 | High     | Open   |


##  Step 2: Case Creation (TheHive)

* Created case: **Suspicious File Download**
* Severity: **Medium**
* TLP/PAP: **Amber**
* Assigned to: SOC Analyst



##  Step 3: Observable Analysis

* Added file hash as observable:

text
44d88612fea8a8f36de82e1278abb02f

* Tagged as: `malware`
* Marked as IOC (Indicator of Compromise)



##  Step 4: VirusTotal Validation

The file hash was analyzed using VirusTotal.

###  Result:

* Detected by **multiple antivirus engines**
* Labels included:

  * EICAR-Test-File
  * Win32:EICAR
  * Malicious/Test Signature

 This confirms the file is **malicious (test malware)**



##  Automation Insight

* VirusTotal integration via Cortex was intended
* Due to lab limitations, validation was performed manually
* Still demonstrates **threat intelligence enrichment**



##  Analysis Summary (50 Words)

The alert was triaged in Wazuh by analyzing security logs. A suspicious file-related event was identified and escalated to TheHive. The file hash was validated using VirusTotal, which showed multiple detections across antivirus engines. This confirms malicious activity and demonstrates how automation improves threat validation and incident response efficiency.


##  Screenshots

* Wazuh Discover alerts
* TheHive case creation
* Observable (hash) added
* VirusTotal detection results




##  Outcome

Successfully performed alert triage and validated malicious activity using threat intelligence tools. The workflow demonstrates integration of SIEM, incident response, and external intelligence for efficient security operations.

