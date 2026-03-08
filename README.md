# Splunk Firewall Log Analysis

## Overview
SIEM analysis of firewall logs using Splunk Enterprise to detect
real threats including brute force attacks, C2 malware beaconing,
and port scanning.

## Tools
- Splunk Enterprise (Free)
- SPL (Search Processing Language)
- Firewall Log Dataset (CSV, 100 events)

## Key Findings
- **Brute Force**: IP 185.220.101.34 (Russia) made 64 blocked attempts
  targeting RDP, SSH, SMB, MySQL over 1 hour
- **Compromised Host**: Internal IP 192.168.1.200 beaconing to port 4444
  (C2 server, China) and port 6667 (IRC botnet, Netherlands) — 40 events
- **Port Scan**: IP 45.33.32.156 scanned 8 unique ports including
  database services (MySQL, MSSQL, Oracle, Postgres)

## MITRE ATT&CK Mapping
| Detection | Technique |
|---|---|
| Brute Force (RDP/SSH) | T1110 - Brute Force |
| C2 Beacon port 4444 | T1071 - Application Layer Protocol |
| IRC Botnet port 6667 | T1071 - Application Layer Protocol |
| Port Scan | T1046 - Network Service Scanning |

## Screenshots
See the /screenshots folder for all dashboard and query results.

## Files
- firewall_logs.csv — sample dataset
- queries/firewall_detections.txt — all 10 SPL queries
- screenshots/ — dashboard and findings screenshots
