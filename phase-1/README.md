# 🚨 Phase 1: Cybersecurity Internship – Blue Team Detection & Log Analysis

This repository documents my hands-on work in **Phase 1 of the Cybersecurity Internship at Srida IT Consulting & Services (OPC) Pvt Ltd**, under the guidance of Rajendra Bodda.

In this phase, I worked through real-world SOC-level detection scenarios. Each scenario reflects practical blue team concepts like log analysis, exploitation detection, and endpoint behavior monitoring. I didn’t just simulate attacks—I broke down **how they appear in logs**, what they mean from a defender’s perspective, and **how to detect them.**

---

## 🔍 What You'll Find in This Repository

✅ **8 Detection Hints Covered** (based on real-world SOC tasks):  
- Brute force attacks  
- Malware simulation  
- Unauthorized access attempts  
- Suspicious network activity  
- File download monitoring  
- Privilege escalation  
- Phishing email detection  
- Command & Control (C2) traffic

---

### ✅ Phase 1 Detection Scenarios

**Hint 1: Brute Force Detection**  
Simulated password brute-forcing via SMB using Hydra. Mapped failures to **Event ID 4625**, showing how login failures from the same IP are caught in a SIEM.

**Hint 2: Malware Detection**  
Analyzed malware using VirusTotal, PEStudio, and any.run. Explored file execution and process creation patterns logged via Sysmon (Event ID 1, 11).

**Hint 4: Suspicious Network Activity**  
Performed network reconnaissance using Nmap. Focused on detecting abnormal port scanning patterns with **Sysmon Event ID 3**.

**Hint 5: Phishing Email Detection**  
Reviewed phishing scenarios using TryHackMe labs. Parsed headers, evaluated attachments, and identified spoofed domains and malicious links.

**Hint 6: Unauthorized Access Attempt**  
Captured failed SMB login attempts using Metasploit. Explained detection via **Windows Security Log 4625**, and how defenders identify external probing.

**Hint 7: Suspicious File Download**  
Simulated a payload drop using Metasploit. Mapped file creation to **Event ID 11**, followed by execution via Event ID 1.

**Hint 8: Privilege Escalation**  
Gained SYSTEM-level access using exploitation techniques. Focused on identifying **Event ID 4672** and behaviors linked to privilege abuse.

**Hint 10: Command & Control (C2) Detection**  
Used Meterpreter reverse shells to simulate C2 traffic. Explained beaconing and remote control via outbound traffic on uncommon ports.

---

### 🧰 Tools and Techniques Used

- **Hydra, SMBClient, Nmap** – Simulated brute force and recon
- **Sysmon, Event Viewer, Winlogbeat** – Collected and analyzed logs
- **Metasploit** – Delivered and executed payloads
- **VirusTotal, any.run, PEStudio** – Analyzed file and process behavior
- **Netcat** – Used for simulated data exfiltration
- **Markdown + GitHub** – Wrote structured reports for each detection scenario

---

### 💡 Key SOC/Blue Team Skills Gained

- Identified attacker activity using Event IDs and log correlation
- Simulated real-world incidents in a lab using safe tools
- Learned detection engineering fundamentals
- Documented all tasks clearly with screenshots and analysis
