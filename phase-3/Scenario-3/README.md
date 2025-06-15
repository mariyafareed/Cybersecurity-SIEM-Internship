Scenario 3: Persistence via Registry Run Keys – Script added to registry key for persistence
Room Used: TryHackMe – Registry Persistence Detection
Link: https://tryhackme.com/room/registrypersistencedetection 
tryhackme.com

Objective:
Understand how attackers inject malicious entries into Windows Registry Run keys (HKCU or HKLM) to maintain persistence across reboots, and learn how to detect and remediate these entries.

🛠 What I Did:
Explored how malware abuses:
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run  
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run
Used reg add and a .bat file to simulate persistence:

powershell
reg add HKLM\Software\Microsoft\Windows\CurrentVersion\Run /v Updater /t REG_SZ /d "C:\malicious.bat"
Powered through Task‑based labs:

Found the suspicious (Default) entry and traced its data path (e.g., C:\Users\Administrator\AppData\Local\bd84\24d9.bat)

Observed console message: “pleaseletmepersist” 


Used the AutoRuns PowerShell module to scan and baseline autorun entries:

Get-PSAutorun → retrieved all startup entries

New-AutoRunsBaseLine → snapshot before infection

Compare-AutoRunsBaseLine → diff new changes 


🔍 Detection Strategy:
Used Sysmon Event ID 13 to log registry value modifications.

Employed Autoruns / Get-PSAutorun to detect new Run‑key entries.

Created Sigma rule:
detection:
  selection:
    EventID: 13
    TargetObject|contains: '\\Run'
    Details|contains: '.bat'
  condition: selection
Validated persistence by testing system reboot and confirming malware execution at startup.

🧰 Tools Used:
Sysmon

AutoRuns PowerShell Module

Windows Registry (reg.exe)

Event Viewer / Winlogbeat

Sigma + ELK Stack (for alerting)

✅ Conclusion:
This room clearly demonstrates how simple registry Run key modifications can invisibly provide persistence for attackers. By simulating the attack and using Sysmon’s registry monitoring, along with baseline comparisons via AutoRuns, I practiced detecting and remediating this stealthy APT technique—perfect for inclusion in a threat-hunting portfolio.

