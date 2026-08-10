## what is soc 
SOC (Security Operations Center) is a team of cybersecurity professionals that monitors, detects, investigates, and responds to cyber threats 24/7 to keep an organization's systems and data safe.



### Key Responsibilities of a SOC

​Monitoring & Detection: Scanning network traffic, logs, and endpoints 24/7/365 to catch suspicious activity. 

​Incident Response: Reacting swiftly to contain and eliminate threats (like malware infections, phishing attacks, or unauthorized access). 

​Threat Hunting: Proactively searching through systems to find hidden vulnerabilities or threats that bypassed initial security controls. 

​Log & Data Analysis: Collecting and analyzing data from various sources (using tools like SIEM) to track system health and detect security anomalies. 

​Recovery & Remediation: Restoring compromised systems and learning from incidents to strengthen future defenses.



## SOC operational models:

Dedicated (In-house) SOC – The organization builds and manages its own SOC with internal security staff.

Virtual SOC (vSOC) – A remote SOC where analysts work from different locations using secure connections.

Co-managed (Hybrid) SOC – Security operations are shared between the organization's internal team and an external security provider.

Outsourced (Managed) SOC – A third-party provider (MSSP) handles the organization's SOC operations and 24/7 monitoring.

Multi-Tenant SOC – One SOC monitors and protects multiple organizations while keeping each customer's environment separate.


## core functions of a  (SOC):

Monitoring – Continuously monitor networks, systems, and security tools for suspicious activity.

Threat Detection – Identify potential cyber threats, attacks, or security incidents.

Alert Triage – Review and prioritize security alerts based on their severity and impact.

Incident Investigation – Analyze alerts to determine whether they are real threats and understand what happened.

Incident Response – Contain, eradicate, and recover from confirmed security incidents.

Threat Hunting – Proactively search for hidden threats that automated tools may have missed.

Vulnerability Management – Identify, assess, and help remediate security weaknesses in systems.

Log Management & Analysis – Collect, store, and analyze logs from various systems to detect suspicious behavior.

Reporting & Documentation – Document incidents, create reports, and provide recommendations to improve security.

Continuous Improvement – Update detection rules, improve processes, and strengthen defenses based on lessons learned from incidents.


## SOC Team Roles & Responsibilities ##


L1 SOC Analyst – Monitor and triage alerts.

L2 SOC Analyst – Investigate and respond.

L3 SOC Analyst – Handle advanced threats and threat hunting.

SOC Manager – Lead the SOC team.

Threat Hunter – Search for hidden threats.

Threat Intelligence Analyst – Research emerging threats.

Incident Responder – Contain and recover from incidents.

DFIR Analyst – Perform forensics and incident investigations.

Malware Analyst – Analyze malicious software.

Detection Engineer – Build and improve detection rules.

SIEM/Security Engineer – Maintain SOC tools.

SOC Architect – Design the overall SOC environment.

SOC Manager
      │
      ├── L3 SOC Analyst
      │      ├── Threat Hunter
      │      ├── Malware Analyst
      │      ├── DFIR Analyst
      │      └── Detection Engineer
      │
      ├── L2 SOC Analyst
      │      └── Incident Responder
      │
      └── L1 SOC Analyst
      
      
## ## Essential Tools and Technologies  ##


1. Detection & Monitoring Tools

SIEM (Security Information and Event Management): Wazuh, Splunk, IBM QRadar, Microsoft Sentinel, Elastic Security.

EDR (Endpoint Detection and Response): Microsoft Defender for Endpoint, CrowdStrike Falcon, SentinelOne, Sophos Intercept X, VMware Carbon Black.

XDR (Extended Detection and Response): Microsoft Defender XDR, Cortex XDR, Trend Micro Vision One, SentinelOne Singularity XDR.

NDR (Network Detection and Response): Darktrace, Vectra AI, ExtraHop, Cisco Secure Network Analytics.

2. Threat Intelligence Tools
TIP (Threat Intelligence Platform): VirusTotal, MISP, OpenCTI, Recorded Future, AlienVault OTX, Cisco Talos, GreyNoise, AbuseIPDB.

