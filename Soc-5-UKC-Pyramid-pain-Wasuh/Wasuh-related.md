WAZUH
==================

NIST, SCA, MITRE


windows tool for log collection:


Task 4:
vulnerability assessment
Scan interval

Task 5: 

| Term         | Category           | Purpose                         |
| ------------ | ------------------ | ------------------------------- |
| NIST         | Security Standards | Improve cybersecurity practices |
| SCA          | Security Testing   | Detect vulnerable dependencies  |
| GDPR         | Privacy Law        | Protect personal data           |
| MITRE ATT&CK | Threat Framework   | Understand attacker behavior    |






- PCI DSS
- SCA  - Security Configuration Assessment
- NIST
- GDPR

Task 6:
can detect successful and unsuccessful logs

pre-defined rules:
rule ID: 5710, 5501

Wazuh -> management -> Rules 
view, search , modify rules

Raw event logs are stored in: /var/ossec/logs/alerts/alerts.log


Task 7: Collecting windows logs
windows events:
authentication attempts,
networking connections,
files that were accessed,
behaviours of applications and services.

This information is stored in the Windows event log using a tool called sysmon.

* sysmon rules are in xml formate

Task 8 : 
Linux logs Collections
Apache2 web server



Task 9 :
- auditd

Normal logs give high-level system events, while auditd provides detailed, low-level visibility of user actions and commands.

auditd works at the kernel level, so it can log things like:

Every command executed (execve)
Who ran it (user ID, including root)
File access (read/write)
Privileged actions
System calls

 Monitoring the usage of tcpdump, netcat important because they are commonly used by attackers
 
 
 Task 10: Wazuh API
 
 wazuh allow api to alow interact with commandline

Wazuh management server requires authentication frist

here we are using curl to interact with wazuh management server api
authenticate endpoint -> server give a token -> we can store token as an envrironment variable on linux machine


- api console

Task 11: Generating Reports with Wazuh

Convert large amounts of logs into a clear summary
Understand security activity (alerts, attacks, trends)
Investigate incidents (what happened, when, where)
Share information with teams, managers, or clients
Maintain records for auditing and compliance
Support decision-making to improve security

👉 In short:
Wazuh reports turn raw logs into meaningful insights that are easy to read and share.




Task 12: Loading Sample data
for :
avoid empty dashboard,
practical analysis,
Test Features
Demonstrate Wazuh Capabilities

Sample data = training dataset for your SIEM




