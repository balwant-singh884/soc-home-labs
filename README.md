# Web Crawling Traffic Analysis using Wireshark

## Objective
To analyze automated web crawling behavior at the network level using Wireshark and correlate it with web server logs, from a SOC analyst perspective.



## Lab Environment
- Attacker: Kali Linux
- Victim Server: Ubuntu Linux (Apache Web Server)
- Analysis Tool: Wireshark
- Network: Local virtual lab (VMware)



## Scenario
A simple Apache-hosted website was accessed normally via a browser and then crawled using an automated tool from Kali Linux. Network traffic and server logs were analyzed to identify differences between normal user behavior and automated crawling.



## Tools Used
- Wireshark
- Apache Web Server
- wget (web crawler)



## Baseline Observation (Normal Traffic)
- Single HTTP GET request
- Browser-based User-Agent
- Minimal packet count
- Human-like interaction



## Automated Crawling Observation
- Multiple rapid HTTP GET requests
- Automated User-Agent (`Wget`)
- Requests to `/robots.txt`, `/manual`, and other paths
- No human delay between requests



## Network-Level Analysis (Wireshark)
- Filter used: `http`
- Automated requests identified via User-Agent field
- Sequential and rapid request pattern observed



## Server Log Correlation
- Apache access logs confirmed repeated requests
- Same source IP as observed in Wireshark
- Matching User-Agent value



## SOC Perspective
This activity represents reconnaissance behavior often observed during early stages of an attack. While not malicious by itself, such behavior would be flagged by SOC analysts for further investigation.



## Conclusion
This lab demonstrates how Wireshark can be used to distinguish between normal user traffic and automated reconnaissance activity, and how network traffic analysis can be correlated with application logs for effective security monitoring.