3. Response & Automation Tools
SOAR (Security Orchestration, Automation and Response): Shuffle SOAR, Cortex XSOAR, Splunk SOAR, FortiSOAR, Microsoft Sentinel, Swimlane.

4. Vulnerability Management Tools
VM (Vulnerability Management): Nessus, Qualys VMDR, Rapid7 InsightVM, OpenVAS, Greenbone, Tenable.io.

5. Identity & Access Security
IAM (Identity and Access Management): Microsoft Entra ID, Okta, Ping Identity, OneLogin, ForgeRock.

PAM (Privileged Access Management): CyberArk, BeyondTrust, Delinea, ManageEngine PAM360.

6. AI & Advanced Analytics
AI/ML (Artificial Intelligence & Machine Learning): Darktrace, Vectra AI, Microsoft Defender XDR, CrowdStrike Falcon, Google Chronicle, Elastic AI Assistant.


Appendix:

UEBA : 
UEBA analyzes the normal behavior of users and machines while working with SIEM tools to spot unusual activity that could signal a security threat.      



## Security frameworks and Models 

NIST Cybersecurity Framework
MITRE ATT&CK

Cyber Kill Chain
Unified Kill Chain 
The diamond model of intrusion analysis 
SOC-CMM -- Capability Maturity Model


## SOC Metrics and KPIs


1.-----Detection Metrics-----
Purpose: Measure how effectively the SOC detects security threats.

- MTTD (Mean Time to Detect): Average time taken to detect a security incident.

- Alert Volume: Total number of security alerts received.

- False Positive Rate: Percentage of alerts that are not actual threats.

- Detection Coverage: Percentage of systems, assets, or attack techniques being monitored.

- Threat Detection Rate: Percentage of actual threats successfully detected by the SOC.

2. --------Response Metrics------------
Purpose: Measure how efficiently the SOC responds to security incidents.

- MTTR (Mean Time to Respond): Average time taken to respond to a detected incident.

- MTTC (Mean Time to Contain): Average time taken to isolate or contain a threat.

- Incident Escalation Rate: Percentage of incidents escalated from L1 to L2 or L3 analysts.

- SLA Compliance Rate: Percentage of incidents resolved within the agreed Service Level Agreement (SLA).

- Cases Closed per Analyst: Number of incidents successfully resolved by each SOC analyst.


3. -------Business Impact Metrics-------
Purpose: Measure how SOC performance impacts the organization.

- Cost per Incident: Average cost incurred for handling a security incident.

- Dwell Time Reduction: Reduction in the time attackers remain undetected within the environment.

- Data Breach Prevention Rate: Percentage of potential data breaches successfully prevented.

- Compliance Posture Score: Score indicating how well the organization meets security and regulatory compliance requirements.


## ----- SOC Challenges & Pain Points ----

Purpose: Common challenges that reduce the efficiency and effectiveness of a SOC.

1. Alert Fatigue: Analysts receive too many alerts, making it difficult to identify real threats.

2. Cybersecurity Talent Shortage: Lack of skilled cybersecurity professionals to monitor and respond to incidents.

3. Expanding Attack Surface: More devices, cloud services, and applications create more opportunities for attackers.

4. Tool and Integration Complexity: Managing and integrating multiple security tools can be difficult and time-consuming.

5. Evolving and Sophisticated Threats: Attackers continuously develop new techniques that are harder to detect and stop.

6. False Positives and Low Signal-to-Noise Ratio: Security tools generate many unnecessary alerts, making it harder to identify genuine threats.



