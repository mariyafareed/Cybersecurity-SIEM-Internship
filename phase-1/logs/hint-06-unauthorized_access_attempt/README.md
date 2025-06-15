
# Hint 6: Unauthorized Access Attempt

### ✅ Room
[TryHackMe: Blue](https://tryhackme.com/room/blue)

---

### 🧪 What Happened
Before exploiting the target, the attacker interacted with the SMB service (port 445) using Metasploit. This simulates unauthorized access attempts and could involve password guessing or login probes.

---

### 🧠 What Would Be Logged
- **Windows Event ID 4625**: Failed logon attempt
- **Logon Type**: 3 (network-based)
- **Status Code**: 0xC000006D (bad credentials)

Even if the login succeeded later, the failed attempts would generate alerts.

---

### 📸 Screenshot
![SMB login attempt](../screenshots/hint6_smb_login_attempt.png)

---

### 💡 Learning Outcome
SMB logins, especially with invalid credentials, are highly detectable using Event ID 4625. Correlating repeated attempts from a single IP is a key technique for spotting brute-force attacks.
