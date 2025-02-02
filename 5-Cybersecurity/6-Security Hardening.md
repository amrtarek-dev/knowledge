The process of strengthening a system to reduce its vulnerability and attack surface.
An attack surface is all the potential vulnerabilities a threat actor could potentially exploit in a system.

Conducted on:
- Hardware
- Operating systems
- Applications
- Computer networks
- Databases

- Physical security hardening like adding security cameras.
- Software security hardening like software updates (Patches)
- Remove or disable the unused applications or the access permissions across devices and network.
- Conduct regular penetration testing.

### Penetration test (Pentest)
A simulated attack that helps identify vulnerabilities in systems, networks, websites, applications, and processes.

## Operating System Hardning
**Operating system (OS)** the interface between computer hardware and the user.
Hardning OS by:
- Regular intervals (updates, backups)
- Only once (Configure a device settings to fit a secure encryption standard)
- Hardware and software disposal (old hardware is wiped, and delete unused software).
- Use strong password policy and MFA.

### Patch update
A software and operating system update that addresses security vulnerabilities within a program or product.

### Baseline configuration (baseline image)
A documented set of specifications within a system that is used as a basis for future builds, releases, and updates.
- A firewall with a list of allowed and disallowed ports.

### Multi-factor authentication (MFA)
A security measure which requires a user to verify their identity in two or more ways to access a system or network.
- Something you know (Password)
- Something you have (ID card)
- Something unique about you (Fingerprint)


### Virtual Machines (VMs)
Virtual machines are software versions of physical computers. by provide an additional layer of security for an organization because they can be used to run code in an isolated environment.

### Sandbox environments
A sandbox is a type of testing environment that allows you to execute software or programs separate form your network. it used to evaluate suspicious software, evaluate files containing malicious code, and simulate attack scenarios.

## Brute force attack
Is a trial-and-error process of discovering private information.
- Simple brute force attacks (Guess the username and password)
- Dictionary brute force attacks (use a list of commonly used password and stolen credentials).

Prevention:
- **Salting and hashing:** 
	- **Hashing** converts information into a unique value that can then be used to determine its integrity. It is a one-way function, meaning it is impossible to decrypt and obtain the original text.
	- **Salting** adds random characters to hashed passwords. This increases the length and complexity of hash values, making them more secure.
- **Multi-factor authentication (MFA) and two-factor authentication (2FA):**
	- MFA requires a user to verify their identity in two or more ways to access a system or network. This verification happens using a combination of authentication factors: a username and password, fingerprints, facial recognition, or a one-time password (OTP) sent to a phone number or email.
	- 2FA is similar to MFA, except it uses only two forms of verification.
- **CAPTCHA and reCAPTCHA:**
	- CAPTCHA (Completely Automated Public Turing test to tell Computers and Humans Apart) This helps prevent software from trying to brute force a password.
	- reCAPTCHA is a free CAPTCHA service from Google that helps protect websites from bots and malicious software.
- **Password policies**: organizations use password policies to standardize good password practices throughout the business.


## Network Security hardening
- Port filtering
- Network access privilege
- Encryption

Network hardening tasks are performed:
- Regularly (firewall rules maintenance, network log analysis, patch update, server backups)
- Once and updated as needed (Port filtering on firewalls, network access privileges, and encryption for communication.)

Network log analysis:
The process of examining network logs to identify events of interest.

SIEM (Security Information and Event Management tool)
An application that collects and analyzes log data to monitor critical activities in an organization.
using its Dashboard (A single pane of glass)
- **Chronicle** is a cloud-native tool designed to retain, analyze, and search data.
- **Splunk** is another common SIEM tool. Splunk offers different SIEM tool options: Splunk Enterprise and Splunk Cloud.

Port filtering
A firewall function that blocks or allows certain port numbers to limit unwanted communication. (Only ports that are needed are allowed)

Full packet capture devices allow you to record and analyze all of the data that is transmitted over your network. They also aid in investigating alerts created by an IDS.

An **intrusion detection system** (IDS) is an application that monitors system activity and alerts on possible intrusions. An IDS alerts administrators based on the signature of malicious traffic.

An **intrusion prevention system (IPS)** is an application that monitors system activity for intrusive activity and takes action to stop the activity.

| **Devices / Tools**                              | **Advantages**                                                                                                                                  | **Disadvantages**                                                                                                                                                             |
| ------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Firewall                                         | A firewall allows or blocks traffic based on a set of rules.                                                                                    | A firewall is only able to filter packets based on information provided in the header of the packets.                                                                         |
| Intrusion Detection System (IDS)                 | An IDS detects and alerts admins about possible intrusions, attacks, and other malicious traffic.                                               | An IDS can only scan for known attacks or obvious anomalies; new and sophisticated attacks might not be caught. It doesn’t actually stop the incoming traffic.                |
| Intrusion Prevention System (IPS)                | An IPS monitors system activity for intrusions and anomalies and takes action to stop them.                                                     | An IPS is an inline appliance. If it fails, the connection between the private network and the internet breaks. It might detect false positives and block legitimate traffic. |
| Security Information and Event Management (SIEM) | A SIEM tool collects and analyzes log data from multiple network machines. It aggregates security events for monitoring in a central dashboard. | A SIEM tool only reports on possible security issues. It does not take any actions to stop or prevent suspicious events.                                                      |

## Cloud hardning
In cloud network hardening we use a server baseline image for all server instances stored in the cloud.

### IAM (Identity Access management)
Is a collection of processes and technologies that helps organizations manage digital identities in their environment and authorizes how users can use different cloud resources.


CSP (Cloud Service Provider)

The **shared responsibility model** states that the CSP must take responsibility for security involving the cloud infrastructure, including physical data centers, hypervisors, and host operating systems. The company using the cloud service is responsible for the assets and processes that they store or operate in the cloud.

A **hypervisor** abstracts the host’s hardware from the operating software environment.
- hypervisors run on the hardware of the host computer. (VMware)
- hypervisors operate on the software of the host computer. (VirtualBox)

(CSPs) commonly use type one hypervisors.

Vulnerabilities in hypervisors or misconfigurations can lead to **virtual machine escapes (VM escapes)**. A VM escape is an exploit where a malicious actor gains access to the primary hypervisor, potentially the host computer and other VMs.

**Baselining** for cloud networks and operations cover how the cloud environment is configured and set up. A baseline is a fixed reference point. This reference point can be used to compare changes made to a cloud environment.


**Cryptography** uses encryption and secure key management systems to provide data integrity and confidentiality.

**Encryption** is the process of scrambling information into ciphertext, which is not readable to anyone without the encryption key.

Modern encryption relies on the secrecy of a key, rather than the secrecy of an algorithm.

**Cryptographic erasure** is a method of erasing the encryption key for the encrypted data. When destroying data in the cloud, more traditional methods of data destruction are not as effective.

**Crypto-shredding** is a newer technique where the cryptographic keys used for decrypting the data are destroyed.

Key Management:
- Trusted platform module (TPM). TPM is a computer chip that can securely store passwords, certificates, and encryption keys.
    
- Cloud hardware security module (CloudHSM). CloudHSM is a computing device that provides secure storage for cryptographic keys and processes cryptographic operations, such as encryption and decryption.