## SOC Tier one activity 

                     │
                     ▼
        ┌─────────────────────────┐
        │ 1. ALERT HANDLING       │
        │ Receive + Acknowledge   │
        └────────────┬────────────┘
                     ▼
        ┌─────────────────────────┐
        │ 2. TRIAGE & VALIDATION  │
        │ What happened?          │
        │ Is it really suspicious?│
        └────────────┬────────────┘
                     ▼
        ┌─────────────────────────┐
        │ 3. INVESTIGATION        │
        │ Enrichment              │
        │ Correlation             │
        │ Timeline                │
        └────────────┬────────────┘
                     ▼
        ┌─────────────────────────┐
        │ 4. DECISION             │
        │ FP / TP / Suspicious    │
        │ Severity + Classification│
        └────────────┬────────────┘
                     ▼
        ┌─────────────────────────┐
        │ 5. RESPONSE             │
        │ L1 Action OR Escalate   │
        │ to L2                   │
        └────────────┬────────────┘
                     ▼
        ┌─────────────────────────┐
        │ 6. DOCUMENT & MONITOR   │
        │ Ticket + Evidence       │
        │ Continue Monitoring     │
        └─────────────────────────┘
        
        

## SOC Level Roles and Responsibilities 


Tier 1 Main Responsibilities

Tier 1 is the first line of defense. L1 analysts monitor SIEM dashboards, classify alerts, and escalate suspicious events to higher tiers.

Monitoring — continuous 24/7 SIEM dashboard observation
Alert triage — initial analysis: what happened, where, when
Classification — true positive vs false positive
Documentation — creating and updating tickets
Escalation — passing complex cases to Tier 2
Basic containment — simple actions (e.g., blocking IP in firewall)
Communication — notifying stakeholders per procedures



Required Skills
Technical:

Networking basics (TCP/IP, DNS, HTTP/HTTPS, ports)
Operating systems knowledge (Windows, Linux - basics)
Log reading ability (firewall, proxy, endpoint)
SIEM operation (Splunk, QRadar, Microsoft Sentinel, Elastic)
Malware basics (trojans, ransomware, C2)
MITRE ATT&CK knowledge (basics)




Tier 2 (L2) - Senior SOC Analyst / Incident Responder

Tier 2 are the “heavy lifters” of the SOC. L2 analysts handle incidents escalated by L1, conduct deep analysis, and coordinate threat response.


Tier 2 Main Responsibilities

Deep analysis — investigating incidents escalated by Tier 1
Event correlation — connecting alerts from multiple sources
Incident response — containment, eradication, recovery
Malware analysis — basic analysis (strings, behavior)
Rule creation — developing and tuning SIEM detection rules
Threat intelligence — IoC integration, TI report analysis
Mentoring — training Tier 1 analysts
Documentation — playbooks, procedures, post-mortems




Tier 3 (L3) - SOC Engineer / Threat Hunter / Forensics Expert

Tier 3 is the SOC elite. L3 experts handle the most difficult incidents, perform proactive threat hunting, and develop detection capabilities.

Tier 3 Main Responsibilities
Threat hunting — proactive threat searching without alerts
Advanced forensics — disk, memory, network, mobile forensics
Malware reverse engineering — malicious code analysis
Detection development — creating advanced rules, ML models
Tooling — automation, custom scripts, integrations
Research — tracking new attack techniques, POCs
Incident lead — leading major incidents
Architecture — security monitoring stack design





SOC Career Path
                    ┌─────────────────────────────────────┐
                    │                                     │
                    ▼                                     │
┌─────────────┐   2-3 years  ┌─────────────┐   2-4 years  │
│   Tier 1    │ ───────────► │   Tier 2    │ ────────────►│
│ SOC Analyst │              │Senior Analyst│              │
└─────────────┘              └─────────────┘              │
                                   │                      │
                                   │ 2-3 years            │
                                   ▼                      │
                    ┌──────────────┴──────────────┐       │
                    │                             │       │
                    ▼                             ▼       │
             ┌─────────────┐              ┌─────────────┐ │
             │   Tier 3    │              │SOC Manager/ │ │
             │   Expert    │              │Team Lead    │◄┘
             └─────────────┘              └─────────────┘
                    │                             │
                    │ 3-5 years                   │ 3-5 years
                    ▼                             ▼
             ┌─────────────┐              ┌─────────────┐
             │Threat Hunter│              │   CISO      │
             │Principal Eng│              │ Director    │
             └─────────────┘              └─────────────┘





