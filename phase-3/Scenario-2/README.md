🎯 Objective
Simulate an attacker using a low-privilege account to brute-force RDP access across internal Windows hosts, then detect this activity in logs.

🛠 What I Did
Configured a target Windows VM with RDP enabled.

Loaded Hydra room materials and practiced brute-forcing techniques.

Ran Hydra against the RDP service:

nginx

hydra -l user -P wordlist.txt rdp://<target-ip>
Attempted several password combinations to simulate brute-force.

Used enumeration room concepts to track and analyze login attempts and results.

🔍 Detection Strategy
Monitored Windows Event Logs:

Event ID 4625 – multiple failed RDP login attempts.

Event ID 4624 – successful login after failed attempts.

Used Sysmon to log network connections and process creations.

Correlated log entries in ELK Stack:

Filtered for 4625 events by source IP and user.

Built Sigma rule to detect burst of failed RDP attempts:

detection:
  selection:
    EventID: 4625
    LogonType: 10
  timeframe: last 5m
  condition: count(selection) > 5
Confirmed lateral movement via queries:

quser
whoami /all
🧰 Tools Used
Hydra

Sysmon + Winlogbeat

ELK Stack (Kibana dashboards)

Sigma Rules

Windows Event Viewer

📝 Conclusion
By combining Hydra’s brute-force capability with the enumeration room’s principles, I accurately simulated an RDP lateral movement scenario. Detection became possible through correlation of multiple failed RDP logins (Event 4625) followed by a successful authentication (Event 4624), sourced from the same IP/account. This exercise strengthened skills in log-based anomaly detection and lateral movement identification via brute-force.
