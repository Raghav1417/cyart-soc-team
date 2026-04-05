# Full SOC Workflow Simulation Project

## Objective
This project simulates a complete Security Operations Center (SOC) workflow including attack simulation, detection, triage, response, escalation, and reporting.

## Tools Used
- Metasploit
- Wazuh
- CrowdSec
- TheHive
- MITRE ATT&CK Framework

---

## Workflow Overview

### 1. Attack Simulation
A vulnerability in Metasploitable2 was exploited using Metasploit (Samba usermap script).

### 2. Detection and Triage
Wazuh SIEM detected suspicious activity. Logs were analyzed and mapped to MITRE ATT&CK techniques.

### 3. Response and Containment
The attacker IP was blocked using CrowdSec.

### 4. Escalation
Incident escalated to Tier 2 using TheHive.

### 5. Reporting
Incident documented using SANS-style reporting.

### 6. Briefing
A summary was created for non-technical stakeholders.

---

## Outcome
The SOC workflow successfully detected, analyzed, and mitigated the simulated attack.
