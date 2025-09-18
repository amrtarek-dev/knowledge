
Attack = Motive (Goal) + Method + Vulnerability
## Classification of Attacks
- Passive: do not tamper the data (intercepting and monitoring)
- Active: Temper the data (disrupt the communication)
- Close-in Attacks: Attacker is close physically (shoulder surfing)
- Insider Attacks: Using privileged access to violate rules
- Distribution Attacks: Temper with the hardware or software used by the company at the source or in transit.

## Hacking methodologies
Hacking is understanding the system and manipulate it in a way unexpected by the system developer or designer to make it do something not normally doing it.

Hacking refers to exploiting system vulnerabilities and compromising security controls to gain unauthorised or inappropriate access to a system's resources.
It involves modifying system or application features to achieve a goal outside of the creator's original purpose.

It have 5 steps cycle:
1. Phase 1: Foot printing and Reconnaissance: when attacker seeks to gather information about. a target prior to launching an attack.
	1. Passive: Without directly interacting with the target (Searching public records or news releases)
	2. Active: directly interacting with the target by any means (telephone calls of target help desk or technical department).
2. Phase 2: Scanning: it is the pre-attack phase when the attacker scans the network for specific information based on information gathered during reconnaissance. (port scanners, network mappers, ping tools, and vulnerability scanners) to get the live machines, port, port status, OS details, device type and system uptime to launch attack.
3. Phase 3: Gaining Access: where the attacker obtains access to the operating system or applications on the target computer or network. then escalate privileges
4. Phase 4: Maintaining Access: when the attacker tries to retain their ownership of the system. by securing their exclusive access with backdoors, rootkits, or Trojans.
5. Phase 5: Clearing Tracks: clearing log files, or overwrites the server , system and application logs to avoid suspicion.


### Cyber Kill Chain Methodology
Is a component of intelligence-driven defense for the identification and prevention of malicious intrusion activites.

1. **Reconnaissance**: Gather data on the target to probe for weak points.
2. **Weapanization**: Create a deliverable malicious payload using an exploit and a backdoor
3. **Delivery**: Send weaponized bundle to the victum using email, USB, etc.
4. **Exploitation**: Exploit a vulnerability by executing code on the victim's system
5. **Installation**: Install malware on the target system
6. **Command and Control**: Create a command and control channel to communicate and pass data back and forth.
7. **Action on Objectives**: Perform actions to achieve intended objectives/goals

## TTPs
- Tactics: are the guideline that describe the way an attacker performs the attack form beginning to the end
- Techniques: are the technical methods used by an attacker
- Procedures: the steps that treat actors follows to launch an attack.

## MITRE Attack Framework
MITRE ATT&CK is a globally accessible knowledge base of adversary tactics and techniques based on real-world observations.

- PRE-ATT&CK
	- Recon
	- Weaponize
- Enterprise ATT&CK
	- Deliver
	- Exploit
	- Control
	- Execute
	- Maintain

## Diamond Model of Intrusion Analysis
it is a way of Incident response analysis which is a framework for identifying the cluster of events that are correlated on any of the system in an organization.

``` md

		  | Adversary |
	Uses  /            \
		 / Deployed via \
Infrastructure -------- Capability
	      \             /
   Connect \           /  Exploits
	  to	 | Victim | 
```

Adversary: An opponent who was behind the attack
Victim: the target that has been exploited or where the attack was performed
Capability: The attack strategies or how the attack was performed
Infrastructure: what the adversary used to reach the victim
