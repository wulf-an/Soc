
1.Research and understand the role and importance of a Security Operations Center (SOC).

2.Differentiate roles and responsibilities of SOC L1, L2, and L3

3.Learn Standard Operating Procedures (SOPs)

4.Identify the Six Stages in the Incident Response Plan

5.Overview of Ticketing Systems

6.Understand Incident Workflows

7.SOC terminologies with definitions.

8.Research different types of security incidents.

9.Apply the six incident response stages to various incidents and document the steps involved.

10.SOC Process for Incident Analysis and Closure

11.Research and Report on Common Security Attacks






------------------------------------------------------------------------------------------------------------------------------------------------------------



##Brute Force >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

preparation:
mfa,rate limiting,ids,ips,siem alerting,account lockout policies.

1 — Log Analysis / Detection
2 — IP and Reputation Analysis
3 — Account Investigation
4 — Malware or Endpoint Investigation (EDR Scan)
5 — Containment
6 — Eradication
7 — Recovery



##(DDoS) Attack >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>


1 — Traffic & Log Analysis (Detection)
      Sudden increase in traffic
      Multiple requests from many IPs
      Server resource exhaustion (CPU, RAM, bandwidth)
      
2 — IP Reputation Analysis
      IP reputation
      Geolocation
      Botnet activity reports
      
3 — Traffic Pattern Analysis
     
     Analyze the type of attack traffic.
     SYN Flood
     HTTP Flood
     UDP Flood
     ICMP Flood
     DNS Amplification
     
     Things to analyze:
           Protocol used
           Packet rate
           Request patterns
           Target ports


4 — Endpoint / Server Investigation
     Check if the server or endpoint is overloaded or compromised.
     investigate:
          CPU usage
          Memory usage
          Network bandwidth
          Running processes
      Use EDR or monitoring tools to verify system health.    
      
      
5 — Containment
     Block malicious IPs in firewall
     Enable rate limiting
     Enable Web Application Firewall (WAF)
     Use DDoS protection services
     Activate CDN protection
     
     Network teams may also:
       Blackhole traffic
       Apply filtering rules


6 — Eradication
     Update firewall rules
     Patch vulnerable services
     Improve network filtering
     Strengthen server configurations
     cdn
     

7 — Recovery

Restore services to normal operation.
Actions:
Restart affected servers
Restore normal traffic flow
Monitor server performance
Verify system availability

8 — Monitoring & Prevention

Prevent future attacks.
Security improvements:

Enable DDoS protection services
Deploy WAF
Configure traffic rate limiting
Implement network monitoring alerts
Use CDN protection




