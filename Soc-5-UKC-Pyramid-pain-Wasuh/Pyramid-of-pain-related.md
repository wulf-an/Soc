

IDN homograph / Punycode attack


# Task 5 : Host Artifacts (Annoying)
Suspicious processes
Unusual parent-child process relationships
Dropped/created files
Hidden or temporary files
Registry key modifications
Autorun entries
Scheduled tasks
Startup folder entries
New or modified services
System log entries (authentication, privilege changes)
Failed/successful login events
New user account creation
LSASS access / credential dumping traces
Process execution chains
Command-line execution history
PowerShell execution logs
Firewall rule changes
Security configuration changes
Tool execution traces (e.g., Mimikatz)

# Task 6 : Network Artifacts (Annoying)

- network artifact can be:
user-agent string
C2 information
URI patterns followed by the HTTP POST requests.



- Network Artifacts – List
DNS queries (suspicious domains)
HTTP/HTTPS requests
URL patterns
User-Agent strings
Beaconing traffic (regular intervals)
C2 communication patterns
Unusual outbound connections
Suspicious ports and protocols
TLS/SSL certificate details
Proxy logs
NetFlow data
Packet capture (PCAP) indicators
Domain resolution patterns
Data exfiltration traffic patterns
Unusual data transfer volumes
Repeated connection attempts
Encoded or obfuscated network traffic
Suspicious API calls over network


# Task 7 Tools (Challenging)
malicious macros, backdoors, custom executables, DLLs, payloads, or password crackers, 

Antivirus signatures, detection rules, and YARA rules can be great weapons for you to use against attackers at this stage.

MalwareBazaar  (opens in new tab)and Malshare  (opens in new tab)are good resources to provide you with access to the samples, malicious feeds, and YARA results 

fuzzy hashes - also know as (CTPH) Context Triggered Piecewise Hashes
ssdeep = ssdeep is a tool used to create fuzzy hashes
https://ssdeep-project.github.io/ssdeep/index.html



# Task 8 TTP (Tough)

Tactics → attacker’s goal (e.g., steal data)
Techniques → how they do it (e.g., phishing, credential dumping)
Procedures → exact steps they follow

Tool = weapon (e.g., malware)
TTP = fighting style
-----------------------------------------------
- LSASS = Local Security Authority Subsystem Service
Plaintext passwords (sometimes)
NTLM password hashes
Kerberos tickets
-------------------------------------------------
- Pass-the-Hash Attack (PtH)
Attacker steals the hash
That hash is used for authentication
Common in Windows environments
-----------------------------------------
- what is a Kerberos ticket
In Kerberos:

When you log in, the system gives you a ticket (like a digital pass)
This ticket proves your identity to other services
You don’t need to enter your password again

👉 The most important one:
- TGT (Ticket Granting Ticket)
-------------------------------------------------
- Pass-the-Ticket (PtT)
  👉 An attacker steals a Kerberos authentication ticket and reuses it to access systems
❌ Without needing the user’s password or hash
-------------------------------------------------

MITRE ATT&CK Matrix , which means all the steps taken by an adversary to achieve his goal = https://attack.mitre.org/

For mobile: https://attack.mitre.org/matrices/mobile/


# Task 10 - Conclusion

From David Bianco:

“The amount of pain you cause an adversary depends on the types of indicators you use”

f you detect only hashes → attacker doesn’t care 😄
If you detect their behavior → attacker struggles 😖

- Strong detection (high pain)
Detect behavior
Detect techniques
Detect TTPs



https://docs.rapid7.com/insightidr/apt-groups/
