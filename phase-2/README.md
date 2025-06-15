In this phase, I worked on real-world SOC analyst tasks focusing on SIEM log analysis, vulnerability assessment, network traffic analysis, incident simulation, and security documentation. The goal was to bridge the gap between tools and techniques used in blue teaming and how they're applied in a live security operations environment. I've broken each scenario down in a simple, hands-on way—not just what I did, but why it matters.

🔍 What You'll Find in This Repository
✅ Blue Team Scenarios Covered:

Scenario 1: SIEM Log Analysis (Advanced) – Analyzed logs from Sysmon, Winlogbeat, Filebeat, and Auditbeat to detect malicious PowerShell usage, credential dumping, and privilege escalation attempts.

Scenario 2: Vulnerability Assessment & Penetration Testing (VA/PT) – Conducted system scans using OpenVAS, Nmap, and Nikto, identified known vulnerabilities, and documented them with CVSS-based prioritization.

Scenario 3: Network Traffic Analysis – Used Zeek to investigate packet captures, identified beaconing patterns, DNS tunneling, and suspicious HTTP requests using structured logs.

Scenario 4: Hands-on Incident Simulation – Simulated real-world attacks like reverse shells, PowerShell malware, and miner installations. Followed the incident response lifecycle: detection, containment, eradication.

Scenario 5: Security Documentation & Reporting – Documented investigation findings, timelines, affected assets, and recommendations. Wrote audit-ready reports and executive summaries based on incidents.

✅ Tools and Techniques I Used:

Sysmon + Winlogbeat – Collected and forwarded endpoint logs for event correlation.

Zeek – Performed passive traffic inspection and log generation for anomaly detection.

OpenVAS / Nmap / Nikto – Ran system and web app scans to identify vulnerabilities.

PowerShell + CertUtil + Netcat – Simulated attacker behavior for incident simulation.

Windows Event Viewer / wevtutil / Get-WinEvent – Extracted and analyzed Event IDs like 4104, 800, 4624, and 4728.

Excel & Markdown – Used to build structured reports and summarize incident timelines.

✅ Blue Team & SOC Skills Gained:

Identified indicators of compromise (IOCs) from logs

Understood attacker behavior through log analysis

Correlated SIEM, system, and network-level data

Conducted basic vulnerability assessments

Wrote clear and professional incident documentation

Followed the NIST/SANS IR lifecycle in simulations


