Scenario 2: Lateral Movement via RDP Brute Force – Low-privilege user brute-forces RDP across servers using stolen credentials
Room Used: TryHackMe – Lateral Movement
Link: https://tryhackme.com/room/lateralmovement

Objective:
The goal of this room was to understand how attackers use stolen credentials to move laterally within a network using Remote Desktop Protocol (RDP). The scenario focused on brute-forcing RDP login attempts from one compromised host to others and identifying such behavior using Windows Event Logs and detection tools.

What I Did:

Simulated an attacker with low-privilege credentials attempting RDP brute-force attacks across different Windows machines.

Used tools like hydra and crackmapexec to perform login attempts on RDP service (port 3389).

Investigated RDP login success/failure events (Event ID 4624, 4625) on the victim system.

Monitored network activity and Windows logs for patterns such as failed login storms, unusual login hours, and login attempts from non-administrative accounts.

Detection Strategy:

Used Sysmon and Windows Event Viewer to monitor:

Event ID 4625: Failed login attempts

Event ID 4624: Successful login after multiple failures

Identified brute-force attempts by filtering logs for high-frequency 4625 events from a single IP or user account.

Used Sigma rule to detect multiple failed RDP login attempts in a short time window.

Verified lateral movement by observing login sessions using:


Hydra

CrackMapExec

Sysmon

Event Viewer

Sigma + ELK Stack for log correlation and detection

Conclusion:
This room clearly illustrated how lateral movement via RDP brute-force attacks is carried out using legitimate credentials. Detecting such activity relies on correlating logon failures, login timings, and account behavior across systems. By analyzing authentication events and writing detection rules for failed login patterns, I improved my ability to detect and respond to brute-force-based lateral movement techniques.

