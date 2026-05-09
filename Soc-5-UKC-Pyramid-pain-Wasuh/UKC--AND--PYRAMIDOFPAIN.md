# Unified Kill Chain Framework (UKC)

* Introduced by = Paul Pols in 2017

* Goal : 
The goal is to find and understand potential security threats and risks to a system 

* its basically a detailed life cycle of a cyber attack.

Unified Kill Chain (UKC) is not just to list attack steps—it’s to help defenders understand, detect, and stop cyber attacks more effectively across their entire lifecycle.

The UKC provides a complete, structured view of how attackers operate, from the very first step (reconnaissance) to the final goal (data theft, disruption, etc.).



# IN (Initial Foothold)

(Attacker gets access and establishes control)

1. Reconnaissance – Gathering information about the target
2. Resource Development – Preparing infrastructure (domains, malware, tools)
3. Delivery – Sending payload (phishing, USB, exploit, etc.)
4. Social Engineering – Manipulating users to trigger the attack
5. Exploitation – Exploiting vulnerabilities to gain access
6. Persistence – Maintaining access after initial compromise
7. Defense Evasion – Avoiding detection (obfuscation, disabling logs)
8. Command and Control (C2) – Establishing communication with attacker server

# THROUGH (Network Propagation)

(Attacker moves inside the network)

9. Discovery – Exploring internal systems and network
10. Privilege Escalation – Gaining higher-level permissions
11. Credential Access – Stealing usernames/passwords
12. Execution – Running malicious code on systems
13. Lateral Movement – Moving between machines
14. Pivoting – Using one system to reach another network/system

# OUT (Action on Objectives)

(Attacker achieves the goal)

15. Collection – Gathering sensitive data
16. Exfiltration – Transferring data out of the network
17. Impact – Causing damage (ransomware, deletion, disruption)
18. Objectives – Final goal achieved (espionage, financial gain, etc.)


















-----------------------------------------------------------------












The Pyramid of Pain is a cybersecurity model created by David Bianco.

* It explains how difficult it is for attackers to change different types of indicators when defenders detect them.
* Ranking them based on how much it hurts the hacker to change them.
# Core Idea (Very Important)
👉 The higher you go in the pyramid, the more pain you cause the attacker.


# Levels of the Pyramid 
7. TTP (Tough)
6. Tools (Challenging)
5. Host Artifacts (Annoying)
4. Network Artifacts (Annoying)
3. Domain Names (Simple)
2. IP Address (Easy)
1. Hash Value (Trivial)
-----------------------------------------------------------
# TTP 
Tactic = aim
Technique = Method
Procedure = Steps

👉 Tactic: Initial Access
👉 Technique: Exploitation of SIM/telecom vulnerability
👉 Procedure: Simjacker attack using binary SMS

Tactic = The Plan (attacker’s goal)
Technique = HOW (general method)
Procedure = EXACT ACTION (real-world execution)
--------------------------------------------------------------






--------------------------------------------------------------
First: Understand the 3 Levels (simple truth)
# 1. TACTIC = WHY (goal / intent)

Examples of Tactics:
Initial Access
Execution
Persistence
Privilege Escalation
Credential Access
Lateral Movement
Defense Evasion
Exfiltration
Command & Control
# 2. TECHNIQUE = HOW (general method)
Examples:
Phishing
Valid Accounts
PowerShell execution
Process Injection
Registry persistence
RDP lateral movement
LSASS credential dumping
HTTPS C2 communication

👉 Technique = method type

# 3. PROCEDURE = EXACT HOW (real attack story)
Specific actions
Sequence
Tools used
Flow of attack

👉 Procedure = real-world timeline of attack