https://nflo.tech/knowledge-base/soc-tier-1-2-3-analyst-roles-responsibilities/



## Incident Response Plan 6 Stages


1. Preparation
Build readiness before incidents happen. �
Define incident response policy, roles, and escalation paths.
Create playbooks for common scenarios (phishing, ransomware, account compromise).
Set up tooling: SIEM, EDR, logging, ticketing, communication channels.
Train the team and run tabletop exercises.
This stage determines how smoothly the rest of the workflow runs. �

2. Identification (Detection & Analysis)
Detect and confirm that an incident is occurring. �
Monitor alerts from SIEM/EDR, user reports, threat intel, etc.
Triage: validate if it’s a true positive and classify severity.
Gather initial data: affected users, systems, indicators (IPs, domains, hashes).
Decide whether to declare a formal incident and notify stakeholders.
Output: a scoped, documented incident with initial severity and impact. �

3. Containment
Stop the incident from spreading or causing more damage. �
Short-term containment: quick actions like isolating a host, blocking an IP/domain, disabling a compromised account.
Long-term containment: temporary controls that allow business to keep running while you clean up (e.g., network segmentation, additional MFA).
Preserve evidence for forensics (images, logs, memory dumps) before heavy changes.
Goal: limit impact while maintaining enough visibility to investigate. �

4. Eradication
Remove the root cause and all traces of the threat. �
Identify how the attacker got in (phishing link, vulnerable service, weak creds, etc.).
Remove malware, backdoors, unauthorized accounts, and persistence mechanisms.
Patch vulnerabilities, reconfigure systems, and harden access controls.
Validate that malicious artifacts and C2 channels are gone.
This stage ensures the environment is clean before you bring things back online. �

5. Recovery
Restore normal operations safely and in a controlled way. �
Rebuild or restore systems from clean images/backups.
Reset credentials, rotate keys, and enforce stronger controls (e.g., MFA).
Monitor recovered systems closely for signs of re-infection.
Gradually return services to production, with validation and testing.
Success criteria: business processes are back to normal with acceptable risk. �

6. Lessons Learned
Review the incident to improve future response. �
Conduct a post-incident review (post-mortem) with all relevant teams.
Document timeline, decisions, what worked, and what failed.
Identify root causes and systemic issues (process, tooling, training).
Update playbooks, detection rules, and security controls based on findings.

This stage closes the loop and feeds directly back into Preparation, making the next incident easier to handle.


## Incident Workflow 

An Incident Workflow (specifically within a Security Operations Center or IT Service Management context) is a standardized, repeatable sequence of steps designed to detect, manage, investigate, contain, and resolve operational disruptions or cyber threats.


[ Alert Intake & Log Correlation ]
               │
               ▼
[ Ticket Creation & Enrichment ]
               │
               ▼
    [ Initial Triage (L1) ]
               │
      ┌────────┴────────┐
      ▼                 ▼
(False Positive)   (Confirmed / Suspicious)
  [ Close Ticket ]      │
                        ▼
      [ Escalation & Investigation (L2/L3) ]
                        │
                        ▼
       [ Playbook Execution & Containment ]
                        │
                        ▼
      [ Resolution & Remediation Actions ]
                        │
                        ▼
     [ Ticket Closure & Post-Incident Review ]


Step 1: Alert Intake & Log Correlation

​Log Collection: Security tools across the network (firewalls, EDR/endpoints, servers, applications) continuously generate and send logs to the SIEM (Security Information and Event Management) platform.
​Correlation Rules: The SIEM correlates events across multiple sources to spot suspicious patterns (e.g., multiple failed logins followed by a successful login).
​Alert Generation: Once a rule condition is met, a security alert is triggered automatically.

​Step 2: Ticket Creation & Context Enrichment

​Auto-Ticketing: The security alert automatically generates an incident ticket in the ITSM/Case Management tool (e.g., Jira, ServiceNow).
​Context Enrichment: Automated systems enrich the ticket with context before an analyst looks at it:
​User & Asset Info: Hostname, IP address, user role, ownership, location.
​Threat Intelligence: Reputation data (IP/hash scores, domain age).
​Historical Context: Previous alerts or activity associated with the asset or account.

