Scenario 4: DNS Tunneling – Data exfiltration via encoded DNS subdomain queries
Room Used: TryHackMe – DNS Manipulation
Link: https://tryhackme.com/room/dnsmanipulation 
Objective:
Learn how attackers use DNS queries—not just for resolution, but as covert channels to exfiltrate data by encoding information into subdomains. This technique is stealthy, often bypassing network security appliances.

🛠 What I Did:
Completed labs demonstrating DNS data exfiltration by embedding Base64-encoded payloads in DNS queries.

Simulated a DNS tunneling setup using tools like Iodine (though primarily theoretical in this room).

Used Wireshark to inspect DNS traffic and spot suspicious queries with long subdomain strings.

Found and analyzed in-built PCAP files (“dns.pcap”) containing encoded DNS traffic and connected it back to dataexfil.com.

Learned how to use Zeek (formerly Bro) and Suricata to log DNS activity and detect anomalies based on query length and frequency.

🔍 Detection Strategy:
Filtered for DNS queries longer than normal (dns.qry.name.len > 15) to identify possible tunneling.

Used Zeek’s dns.log to analyze query patterns.

Checked for entropy or Base64 patterns inside DNS names to detect encoded data.

Created a basic detection concept (Sigma-like):

selection:
  dns_query_length: '>63'
  subdomain_pattern: /[A-Za-z0-9+/]{20,}\.[A-Za-z]+\.[A-Za-z]{2,4}/
condition: selection
Cross-referenced DNS anomalies in ELK Stack dashboards, pointing out suspicious hosts and subdomains.

🧰 Tools Used:
Wireshark (for packet inspection)

Zeek (dns.log analysis)

Suricata (DNS anomaly detection)

Optional: Iodine (practical tunneling tool)

Sigma-style detection logic in ELK/Kibana

✅ Conclusion:
Although the room wasn’t labeled “DNS Tunneling,” it perfectly demonstrates how attackers use DNS as a covert channel. By analyzing logs, packet captures, and DNS query characteristics, I built a strong defense strategy involving query-length filtering, entropy detection, and SIEM correlation. This knowledge is essential for identifying stealthy APT exfiltration techniques.
