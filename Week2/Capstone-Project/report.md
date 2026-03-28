# Incident Report - VSFTPD Exploit

## Executive Summary
A critical vulnerability (VSFTPD backdoor) was exploited on Metasploitable2 machine. Unauthorized access was detected and contained.

## Timeline
- 11:00 Attack detected
- 11:05 Alert generated in Wazuh
- 11:15 VM isolated
- 11:20 IP blocked

## Detection
Wazuh detected suspicious FTP activity mapped to MITRE ATT&CK T1190.

## Response
- Isolated affected machine
- Blocked attacker IP using firewall
- Verified no lateral movement

## Recommendations
- Patch vulnerable services
- Enable stronger monitoring
- Regular vulnerability scanning
