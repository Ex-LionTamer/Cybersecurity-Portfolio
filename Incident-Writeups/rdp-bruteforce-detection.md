# Detecting RDP Brute Force Activity

## Summary
This project demonstrates detection logic for identifying brute force attacks against Remote Desktop Protocol (RDP) services.

## Threat Description
Attackers commonly target exposed RDP services to gain unauthorized access using password spraying or brute force attacks.

## MITRE ATT&CK

| Technique | Description |
|---|---|
| T1110 | Brute Force |
| T1021.001 | Remote Desktop Protocol |

## Indicators of Compromise

### Windows Event IDs
- 4625 — Failed Logon
- 4624 — Successful Logon

### Suspicious Indicators
- Multiple failed logins
- Repeated source IP
- Logon Type 10

## Detection Logic
Detect excessive failed logon attempts from a single source IP within a short time period.

## Example Detection Opportunities
- Windows Security Logs
- SIEM correlation rules
- Account lockout events

## Potential Impact
Successful brute force attacks may allow attackers to:
- gain unauthorized access
- move laterally
- deploy ransomware
- steal credentials

## Sigma Rule
See:
`Sigma-Rules/rdp_bruteforce.yml`

## Splunk Query
See:
`Splunk-Queries/rdp_bruteforce.spl`

## Mitigation
- Restrict public RDP exposure
- Enable MFA
- Apply account lockout policy
- Monitor failed authentication attempts

## Lessons Learned
RDP remains one of the most targeted remote access services in enterprise environments.
