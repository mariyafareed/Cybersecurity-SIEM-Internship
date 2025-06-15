Scenario 4: Hands-on Incident Simulation
TryHackMe Room: Incident Response Process

In this scenario, I focused on simulating and investigating a real-world security incident by working through the Incident Response Process room on TryHackMe. This room guided me through the key phases of incident response based on the SANS/NIST framework—Detection, Analysis, Containment, and Eradication. The challenge revolved around investigating a malware infection involving a malicious macro-laced Word document, miner execution, and outbound C2 traffic.

I started with the detection phase, where I triaged alerts and identified a suspicious executable named 32th4ckm3.exe, which was related to a coinminer. I also detected a suspicious outbound connection from the infected machine to a C2 server IP (45.33.32.156:42424). Windows Defender and logs helped me confirm the activity and extract initial indicators of compromise (IOCs).

Next, I analyzed the malicious behavior on the host. A Word document with embedded macros triggered PowerShell, which in turn downloaded a binary using certutil.exe—a classic living-off-the-land (LOLBAS) technique. This behavior was evident from the Windows Event Logs and PowerShell logs. I checked the registry for persistence mechanisms and found a registry autorun entry that ensured the malware ran every time the system booted.

In the containment phase, I applied network isolation steps—such as disabling internet access for the compromised host—to stop further communication with the attacker's C2 server. This ensured that the miner couldn’t exfiltrate data or receive further instructions.

Finally, I moved on to eradication. I removed the malicious registry entries, deleted the miner binary from the system, and cleared the macro-infected document. I documented the entire incident workflow, including how the attack started, how it was detected, and the steps taken to remove the threat completely.

This room gave me hands-on experience in simulating real attack scenarios including malware execution, reverse shells, C2 detection, and post-exploitation cleanup. It also strengthened my skills in identifying attack vectors, analyzing host behavior, and applying structured incident response methodologies. These are essential skills for any SOC analyst or blue teamer working in active environments.
