2. 🛡 Vulnerability Assessment & Penetration Testing (VA/PT)
Scenario: Use Nessus, Nikto, or Nmap for enumeration & VA.
Hint Example: Vulnerability scan simulation.
✅ Room: Vulnerability Assessment
→ Use OpenVAS/Nessus, identify real vulnerabilities, and assess scan detection.

The OpenVAS room introduces you to practical vulnerability assessment using one of the most widely used open-source tools—OpenVAS/GVM (Greenbone Vulnerability Manager). You’ll start by setting up and configuring the scanner, learning how it integrates into a vulnerability management pipeline, and using it to scan both local and remote targets. The exercises guide you through creating scan tasks, exploring scan architecture, and understanding plugin families for identifying misconfigurations and exploitable software flaws. After scanning, you interpret the results in detail—identifying how many ports are open, the number and severity of vulnerabilities (even tracing back to Windows-specific issues like MS17-010), and how to prioritize findings based on CVSS scoring. You’ll also practice creating alerts and monitoring for changes, which helps with ongoing vulnerability management. Finally, the room wraps up with real-world reporting tips and emphasizes continual scanning and remediation practices. 
WHAT I HAVE LEARNED:
Installing and configuring OpenVAS (on Kali/VM or THM cloud environment).

Creating scan tasks: Set scope (local vs remote), configure schedules, and launch baseline scans.

Understanding scanning output: Analyze open ports, detected CVEs (e.g., MS17-010), and severity tiers.

Prioritizing vulnerabilities: Apply CVSS scoring and business context to classify risks.

Reporting & remediation planning: Craft scan reports, generate alerts, and recommend next steps.

Continuous scanning best practices: Learn about repeat scans, monitoring setups, and patch validation.

