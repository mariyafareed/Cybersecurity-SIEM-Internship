Scenario 3: Network Traffic Analysis
TryHackMe Room: Zeek

In this scenario, I focused on analyzing network traffic to detect command and control (C2) activity, beaconing, and suspicious data exfiltration using the Zeek TryHackMe room. Zeek (formerly known as Bro) is a powerful network monitoring tool that passively inspects packets and creates structured logs for further investigation. This room helped me understand how to analyze conn.log, dns.log, http.log, and other protocol-specific logs to detect abnormal behavior.

I started by analyzing DNS tunneling traffic. Using zeek -C -r dns-tunneling.pcap, I was able to generate Zeek logs and dive into the dns.log file to identify suspicious DNS queries and potential data exfiltration attempts. I paid close attention to high-frequency AAAA queries, which is often a sign of tunneling. Then, I moved on to conn.log, which helped me spot long-lasting connections—an important indicator for beaconing behavior.

Next, I worked through the phishing and malware section. Zeek’s http.log and files.log provided detailed insight into HTTP GET and POST requests. I analyzed user-agent strings and downloaded file names to identify malicious files. In one challenge, I identified a phishing link by correlating suspicious domains with HTTP activity. I also learned how to extract file hashes and track where and when these files were downloaded.

The final part of the room covered exploitation traffic, specifically Log4Shell. I used Zeek to detect scanning attempts based on user-agent strings like Nmap and payload patterns in the URI. I even applied a custom detection script that helped flag exploit attempts across the logs.

This scenario gave me a solid understanding of network-level threat detection using real PCAPs and structured logs. I can now identify patterns related to C2 activity, phishing, DNS abuse, and post-exploitation behavior. These skills are directly applicable to real-world SOC tasks and help in building detection rules for SIEM and IDS systems.
