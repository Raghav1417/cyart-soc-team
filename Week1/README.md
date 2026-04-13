SOC Task: Log Analysis, Monitoring & Alerting
 Project Overview

This project focuses on log analysis, security event documentation, monitoring dashboards, and alert rule configuration in a SOC environment.

It simulates real-world detection of suspicious activities such as:

Brute-force login attempts
Malicious browser activity
Unauthorized service creation
 1. Log Analysis Practice
 Objective

Identify suspicious activities using Windows logs and browser artifacts.

 Windows Event Viewer Analysis
 Key Event IDs
4625 → Failed login attempts
7045 → New service creation
 Steps

Open Event Viewer:

eventvwr.msc

Navigate:

Windows Logs → Security
Apply Filter:
Event ID: 4625, 7045
Analyze:
Repeated failed logins → Brute-force attack
Unknown service creation → Possible malware
 Browser History Analysis
 Tool Used
Eric Zimmerman’s Tools (LECmd)
 Steps
LECmd.exe -d "C:\Users\Username\AppData\Local\Google\Chrome\User Data\Default" --csv output
 Goal
Identify visits to suspicious URLs
Example test:
http://test.com
 Advanced Tasks
 Brute-Force Detection
Perform multiple wrong login attempts in Windows VM
Filter Event ID 4625
Export logs:
wevtutil qe Security /q:"*[System[(EventID=4625)]]" /f:csv > failed_logins.csv
 Zimmerman Tools Practice
Parse Chrome history using LECmd
Identify:
Suspicious domains
Repeated visits
 Tools Used
Built-in:
Windows Event Viewer
wevtutil CLI
Third-party:
LogParser Lizard
Elastic SIEM
 2. Document Security Events
 Objective

Create structured incident documentation.

 Template
Date/Time	Source IP	Event ID	Description	Action Taken
 Example

| 2026-03-20 10:30 | 192.168.1.10 | 4625 | Multiple failed logins detected | Blocked IP |

 3. Monitoring Dashboards
 Objective

Visualize security events using dashboards.

 Tools
Kibana
Grafana
 Dashboards Created
Top 10 Source IPs generating alerts
Frequency of critical Event IDs
 Steps
Connect logs to Elastic/Kibana
Create visualizations:
Bar chart → Source IPs
Line chart → Event frequency
Import:
Sigma detection rules
 4. Configure Alert Rules
 Elastic SIEM Rule
 Rule Details
Name: Detect Failed Logins
Condition: 5+ failed logins in 5 minutes
Index: security-login-*
 Testing
Simulate failed SSH logins
Verify alert trigger
 Advanced Task: Wazuh Alert Rule
 Rule Configuration
Detect 3+ failed logins in 2 minutes
 Test Command
ssh user@192.168.1.x

(Enter wrong password multiple times)

 Alert Validation
Check Wazuh Dashboard
Confirm:
Alert triggered
Correct rule applied
 Learning Approach
 SOC Lab Setup
SIEM: Wazuh
Endpoint Visibility: Osquery
 MITRE ATT&CK Mapping
Activity	Technique	ID
Brute-force login	Credential Access	T1110
PowerShell attack	Execution	T1059
 How to Reproduce
# Generate failed logins (Windows / SSH simulation)
ssh user@192.168.1.x


# Parse browser history
LECmd.exe -d <chrome_path> --csv output
 Key Takeaways
Event ID 4625 is critical for brute-force detection
Browser artifacts reveal attacker activity
Dashboards improve visibility
Alert rules automate detection
MITRE ATT&CK helps map real-world attacks
 Conclusion
 
This project demonstrates hands-on SOC skills including:

Log analysis
Threat detection
Alert creation
Security monitoring

It reflects real-world SOC workflows used by analysts for detecting and responding to cyber threats