​Step 3: Initial Triage (Tier 1 SOC Analyst)

​First-Line Review: The L1 analyst reviews the enriched ticket to validate the alert.
​Validation & Severity: Determines whether the event is a True Positive (real threat) or a False Positive (benign/expected activity).
​Action:
​False Positives / Benign: Document findings and close the ticket.
​True Positives / Unknowns: Escalated to higher tiers for deep-dive investigation.

​Step 4: Escalation & Advanced Investigation (Tier 2 / Tier 3 Analyst)

​Deep-Dive Analysis: L2/L3 analysts conduct a full investigation to uncover the root cause, timeline, and full blast radius.
​Techniques & Artifacts:
​Memory and forensic analysis.
​Endpoint telemetry & network packet capture (PCAP) inspection.
​Identity/Active Directory auditing.
​Impact Assessment: Determines what systems were compromised and whether sensitive data was accessed or exfiltrated.

​Step 5: Playbook & Response Execution

​Standardized Response: Analysts follow predefined Playbooks/Runbooks tailored to the threat type (e.g., Phishing, Malware, Ransomware, Unauthorized Access).
​Mitigation Actions:
​Isolating compromised hosts from the network.
​Blocking malicious IPs or domains at the firewall/web proxy.
​Revoking active user sessions and resetting compromised credentials.
​Removing malicious emails or files from endpoints.

​Step 6: Containment, Resolution & Documentation

​Threat Eradication: The threat is completely removed from the environment, and systems are safely restored to operational status.
​Detailed Logging: All investigation findings, evidence, root causes, and remediation actions are thoroughly documented inside the incident ticket to meet compliance and audit standards.

​Step 7: Ticket Closure & Post-Incident Review (PIR)

​Formal Closure: Once systems are verified as secure, the ticket is officially closed.
​Post-Incident Review (PIR / Lessons Learned): For major or critical incidents, the SOC team conducts a debrief to identify:
​What went well during the response.
​Where detection or containment was delayed.
​Necessary updates to SIEM rules, playbooks, or security controls to prevent recurrence.



Why Is an Incident Workflow Important?

​Reduces Response Time: Minimizes MTTD (Mean Time to Detect) and MTTR (Mean Time to Respond) by replacing guesswork with structured processes.
​Minimizes Impact: Fast containment prevents small localized events from turning into organization-wide outages or breaches.
​Ensures Regulatory Compliance: Frameworks like ISO 27001, SOC 2, and GDPR mandate documented incident response procedures and audit trails.
​Drives Continuous Improvement: Feedback loops from post-incident reviews ensure that security controls and operational playbooks evolve with emerging threats.





## Key Incident Analysis Steps in a SOC

Incident analysis in a SOC is a structured process used to investigate a security alert, determine what happened, assess its impact, and provide the necessary information for response and remediation.

1. Alert Triage and Validation

Start by reviewing and acknowledging the alert generated by security tools such as SIEM, EDR, IDS/IPS, or other monitoring systems. Collect basic information such as the source and destination IP addresses, affected users or systems, timestamps, and alert severity. Determine whether the alert is a true positive, false positive, or benign event.

2. Initial Scoping and Prioritization

Determine the potential scope of the incident by identifying affected hosts, user accounts, applications, systems, and data. Assess the severity and urgency based on factors such as asset criticality, data sensitivity, threat intelligence, and potential business impact. Prioritize the incident according to risk.

3. Evidence Collection and Preservation

Collect relevant evidence required for the investigation, including SIEM logs, endpoint telemetry, network traffic, file artifacts, and other available data. Preserve the evidence properly and avoid unnecessary modifications. When required, maintain a proper chain of custody, especially for forensic investigations.

4. Timeline Reconstruction and Event Correlation

Correlate events from multiple security and infrastructure sources to reconstruct the sequence of activities. Identify important Indicators of Compromise (IOCs), attack vectors, initial access, lateral movement, persistence, and other suspicious activities. Where appropriate, map the observed behavior to frameworks such as MITRE ATT&CK.

