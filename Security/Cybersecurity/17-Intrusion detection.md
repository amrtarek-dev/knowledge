
## IDS
Intrusion detection systems collects and analyzes system information for abnormal activities.
If something unusual is detected, the IDS send out an alert to appropriate channels and personnel.

## IPS
Intrusion prevention systems, has all the same capabilities as an IDS, but they can do more, they monitor system activity for intrusions and takes action to stop it.

- Snort
- Zeek
- Kismet
- Sagan
- Suricata

## EDR
Endpoint detection and Response is an application that monitors an endpoint for malicious activity. EDR tools are installed on endpoints. Remember that an **endpoint** is any device connected on a network. Examples include end-user devices, like computers, phones, tablets, and more.

EDR tools also use _automation_ to stop attacks without the manual intervention of security professionals. For example, if an EDR detects an unusual process starting up on a user’s workstation that normally is not used, it can automatically block the process from running.

- Open EDR®
- Bitdefender™ Endpoint Detection and Response
- FortiEDR™

## SIEM
Security information and event management (SIEM) tools also have detection capabilities

### **Detection categories**

As a security analyst, you will investigate alerts that an IDS generates. There are four types of detection categories you should be familiar with:

1. **A true positive** is an alert that correctly detects the presence of an attack.
2. **A true negative** is a state where there is no detection of malicious activity. This is when no malicious activity exists and no alert is triggered. 
3. **A false positive** is an alert that incorrectly detects the presence of a threat. This is when an IDS identifies an activity as malicious, but it isn't. False positives are an inconvenience for security teams because they spend time and resources investigating an illegitimate alert. 
4. **A false negative** is a state where the presence of a threat is not detected. This is when malicious activity happens but an IDS fails to detect it. False negatives are dangerous because security teams are left unaware of legitimate attacks that they can be vulnerable to.


## SIEM
Security Information and Event Management (SIEM)
An application that collect and analyzes log data to monitor critical activities in an organization.

A SIEM looks at data flows between all the different systems in the network and analyzes them to provide a real-time picture of any potential threats to the network. 

It does this by ingesting massive amounts of data and categorizes this data, so that it's easily accessible through a centralized platform similar to a car's dashboard. 

1. SIEM tools collect and aggregate data. This data is typically in the form of logs, which are basically a record of all the events that happened on a given source. Data can come from multiple sources such as IDS or IPS, databases, firewalls, applications, and more.Different data sources gets centralized in one place.
2. Normalize data. Takes the raw data that the SIEM has collected and cleans it up by removing non essential attributes to make consistency in log records.
3. Analyze data. according to configured rules

tools:
- AlienVault® OSSIM™
- Chronicle
- Elastic
- Exabeam
- IBM QRadar® Security Intelligence Platform
- LogRhythm
- Splunk


## SOAR
Security Orchestration, automation, and response
A collection of applications, tools, and workflows that uses automation to respond to security events.

> SIEM Collect, analyze, and report on security events
> SOAR Automates analysis and response to security events and incident.

