When Windows was first released, it used the FAT (File Allocation Table) file system. FAT was a simple and compatible file system but didn't support large files (over 4 GB) and didn't offer advanced security features.

In 1993, with the release of Windows NT 3.1, the NTFS (New Technology File System) was introduced. NTFS was designed to address the limitations of FAT. It supports large files, offers advanced security features such as file and folder permissions, and uses disk space more efficiently. NTFS is the default file system for Windows today.

In the early 2000s, portable storage devices like USB flash drives became popular. The FAT32 file system emerged as an ideal solution for portable storage devices. FAT32 is a more advanced file system than FAT and supports files larger than 4 GB.

In 2006, Windows Vista introduced the exFAT (Extended File Allocation Table) file system. exFAT was designed to replace FAT32 and supports files larger than 4 GB. While not as advanced as NTFS, it is simpler and more suitable for portable storage devices.

## NTFS

NTFS is known as a journaling file system. In the event of a failure, the file system can automatically repair folders/files on the disk using information stored in a journal file. This function is not possible with FAT.

NTFS was a significant development at a time when Windows' storage needs were growing and overcame many of FAT's limitations:

Security: NTFS offered a more robust security model by providing permissions to control file access.

Scalability: NTFS supported larger file sizes and drive capacities, accommodating more modern storage needs.

Reliability: NTFS provided journaling to enhance data integrity and recovery.

Features: NTFS offered additional functions such as file compression, encryption, and disk quotas to improve storage management and security.

As a result, NTFS remains a more modern, secure, and scalable file system compared to FAT and continues to be a fundamental component of Windows.

### Access Control List (ACL)

ACL stands for Access Control List. This list determines who can access a resource (file, folder, printer, network resource, etc.) on a computer system and what access permissions they have.

ACL allows system administrators and users to protect sensitive data and ensure that only authorized individuals can access specific resources.

In NTFS disks, access permissions for files and folders can be set.

The adjustable permissions are:

- Full control
- Modify
- Read and execute
- List folder contents
- Read
- Write

Viewing/Changing the Access Control List

1. Right-click the file or folder
2. Select Properties from the menu.
3. In the Properties window, click the Security tab.
4. In the Group or user names list, select the user, computer, or group whose permissions you want to view.

### Alternative Data Streams (ADS)

In the world of NTFS file systems, Alternative Data Streams (ADS) act like hidden compartments within files. NTFS allows files to have more than just the visible regular data.

Advantages:

ADS provides legitimate purposes for applications. Programs can use:

- Metadata such as thumbnail previews or document summaries for images.
- Non-critical information associated with the file.
- Security information about downloaded files.
- Information about where the file was downloaded from, etc.

Security Risks:

While ADS has valid uses, it can also be misused.

Malware can exploit ADS to hide malicious code within a file, making it challenging to detect using traditional methods.

### Shadow Copy

Shadow copy is a feature in Windows that allows you to create and store a copy of a file or folder at a specific point in time. This helps you restore files or folders if you accidentally delete or modify them.

Although it is not covered in detail, it should be noted that this feature is not a means of protection against ransomware attacks.

Malware developers are aware of the shadow copy feature in Windows and can write code to find and delete these files. This can make recovering from a ransomware attack impossible if you don't have an offline backup.