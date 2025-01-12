
## Security Audit
A review of an organization's security controls, policies , and procedures against a set of expectations.
There are 2 main types of security audits:
- External
- Internal: Conducted by a team of people that might include an oraganization's compliance office, security manager, and other security team members.
	- Identify organizational risk
	- Assess controls
	- Correct compliance issues
## Internal Security Audit
Steps:
- Establishing the scope and goals
	- Scope requires organization to identify people, assets, policies, procedures and technologies that impact the security posture.
	- Goals are outline of the organization's security objectives.
- Conducting a risk assessment
	- Focused on identifying potential threats, risks, and vulnerabilities
- Completing a controls assessment
	- Reviewing an organization's existing assets, then evaluating potential risks to those assets, to ensure internal controls and processes are effective.
	- Control categories:
		- Administrative controls: related to human component
		- Technical Controls: Hardware and Software solutions to protect assets. (IDS)
		- Physical Controls: prevent physical access to protected assets, (CCTV)
- Assessing compliance
	- determining whether or not the organization is adhering to necessary compliance regulations. (GDPR, PCI DSS)
- Communicating result to stakeholders.
	- Summarizes scope and goals
	- Lists existing risks
	- Notes how quickly those risks need to be addressed
	- Identifies compliance regulations.
	- Provide recommendations for security posture.

https://www.nist.gov/cyberframework/assessment-auditing-resources
https://www.ready.gov/business/emergency-plans/recovery-plan

## Security tools

**Logs** are the source of data that the tools we'll cover are designed to organize.

A log is a record of events that occur within an organization's systems and networks.
i.e. security related logs include records of employees signing into thier computers or accessing web-based services.
Common log sources:
- **Firewall logs**: Is a record of attempted of established connections for incoming traffic from the internet, includes outbound requests to the internet from the network.
- **Network logs**: is a record of all computers and devices that enter and leave the network, includes connections between devices and services on the network
- **Server logs**: is a record of events related to services (Websites, emails, file shares) includes login, password, and username requests.

## Security information and event management (SIEM)
**Security information and event management** (SIEM) tool is an application that collects and analyzes log data to monitor critical activities in an organization, by collecting a real-time information and allow security analysts to identify potential breaches.
- Splunk (self hosted SIEM solution)
- Google Chronicla (Cloud-native SIEM sool)

## Software application Metrics
are key technical attributes such as response time, availability, and failure rate, which are used to assess the performance of the software application.

-  **Security posture dashboard**: designed for security operations centers (SOCs) , It displays the last 24 hours of an organization’s notable security-related events and trends
-  **Executive summary dashboard**: analyzes and monitors the overall health of the organization over time
-  **Incident review dashboard**: allows analysts to identify suspicious patterns that can occur in the event of an incident
-  **Risk analysis dashboard**: identify risk for each risk object (e.g., a specific user, a computer, or an IP address). It shows changes in risk-related activity or behavior, such as a user logging in outside of normal working hours or unusually high network traffic from a specific computer.
-  **Enterprise insights dashboard**: identifies suspicious domain names in logs, known as indicators of compromise (IOCs). Each result is labeled with a confidence score to indicate the likelihood of a threat.
-  **Data ingestion and health** **dashboard**: shows the number of event logs, log sources, and success rates of data being processed into Chronicle.
-  **IOC** **matches** **dashboard**: indicates the top threats, risks, and vulnerabilities to the organization.
-  **Main** **dashboard**: displays a high-level summary of information related to the organization’s data ingestion, alerting, and event activity over time.
- **Rule detections** **dashboard**: provides statistics related to incidents with the highest occurrences, severities, and detections over time.
-  **User sign in overview** **dashboard**: overview dashboard provides information about user access behavior across the organization.

## SIEM Tools types
- Self-hosted (Own physical infrastructure)
- Cloud-hosted (Accessible through the internet)

### Splunk
- Splunk Enterprise (self-hosted SIEM tool)
- Splunk Cloud (cloud only environment)
### Google's Chronicle
- Cloud native tool designed to retain analyze and search data.
###  Suricata
Network analysis and threat detection software is used to inspect network traffic to identify suspicious behavior and generate network data logs.

## Security Orchestration, automation,  and response (SOAR)
Is a collection of applications, tools, and workflows that uses automation to respond to security events. by Open Information Security Foundation (OISF).
## Playbook
**Playbook** is a manual that provides details about any operational action, including incident response, security or compliance reviews, access management, and many other organizational tasks that require a documented process from beginning to end.

Packet sniffer (Network protocol analyzer) is a tool designed to capture and analyze data traffic within network.
- tcpdump
- Wireshark

## Programming
used to create a specific set of instructions for a computer to execute tasks.
programming languages, such as Python, to execute automation or Structured Query Language (SQL) to create, interact with, and request information from a database

An **operating system** is the interface between computer hardware and the user. Linux®, macOS®, and Windows are operating systems.

A **web vulnerability** is a unique flaw in a web application that a threat actor could exploit by using malicious code or behavior, to allow unauthorized access, data theft, and malware deployment.

**Antivirus software** is a software program used to prevent, detect, and eliminate malware and viruses. It is also called anti-malware. Depending on the type of antivirus software, it can scan the memory of a device to find patterns that indicate the presence of malware.

An **intrusion detection system** (IDS) is an application that monitors system activity and alerts on possible intrusions.

**Encryption** is the process of converting data from a readable format to a cryptographically encoded format which makes data unreadable and difficult to decode for an unauthorized user; its main goal is to ensure confidentiality of private data

**Penetration testing**, also called pen testing, is the act of participating in a simulated attack that helps identify vulnerabilities in systems, networks, websites, applications, and processes.
