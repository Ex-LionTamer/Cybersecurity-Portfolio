# PowerShell IOC Collection

## Suspicious Processes
- powershell.exe
- pwsh.exe

## Suspicious Command Arguments
- EncodedCommand
- FromBase64String
- Invoke-Expression
- IEX

## Common ATT&CK Technique
- T1059.001 — PowerShell

## Detection Opportunities
- Sysmon Event ID 1
- PowerShell Script Block Logging
- Windows Security Event Logs
