an intrusion detection system (IDS) can detect possible intrusions and send out alerts to security analysts to investigate the suspicious activity. 

Security analysts can also use security information and event management (SIEM) tools to detect, collect, and analyze security data.

**Threat hunting** is the proactive search for threats on a network. Security professionals use threat hunting to uncover malicious activity that was not identified by detection tools and as a way to do further analysis on detections.

**threat intelligence** is evidence-based threat information that provides context about existing or emerging threats.

come from private or public sources like:
- **Industry reports**: These often include details about attacker's tactics, techniques, and procedures (TTP).
- **Government advisories:** Similar to industry reports, government advisories include details about attackers' TTP. 
- **Threat data feeds**: Threat data feeds provide a stream of threat-related data that can be used to help protect against sophisticated attackers like **advanced persistent threats (APTs)**. APTs are instances when a threat actor maintains unauthorized access to a system for an extended period of time.

_threat intelligence platform_ (TIP) which is an application that collects, centralizes, and analyzes threat intelligence from different sources.


## **Cyber deception**
Cyber deception involves techniques that deliberately deceive malicious actors with the goal of increasing detection and improving defensive strategies.

**Honeypots** are an example of an active cyber defense mechanism that uses deception technology. Honeypots are systems or resources that are created as decoys vulnerable to attacks with the purpose of attracting potential intruders. For example, having a fake file labeled _Client_ _Credit Card Information - 2022_ can be used to capture the activity of malicious actors by tricking them into accessing the file because it appears to be legitimate. Once a malicious actor tries to access this file, security teams are alerted.


IoC: **Indicators of compromise** (**IoCs**) are observable evidence that suggests signs of a potential security incident.
> IoCs help to identify the _who_ and _what_ of an attack after it's taken place

IoA: **Indicators of attack** (**IoA**) are the series of observed events that indicate a real-time incident.
> IoAs focus on finding the _why_ and _how_ of an ongoing or unknown attack.


>**Note**: Indicators of compromise are not always a confirmation that a security incident has happened. IoCs may be the result of human error, system malfunctions, and other reasons not related to security.


The Pyramid of Pain captures the relationship between indicators of compromise and the level of difficulty that malicious actors experience when indicators of compromise are blocked by security teams.

1. **Hash values**: Hashes that correspond to known malicious files. These are often used to provide unique references to specific samples of malware or to files involved in an intrusion.
    
2. **IP addresses**: An internet protocol address like 192.168.1.1
    
3. **Domain names**: A web address such as www.google.com 
    
4. **Network artifacts**: Observable evidence created by malicious actors on a network. For example, information found in network protocols such as User-Agent strings. 
    
5. **Host artifacts:** Observable evidence created by malicious actors on a host. A host is any device that’s connected on a network. For example, the name of a file created by malware.
    
6. **Tools**: Software that’s used by a malicious actor to achieve their goal. For example, attackers can use password cracking tools like John the Ripper to perform password attacks to gain access into an account.
    
7. **Tactics, techniques, and procedures (TTPs)**: This is the behavior of a malicious actor. Tactics refer to the high-level overview of the behavior. Techniques provide detailed descriptions of the behavior relating to the tactic. Procedures are highly detailed descriptions of the technique. TTPs are the hardest to detect.


**Threat intelligence** is evidence-based threat information that provides context about existing or emerging threats.
By adding context to an IoC—for instance, identifying other artifacts related to the suspicious IP address, such as suspicious network communications or unusual processes—security teams can start to develop a detailed picture of a security incident.

Threat intelligence platforms use crowdsourcing to collect information from the global cybersecurity community.

**Crowdsourcing** is the practice of gathering information using public input and collaboration.
Like:
- Information Sharing and Analysis Centers (ISACs)
- **Open-source intelligence (OSINT)**

This threat intelligence data is used to improve the detection methods and techniques of security products, like detection tools or anti-virus software.


## VirusTotal
[**VirusTotal**](https://www.virustotal.com/gui/home) is a service that allows anyone to analyze suspicious files, domains, URLs, and IP addresses for malicious content.

> Data uploaded to VirusTotal will be publicly shared with the entire VirusTotal community. Be careful of what you submit, and make sure you do not upload personal information.

There are other investigative tools that can be used to analyze IoCs:
- [Jotti's malware scan](https://virusscan.jotti.org/) is a free service that lets you scan suspicious files with several antivirus programs. There are some limitations to the number of files that you can submit.
- [Urlscan.io](https://urlscan.io/) is a free service that scans and analyzes URLs and provides a detailed report summarizing the URL information.
- [MalwareBazaar](https://bazaar.abuse.ch/browse/) is a free repository for malware samples. Malware samples are a great source of threat intelligence that can be used for research purposes.