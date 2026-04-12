# Evidence Analysis Report

## 1. Introduction
This report documents the analysis of system evidence and network activity using FTK Imager and Windows netstat.

---

## 2. Tools Used
- FTK Imager
- Windows CMD (netstat)

---

## 3. Evidence Analysis

### Command Executed:



### Observations:
- Multiple UDP connections observed
- Local and private IP communication present
- External IPv6 connections detected

---

## 4. Findings

### Normal Activity:
- 127.0.0.1 → Localhost
- 192.168.x.x → Internal network
- Ports:
  - 137/138 → NetBIOS
  - 1900 → UPnP
  - 5353 → mDNS

---

### Suspicious Findings:

1. External IPv6 connections on port 443:
   - 2606:4700:90c2:7cbc:c264:53b:5ff2:75c4
   - 2405:200:160f:1731::312c:8950

2. High frequency of UDP port 1900 traffic

3. Multiple dynamic ports (50000+ range)

---

## 5. Evidence Collection

FTK Imager was used to:
- Acquire disk data
- Extract relevant files
- Generate hash values for integrity verification

---

## 6. Chain of Custody

| Item        | Description              | Collected By | Date       | Hash Value |
|-------------|--------------------------|--------------|------------|------------|
| Network Log | Netstat Output           | SOC Analyst  | 2025-08-18 | abc123xyz |
| Disk Image  | FTK Export               | SOC Analyst  | 2025-08-18 | def456uvw |

---

## 7. Conclusion

The system shows mostly benign activity. However, external HTTPS connections should be analyzed further for potential threats.



Netstat Log Sample

Protocol: UDP
Local Address: 192.168.13.1
Port: 1900
State: Listening

External Connection:
IP: 2606:4700:90c2:7cbc:c264:53b:5ff2:75c4
Port: 443

---
