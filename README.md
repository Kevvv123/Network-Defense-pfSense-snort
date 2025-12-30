# Network-Defense-pfSense-snort
Enterprise network defense lab using pfSense and Snort IDS.
Overview
This project demonstrates the design and implementation of a secure virtual enterprise network using pfSense as a perimeter firewall and Snort as an intrusion detection system (IDS). The environment was tested using simulated reconnaissance activity to evaluate the network’s ability to detect, log, and respond to early-stage attack behavior.
The focus of this project is defensive security, specifically identifying and mitigating reconnaissance activity before exploitation occurs.

Network Architecture
- Firewall: pfSense
- Intrusion Detection System: Snort (Emerging Threats rule sets)
- Attacker Machine: Kali Linux
- Protected Network: Internal LAN

![Network Atchitecture](screenshots/01-Network-diagram.png)


Threat Simulation
- Configured pfSense firewall rules to restrict unsolicited traffic and control access to the internal network
- Installed and configured Snort on pfSense using Emerging Threats rule sets
- Simulated attacker reconnaissance from a Kali Linux machine using Nmap
- Targeted common ports and services typically scanned during the reconnaissance phase of an attack
- Monitored Snort alerts and firewall logs to validate detection and response
Reconnaissance activity of this nature is commonly used by attackers to:
- Identify exposed services
- Detect misconfigured systems
- Prepare for brute-force or exploitation attempts

![Nmap reconnaissance from Kali](screenshots/02-Firewall-rules.png)
Basic firewall rules blocking unsolicited traffic, whitelisting internal workstations and blocking suspicious ip addresses.

![Nmap reconnaissance from Kali](screenshots/03-Snort-rule-configuration.png)
![Nmap reconnaissance from Kali](screenshots/04-Snort-rule-configuration.png)
Snort IDS deployed on pfSense using Emerging Threats rule sets to monitor reconnaissance and scan activity.

![Nmap reconnaissance from Kali](screenshots/05-nmap-reconnaissance.png)
Simulated reconnaissance using Nmap from a Kali Linux attacker machine to identify exposed services on the internal network.


Results and Observations
- Firewall rules successfully restricted unauthorized access attempts and logged ICMP probing activity
- Snort detected multiple reconnaissance attempts using scan-based detection rules
- High-priority alerts were generated for suspicious scanning behavior across several service ports
- Logged events clearly identified the attacking host, enabling rapid incident triage
In a production environment, this level of visibility would allow a SOC team to respond early and prevent further attack progression.

![Nmap reconnaissance from Kali](screenshots/06-Snort-alerts.png)
![Nmap reconnaissance from Kali](screenshots/07-Snort-alerts.png)
![Nmap reconnaissance from Kali](screenshots/08-Snort-alerts.png)
Snort successfully detecting and generating alerts in response to reconnaissance activity

![Nmap reconnaissance from Kali](screenshots/09-Firewall-logs.png)
Firewall logs corroborating IDS alerts and confirming blocked probing activity.

Remediation and Hardening Recommendations
- Implement automated blocking of confirmed reconnaissance sources
- Reduce attack surface by disabling or restricting unnecessary services
- Tune IDS alerts to minimize false positives and alert fatigue
- Integrate IDS logs with centralized monitoring or SIEM platforms

Skills Demonstrated
- Network perimeter security using pfSense
- Intrusion detection and alert analysis with Snort
- Identification of reconnaissance attack patterns
- Defensive security monitoring and response planning
- Security hardening and risk reduction strategies
