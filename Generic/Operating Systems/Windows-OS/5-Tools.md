System Configuration `msconfig.exe`  is for advanced troubleshooting
The utility has five tabs across the top. Below are the names for each tab. We will briefly cover each tab in this task. 

1. General
2. Boot
3. Services
4. Startup
5. Tools

Tools has a commands to run the configuration tools in windows with its description.

- `control.exe` for Control Panel
- `UserAccountControlSettings.exe` for UAC

## Computer Management
`compmgmt.msc` utility has three primary sections:
- System Tools
- Storage
- Services and Applications


## System Information
`msinfo32.exe`
The  information in **System Summary** is divided into three sections:

- **Hardware Resources**
- **Components**
- **Software Environment**

## Resource Monitor
`resmon.exe`  Resource Monitor displays per-process and aggregate CPU, memory, disk, and network usage information, in addition to providing details about which processes are using individual file handles and modules.

In the Overview tab, Resmon has four sections:

- **CPU**
- **Disk**
- **Network**
- **Memory**

## Registry Editor
`regedt32.exe` is a central hierarchical database used to store information necessary to configure the system for one or more users, applications, and hardware devices.
The registry contains information that Windows continually references during operation, such as:

- Profiles for each user
- Applications installed on the computer and the types of documents that each can create
- Property sheet settings for folders and application icons
- What hardware exists on the system
- The ports that are being used.


What is the **Trusted Platform Module** (**TPM**)?  

Per Microsoft, "_Trusted Platform Module (TPM) technology is designed to provide hardware-based, security-related functions. A TPM chip is a secure crypto-processor that is designed to carry out cryptographic operations. The chip includes multiple physical security mechanisms to make it tamper-resistant, and malicious software is unable to tamper with the security functions of the TPM_".

What is **BitLocker**?

Per Microsoft, "_BitLocker Drive Encryption is a data protection feature that integrates with the operating system and addresses the threats of data theft or exposure from lost, stolen, or inappropriately decommissioned computers_".

On devices with TPM installed, BitLocker offers the best protection.

Per Microsoft, "_BitLocker provides the most protection when used with a Trusted Platform Module (TPM) version 1.2 or later. The TPM is a hardware component installed in many newer computers by the computer manufacturers. It works with BitLocker to help protect user data and to ensure that a computer has not been tampered with while the system was offline_".

The removable drive on systems without a TPM version 1.2 or later typically contains a startup key. This key is essential for booting the system and ensures that the encrypted drive can be accessed securely.