5. Detailed Analysis and Root Cause Investigation

Analyze the nature and behavior of the threat, such as malware, phishing, credential compromise, insider activity, or unauthorized access. Determine how the attacker gained access, what actions were performed, and whether vulnerabilities, misconfigurations, or process weaknesses contributed to the incident. Identify the root cause where possible.

6. Impact Assessment

Determine the actual or potential impact of the incident. Assess affected systems, accounts, and data, along with possible data exposure or exfiltration, service disruption, financial impact, and compliance implications. The findings can then support decisions about containment and remediation.

7. Documentation, Reporting, and Escalation

Document the investigation findings, evidence, timeline, verdict, impact, and recommended actions in the incident ticket or report. Update the incident status and escalate the case to L2, the Incident Response team, management, or other stakeholders when required.

8. Handover and Lessons Learned Support

Provide the investigation findings to the teams responsible for containment, eradication, and recovery. After the incident, contribute to lessons-learned activities by identifying detection gaps, process weaknesses, and opportunities for improving security controls and detection rules.

Simple Flow

Alert → Validate → Scope → Collect Evidence → Correlate & Reconstruct → Analyze Root Cause → Assess Impact → Document & Escalate → Handover & Improve



https://www.sentinelone.com/blog/mastering-the-art-of-soc-analysis-part-1/

https://www.netwitness.com/blog/incident-response-process/





## Incident Analysis in 4 Simple Steps

1. Validate & Scope
Review the alert.
Determine True Positive / False Positive.
Identify affected users, hosts, systems, and assets.
Determine severity and priority.
Question: Is it real, and how big is it?

2. Collect & Correlate Evidence
Collect relevant logs and endpoint/network data.
Identify IOCs such as IPs, domains, hashes, and files.
Correlate events from different sources.
Build a timeline of what happened.
Question: What happened and in what order?

3. Analyze & Assess Impact
Determine the attack type and method.
Identify the entry point, attacker activity, lateral movement, and persistence.
Investigate the root cause.
Determine affected systems, data, and potential business impact.
Question: How did it happen and what was affected?

4. Document & Handover
Document evidence, findings, timeline, verdict, and impact.
Escalate to L2/Incident Response when required.
Provide recommendations for containment and remediation.
Support lessons learned and detection improvements.
Question: What did we find, and what needs to happen next?





## 1. What Is a Ticketing System?

A ticketing system is a software management tool used by organizations to capture, manage, and track the resolution of incoming requests or reported issues (incidents). It acts as a central hub where various communication channels---such as emails, chats, phone calls, and automated security alerts---are consolidated into a single workflow.

2. What Is a Ticket?

A ticket is a unique digital record within the system that represents a specific task, problem, or request. In a security context, it serves as the "source of truth" for an incident.
Standard Ticket Components:

    Ticket ID: A unique reference number for tracking.\
    Description: Detailed information about the issue or alert.\
    Timestamp: When the incident was detected and reported.\
    Priority Level: The urgency of the issue (Low, Medium, High, Critical).\
    Status: The current stage of the process (New, In-Progress, Resolved, Closed).\
    Assignee: The specific analyst or team responsible for fixing the problem.

3. Importance of Ticketing Systems in a SOC

In a high-pressure environment like a Security Operations Center (SOC), a ticketing system is vital for the following reasons:

    Organization and Scalability: Prevents critical security alerts from being lost in large volumes of data by organizing them into actionable tasks.\
    Accountability (RACI): Clearly defines who is Responsible, Accountable, Consulted, and Informed for every security event, reducing confusion during a crisis.\
    Speed (MTTR): Helps reduce the Mean Time to Respond (MTTR) by providing automated workflows and quick access to necessary data.\
    Compliance and Auditing: Creates a permanent audit trail (historical record), essential for proving that security protocols were followed.

4. Functions of a Ticketing System in a SOC

