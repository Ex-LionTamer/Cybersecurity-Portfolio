# Detecting Suspicious PowerShell EncodedCommand Activity

## Summary
This project demonstrates how suspicious PowerShell activity using EncodedCommand can be detected through process creation logs and detection engineering techniques.

## Threat Description
Attackers frequently abuse PowerShell with Base64 encoded commands to evade detection and execute malicious payloads.

This technique is commonly used in:
- Malware execution
- Initial access payloads
- Post-exploitation
- Living off the Land (LotL) attacks

## MITRE ATT&CK
| Technique | Description |
|---|---|
| T1059.001 | PowerShell |

## Indicators of Compromise (IOC)

### Process
- powershell.exe

### Suspicious Arguments
- EncodedCommand
- FromBase64String
- IEX

## Detection Logic
Detect PowerShell execution containing:
- EncodedCommand
- suspicious Base64 usage

## Example Suspicious Command

```powershell
powershell.exe -EncodedCommand SQBmACgA...
```

## Potential Impact
Successful abuse of PowerShell may allow attackers to:
- execute arbitrary commands
- download malware
- establish persistence
- perform lateral movement

## Detection Opportunities
- Process creation logs
- PowerShell logging
- Sysmon Event ID 1
- Command-line auditing

## Sigma Rule
See:
`Sigma-Rules/suspicious_powershell.yml`

## Splunk Query
See:
`Splunk-Queries/suspicious_powershell.spl`

## Mitigation
- Restrict unnecessary PowerShell usage
- Enable PowerShell logging
- Use constrained language mode
- Monitor suspicious child processes

## Lessons Learned
PowerShell remains one of the most abused Windows utilities in modern attacks due to its flexibility and native availability.
