# Incident Escalation Practice (SOC Workflow)

## Overview

This project simulates a real-world Security Operations Center (SOC) workflow using TheHive. It demonstrates how a security analyst handles a high-priority incident, performs escalation to Tier 2, maps the attack to MITRE ATT&CK, and designs a SOAR automation playbook.



## Tools Used

* TheHive (Incident Response Platform)
* Google Docs (SITREP Documentation)
* Splunk Phantom (SOAR - simulated)



## Scenario

An unauthorized access attempt was detected on **Server-Y** from IP address **192.168.1.200**.

* Detection Time: 18 August 2025, 13:00
* Severity: High
* MITRE Technique: T1078 (Valid Accounts)



## Tasks Performed

### 1. Case Creation

* Created a new case in TheHive:

  * Title: Unauthorized Access on Server-Y
  * Severity: High
  * Tags: wazuh soc alerts



### 2. Observable Analysis

* Added suspicious IP address:

  * 192.168.1.200
* Marked as potential brute-force / suspicious activity



### 3. Incident Escalation

* Created an escalation task
* Documented findings in a 100-word summary
* Assigned case to Tier 2 Analyst



### 4. MITRE ATT&CK Mapping

* Catalog: Enterprise ATT&CK
* Tactic: Initial Access
* Technique: T1078 - Valid Accounts



### 5. SITREP (Situation Report)

Prepared a structured incident report including:

* Summary
* Actions Taken
* Impact
* Status



### 6. SOAR Automation (Simulated)

Designed a Splunk Phantom playbook:

**Logic:**


IF severity == high
THEN assign to Tier2 Analyst