The ticketing system performs several specialized functions to ensure the SOC operates efficiently:

    Incident Capture & Integration: Automatically creates tickets from SIEM (Security Information and Event Management) alerts, ensuring immediate response workflows begin.\
    Categorization & Prioritization: Filters alerts based on severity, allowing analysts to focus on true positives (real threats) while deprioritizing false positives (harmless triggers).\
    Case Management & Documentation: Serves as a repository for evidence, where analysts attach logs, screenshots, and findings to build a complete investigation case.\
    Collaboration: Enables different departments (SOC, IT, Legal, etc.) to communicate within the ticket, ensuring shared visibility.\
    Performance Metrics: Tracks ticket volume, resolution time, and outcomes to measure SOC efficiency and improve response strategies.
    
    



## The Complete  End-to-End SOC Incident Workflow


[ 1. Alert Intake & Log Correlation ]
                 │
                 ▼
[ 2. Ticket Creation & Auto-Enrichment ]
                 │
                 ▼
    [ 3. Initial Triage (L1) ] ◄── Guided by SOP
                 │
                 ├────────────────────────┐
                 ▼                        ▼
      (False Positive / Benign)  (Confirmed Threat)
                 │                        │
                 ▼                        ▼
          [ Close Ticket ]       [ 4. Escalation (L2/L3) ]
                                          │
                                          ▼
                               [ 5. Incident Analysis ]
                                          │
                                          ▼
                               [ 6. Containment & Remediation ] ◄── Executed via Playbooks/Runbooks
                                          │
                                          ▼
                               [ 7. Closure & Post-Incident Review ]




1. Alert Intake & Log Correlation

​What Happens: Security tools (firewalls, EDR, cloud logs, network tools) continuously send log data into the SIEM.
​Trigger: The SIEM correlates events across different logs and matches a detection rule, triggering an alert.

​2. Ticket Creation & Context Enrichment

​What Happens: An incident ticket is automatically generated in the ticketing/ITSM system.
​Automation: Automated tools (SOAR) enrich the ticket with context (user info, asset criticality, threat intelligence reputation scores, IP geolocation) before an analyst opens it.

​3. Initial Triage (L1 Analyst) — Guided by SOP

​What Happens: Tier 1 analysts perform the first level of review using standard SOPs (Standard Operating Procedures) to validate the alert.
​Outcome:
​If identified as a False Positive or Benign Activity, the ticket is documented and closed.
​If confirmed as suspicious or a True Positive, it moves forward.

​4. Escalation (L1 \rightarrow L2/L3)

​What Happens: If the threat is complex or requires higher privilege/deeper technical handling, L1 escalates the ticket to Tier 2/3 analysts or the Incident Response (IR) team.

​5. Incident Analysis
​What Happens:

Deep-dive technical investigation takes place. Analysts perform root-cause analysis, examine memory dumps, analyze network PCAPs, inspect malware samples, and determine the attack timeline and total scope (blast radius).

​6. Playbook & Runbook Execution (Containment & Remediation)

​What Happens: Analysts execute specific response actions based on the attack type.
​Playbook: The high-level decision flow for a specific threat (e.g., Ransomware Playbook or Phishing Playbook).
​Runbook: The step-by-step technical script or command sequence used to carry out that response (e.g., isolate host from network, revoke tokens, delete malicious emails).

​7. Ticket Closure & Post-Incident Review (PIR)

​What Happens: Once the threat is fully eradicated and systems are restored to a safe state, the ticket is updated with complete forensic documentation and formally closed.
​Continuous Improvement: For major incidents, a Post-Incident Review (PIR) is held to update SIEM rules, refine SOPs, and improve playbooks for future prevention.




## SOP

SOP stands for Standard Operating Procedure.
It is a formal, documented set of step-by-step instructions that describes how to perform a routine or critical process consistently and correctly. SOPs ensure that tasks are carried out the same way every time, regardless of who performs them.

SOPs transform industry-standard frameworks into practical procedures to streamline daily operations in a Security Operations Center. Comprising playbooks and runbooks for security monitoring, alert handling, and incident response, these guidelines provide analysts with clear direction and ensure a secure operational approach."


Typical Structure of a SOC SOP
A good SOC SOP usually includes:


