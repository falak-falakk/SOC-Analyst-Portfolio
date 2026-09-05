# WHOIS Lookup & IP Reputation Investigation
## Project Overview
This project demonstrates a basic SOC analyst investigation combining two related security tasks:
. WHOIS lookup to collect domain registration and DNS information.
. IP reputation analysis using VirusTotal to evaluate whether an IP address has been flagged by security vendors.
The purpose of the investigation was to collect technical information, examine reputation results, and document the findings using publicly available security tools
## Investigation Targets
### Domain
`google.com`
### IP Address
`64.233.180.100`
# 1. WHOIS Lookup
## Objective
The purpose of the WHOIS lookup was to collect registration and DNS-related information about the domain `google.com`.
## Findings
| Field | Result |
|---|---|
| Domain | google.com |
| Registered On | 1997-09-15 |
| Expires On | 2028-09-14 |
| Name Server 1 | ns1.google.com |
| Name Server 2 | ns2.google.com |
| Name Server 3 | ns3.google.com |
| Name Server 4 | ns4.google.com |
The WHOIS result also displayed several domain status restrictions, including client and server restrictions related to deletion, transfer, and updates.
## WHOIS Observation
The lookup provided information about the domain's registration history, expiration date, status, and authoritative name servers.
---
# 2. IP Reputation Check
## Objective
The IP address `64.233.180.100` was investigated using VirusTotal to determine whether security vendors had identified the IP as malicious or suspicious.
## VirusTotal Findings
| Field | Result |
|---|---|
| IP Address | 64.233.180.100 |
| Detection | 0/90 |
| Network | 64.233.160.0/19 |
| Autonomous System Number | AS15169 |
| Autonomous System Label | Google LLC |
| Regional Internet Registry | ARIN |
| Country | US |
VirusTotal also displayed:
> 8 detected files communicating with this IP address
This indicates that VirusTotal had identified eight files associated with communications involving the IP address. This observation alone does not establish that the IP address is malicious.
---
# 3. Reputation Assessment
The VirusTotal detection result was:
**0/90**
This means that none of the 90 security vendors shown in the captured result flagged the IP address as malicious at the time of the analysis.
However, a `0/90` result should not be interpreted as a guarantee that an IP address is completely safe. Reputation can change over time, and additional investigation may be required when other suspicious indicators are present.
# 4. Combined Analysis
The investigation used two different types of information:
### WHOIS
WHOIS information helped identify registration and DNS-related information for `google.com`.
### IP Reputation
VirusTotal provided security-vendor reputation information for the IP address `64.233.180.100`.
Combining these sources provides a broader view of an indicator during a SOC investigation.
# 5. SOC Analyst Conclusion
Based on the evidence captured during this investigation:
- The WHOIS lookup provided registration and name-server information for `google.com`.
- The investigated IP address `64.233.180.100` belongs to the network `64.233.160.0/19`.
- The IP is associated with **AS15169 (Google LLC)** according to the VirusTotal result.
- The VirusTotal detection result was **0/90**.
- VirusTotal showed eight files communicating with the IP.
- The available evidence does not, by itself, provide sufficient grounds to classify the IP as malicious.
A SOC analyst should consider additional context, such as DNS history, network activity, associated files, timestamps, and other threat-intelligence sources before making a final determination.
# 6. Tools Used
- WHOIS lookup
- VirusTotal
- Public threat-intelligence information
# 7. Skills Demonstrated
- WHOIS investigation
- IP reputation analysis
- IP address investigation
- DNS information analysis
- Threat intelligence
- Security evidence collection
- IOC investigation
- SOC analyst documentation
- Analytical assessment
# 8. Evidence
Screenshots documenting the investigation are available in the `screenshots` folder.
### Evidence 1 — WHOIS Lookup
WHOIS information collected for `google.com`.
### Evidence 2 — VirusTotal Detection
VirusTotal security-vendor analysis of `64.233.180.100`.
### Evidence 3 — VirusTotal Details
Network, ASN, organization, registry, and country information for the investigated IP.
## Disclaimer
This project was performed as an educational cybersecurity exercise using publicly available information. The findings represent the information visible during the investigation and should not be treated as a definitive security verdict.
