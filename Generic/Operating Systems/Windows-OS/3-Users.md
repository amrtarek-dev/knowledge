## User Structure

Windows uses a user structure that categorizes users with different access rights. The two most common categories are:

1. Administrators:
	- Have full control over the computer.
	- Can change system settings, install and uninstall programs, manage other user accounts, and perform many other tasks.
	- Administrators have the ability to modify sensitive system files and data, so this role should only be assigned to trusted individuals.

2. Standard Users:
	- Have basic permissions to use the computer.
	- Can run programs, open and edit files, and access the internet.
	- Cannot change system settings, install or uninstall programs, or manage other user accounts.
	- Standard users have limited permissions to help maintain the computer's security and stability.

Other User Types:
- Guest: A user type with limited permissions to temporarily use the computer.
- Assigned Access: A user type with special permissions to use specific programs or files.

### Managing User Accounts

The quickest way to manage accounts is to edit via Local Users and Groups.

Open the Start menu, type PowerShell, and open it.

In the prompt, type:

``` shell
lusrmgr.msc
```

In the window that appears, you can manage local users and groups.

You can change account types, activate/deactivate accounts, and do much more.

### User Account Control (UAC)

A built-in security feature in Microsoft Windows operating systems. UAC works by asking for your confirmation before performing operations that require administrative permissions on your computer. This helps to prevent errors caused by unauthorized changes or the installation of malicious software.

When a program attempts to perform an operation requiring administrative privileges (e.g., installing a program, changing system settings), the UAC window appears on the screen. You need to approve or deny this action.

Levels (from high to low):

- Always notify: The most secure option. You receive notifications for everything, including changes you make to system settings.
- Notify me only when programs try to make changes to my computer (default): You receive notifications for changes made by programs but not for changes you make yourself.
- Notify me only when programs try to make changes to my computer (do not dim my desktop): The least secure of the three notification options. The warning is the same as above, but the desktop remains usable when the UAC window is open.
- Never notify (UAC disabled): Not recommended. It disables all UAC warnings, making your system vulnerable.

Advantages

- Security: UAC helps prevent errors caused by unauthorized changes and the installation of malicious software.
- Control: Provides more control over operations requiring administrative privileges.
- User-Friendly: The UAC window allows you to understand what is happening and stop an operation before giving approval.

Disadvantages

- Inconvenience: UAC may frequently request approval, which can be annoying for some users.
- Incompatibility: Some programs may be incompatible with UAC and may not work correctly.