Purpose – Why the procedure exists

Scope – What it covers and who it applies to

Roles & Responsibilities – Who does what (Tier 1, Tier 2, etc.)

Prerequisites / Tools – Required systems (SIEM, EDR, ticketing, etc.)

Step-by-step procedure – Detailed actions

Decision points / Escalation criteria

Documentation requirements

Related documents / references (e.g., NIST guidelines, internal policies)




Common Types of SOPs / Playbooks in a SOC

Alert triage and prioritization
Phishing / email compromise investigation
Malware / ransomware response
Suspicious login or account compromise
Data exfiltration investigation
Network anomaly / DDoS handling
Vulnerability exploitation response
Escalation and communication procedures
Evidence collection and chain-of-custody
Post-incident reporting and lessons learned




## SOC & NOC


In cybersecurity, a SOC, or Security Operations Center, is dedicated to monitoring, detecting, analyzing, and responding to security incidents.
A NOC, or Network Operations Center, focuses on maintaining the overall performance, availability, and health of the network infrastructure.
The main difference is that the SOC is primarily concerned with security threats and protection, while the NOC is focused on network performance and uptime.




## SCENARIO QUESTIONS :

Q 1:
Multiple failed login attempts followed by one successful login from an external IP address."
A:
As an L1 SOC analyst, the first step is to validate the alert and create or update the incident ticket. I then gather relevant information such as the affected user, endpoint, source IP address, timestamps, login history, and any related logs. Next, I perform the initial triage by assessing the severity and priority of the alert and conducting a basic investigation to determine whether it is a true positive or a false positive. I document all my findings and evidence in the ticket. If the incident is confirmed and my organization's SOP allows it, I perform authorized initial containment actions, such as isolating the endpoint or disabling the compromised account. Finally, I escalate the incident to the Tier 2 analyst with all the investigation details for further analysis and response. If the alert is determined to be a false positive, I document the reason and close the ticket according to the organization's procedures.




Q 2:
A user reports that they accidentally downloaded a PDF converter from an unknown website. Shortly afterward, your EDR detects:
Trojan:Win32/FakeUpdate
As the L1 SOC analyst, what steps would you take to investigate and handle this alert before escalating it?

A:
"As an L1 SOC analyst, I would first validate the alert and create or update the incident ticket. I would gather relevant information such as the affected endpoint, user, timestamps, the downloaded file, source domain or URL, and any associated IP addresses. I would then perform initial triage to determine the severity and priority of the incident. During the investigation, I would review EDR telemetry, including the process tree, command-line activity, PowerShell execution, network connections, DNS activity, browser history, and the file hash and reputation to determine whether the downloaded PDF converter caused the malware detection. I would document all findings and determine whether the alert is a true positive or false positive. If authorized by the organization's SOP, I would perform initial containment, such as isolating the endpoint, and then escalate the incident to the Tier 2 analyst with all the collected evidence for further investigation."




Q 3:

"A user account has successfully logged in from India at 10:00 AM and then from Russia at 10:15 AM."
As an L1 SOC analyst, how would you investigate this alert?


A:
"I would first validate the alert and gather information such as the user account, timestamps, source IP addresses, device details, and authentication logs. Since the alert indicates successful logins from India and Russia within 15 minutes, I would consider it a possible impossible travel scenario. I would check whether the user was connected through a VPN, whether MFA was used, whether the device and browser match the user's normal behavior, and whether either IP address has a malicious reputation. I would also review previous login history and any suspicious activities after the login. I would contact the user to verify whether they performed both logins. Based on the collected evidence, I would determine whether the alert is a true positive or false positive, document my findings, and escalate the incident to Tier 2 if further investigation or containment is required."



Q4:
A Windows endpoint generates an EDR alert:
"powershell.exe spawned cmd.exe, which then launched a file from the user's Downloads folder."
How do you investigate this incident?

A:
"EDR generates alerts based on its detection logic, which may include process behavior, command-line activity, file reputation, network connections, and other telemetry. The process tree is used to provide context and help analysts understand the sequence of events during an investigation."





