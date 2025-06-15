🚀 Cybersecurity Internship at Srida IT Consulting & Services (OPC) Pvt Ltd

📌 Overview  
This repository documents my hands-on journey through **Phase 3: Advanced Threat Hunting & APT Simulation** of the Cybersecurity Internship at Srida IT Consulting & Services (OPC) Pvt Ltd, under the guidance of Rajendra Bodda.

In this phase, I worked on realistic APT-style scenarios that mimic nation-state threat actor behavior. Each scenario focused on learning how attackers execute multi-stage attacks and how defenders can detect them using Windows telemetry, SIEM, and network analysis tools. I’ve tried to break down each simulation in a simplified and understandable way—not just how I did it, but why each step matters for Blue Teamers and Threat Hunters.

🔍 What You'll Find in This Repository  
✅ **Realistic Attack Scenarios Covered:**  
- **Scenario 1: Fileless Malware via PowerShell** – Simulated a phishing attack leading to remote execution of an obfuscated PowerShell payload.  
- **Scenario 2: Lateral Movement via RDP Brute Force** – Used compromised credentials to brute-force RDP and move laterally across machines.  
- **Scenario 3: Persistence via Registry Run Keys** – Created registry-based persistence using `HKCU\Software\Microsoft\Windows\CurrentVersion\Run`.  
- **Scenario 4: DNS Tunneling** – Performed covert data exfiltration by encoding data into subdomain queries.  
- **Scenario 5: Credential Dumping and Exfiltration** – Dumped credentials from LSASS using Mimikatz and simulated secure exfil over HTTPS.

✅ **Tools and Techniques I Used:**  
- **Sysmon** – Monitored event IDs like 1, 3, and 10 to track command-line usage, network connections, and memory access.  
- **Winlogbeat** – Sent logs to the ELK stack for centralized log analysis.  
- **ELK Stack (Elasticsearch, Logstash, Kibana)** – Created dashboards and detection queries for each scenario.  
- **Sigma Rules** – Wrote detection logic to identify attacker techniques from log events.  
- **Suricata / Zeek** – Used for network-level threat detection like DNS tunneling and HTTPS exfiltration.

✅ **Detection Engineering & Blue Team Skills Gained:**  
- Correlated Windows logs with network activity  
- Wrote custom detection rules for attacker behavior  
- Practiced real-world incident investigation workflows  
- Gained confidence in using ELK for threat hunting  
- Learned how APTs hide in plain sight using fileless and stealthy techniques

💻 Lab Setup  
- Virtual Machines running Windows 10, Kali Linux, and Ubuntu  
- Tools like Metasploit, Mimikatz, PowerView, Sysmon, and ELK Stack  
- Logged everything using Winlogbeat and Sysmon  
- Simulated real attacks and observed their behavior in logs

🙏 Acknowledgements  
Huge thanks to **Rajendra Bodda** sir for the guidance and opportunity to learn hands-on threat detection and response in a practical, lab-driven way.

📖 Why I Created This Repo  
I wanted to keep this as a public documentation of what I’ve learned, both for my own reference and for anyone who wants to get into Blue Teaming. Every scenario is written in a beginner-friendly way so others can learn too. If you find something useful, feel free to fork or drop feedback!

🛡️ Hashtags  
#Cybersecurity #BlueTeam #ThreatHunting #SIEM #WindowsLogs #Sysmon #APT #DetectionEngineering #Internship #ELKStack #SigmaRules #ThreatIntel

