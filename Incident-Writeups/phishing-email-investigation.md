# Phishing Email Investigation

## Summary
This project demonstrates a basic phishing investigation workflow focusing on suspicious email behavior and malicious execution attempts.

## Scenario
A user received a suspicious email attachment disguised as an invoice document. After opening the attachment, Microsoft Outlook spawned unexpected child processes.

## Threat Description
Phishing attacks commonly attempt to:
- steal credentials
- deliver malware
- establish persistence
- initiate ransomware attacks

## MITRE ATT&CK

| Technique | Description |
|---|---|
| T1566 | Phishing |
| T1204 | User Execution |
| T1059 | Command Execution |

## Indicators of Compromise (IOC)

### Suspicious Processes
- outlook.exe
- cmd.exe
- powershell.exe

### Suspicious Behavior
- Outlook spawning command shell
- PowerShell execution after email open
- Suspicious attachment execution

## Detection Logic
Detect Microsoft Outlook spawning suspicious child processes such as:
- cmd.exe
- powershell.exe
- wscript.exe

## Example Attack Flow

1. User receives phishing email
2. User opens malicious attachment
3. Outlook launches child process
4. Payload execution begins

## Potential Impact
Successful phishing attacks may result in:
- credential theft
- malware infection
- ransomware deployment
- lateral movement

## Sigma Rule
See:
`Sigma-Rules/suspicious_outlook_child_process.yml`

## Splunk Query
See:
`Splunk-Queries/suspicious_outlook_child_process.spl`

## Mitigation
- Security awareness training
- Email attachment sandboxing
- Block Office child processes
- Monitor suspicious process chains

## Lessons Learned
Phishing remains one of the most effective initial access techniques due to human interaction and trust abuse.
