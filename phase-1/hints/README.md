**Completed Hint Reports**

1. Brute Force Detection

Tools Used: Hydra, SMBClient

Logs Expected: Event ID 4625 (Failed login), Logon Type 3

Room Used: TryHackMe: Blue

2. Malware Detection

Tools Used: VirusTotal, any.run, PEStudio

Logs Expected: Sysmon Event ID 1 (Process Create), ID 11 (File Create)

Room Used: TryHackMe: Malware Analysis Introduction

4. Suspicious Network Activity

Tools Used: Nmap

Logs Expected: Sysmon Event ID 3 (Network Connections)

Room Used: TryHackMe: Blue

5. Phishing Email Detection

Tools Used: Email header analysis, TryHackMe content

Indicators: Mismatched domains, .exe attachments, malicious URLs

Room Used: TryHackMe: Phishing

6. Unauthorized Access Attempt

Tools Used: Metasploit (SMB), SMBClient

Logs Expected: Event ID 4625 (Failed login), Logon Type 3

Room Used: TryHackMe: Blue

7. Suspicious File Download

Tools Used: Metasploit payload delivery

Logs Expected: Sysmon Event ID 11 (File creation), Event ID 1 (Execution)

Room Used: TryHackMe: Blue

8. Privilege Escalation Attempt

Tools Used: getSystem, SYSTEM shell

Logs Expected: Event ID 4672 (Special privileges), 4720/4732 (if applicable)

Room Used: TryHackMe: Blue

10. Command & Control (C2) Traffic Detection

Tools Used: Metasploit reverse TCP, Cobalt Strike theory

Logs Expected: Event ID 3 (Outbound connection), periodic connections

Room Used: TryHackMe: C2 101
