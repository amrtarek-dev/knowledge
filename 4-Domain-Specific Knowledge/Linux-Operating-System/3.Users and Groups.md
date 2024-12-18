When you have your Linux system you have to login using a username and password, and this calls authentication.

Each user is associated with a User ID (uid), and every process has been started has to have associated with UID of the user running the process.

> /etc/passwd maps usernames to uids

UID 0 is the root user, which can do almost anything on the system,
Each user belongs to one or more groups, with corresponding Group IDs (gid)

> /etc/group maps group name to gids


## Adding a New User
- adduser
- useradd
**`adduser`**: Adds a new user with the home directory and other basic configurations.
``` bash
sudo adduser <username>
```
**`useradd`**: Adds a user with more manual control over the options (without creating a home directory by default).
``` bash
sudo useradd <username>
```
To create a home directory, use:
``` bash
sudo useradd -m <username>
```

## Editing/Modifying a User
**`usermod`**: Modifies an existing user’s information (e.g., home directory, group, shell).
Change home directory:
``` bash
sudo usermod -d /new/home/directory <username>
```
Add the user to a group:
``` bash
sudo usermod -aG <group> <username>
```
Change the user’s shell:
``` bash
sudo usermod -s /bin/bash <username>
```

## Changing User Information
**`chfn`**: Change the user’s full name, phone number, etc.
``` bash
sudo chfn <username>
```
**`passwd`**: Change the password of a user.
``` bash
sudo passwd <username>
```

## Deleting a User
**`userdel`**: Deletes a user from the system.
``` bash
sudo userdel <username>
```
Remove the user's home directory and files:
``` bash
sudo userdel -r <username>
```

## Managing Groups
**`groupadd`**: Adds a new group.
``` bash
sudo groupadd <groupname>
```
**`groupdel`**: Deletes a group.
``` bash
sudo groupdel <groupname>
```
**`gpasswd`**: Used to add a user to a group.
``` bash
sudo gpasswd -a <username> <groupname>
```

## Viewing User Information
**`id`**: Shows user ID (UID) and group ID (GID).
``` bash
id <username>
```
**`getent`**: View user details from system databases.
``` bash
getent passwd <username>
```
**`finger`**: Displays user details like name, shell, and last login (if installed).
``` bash
finger <username>
```

## Switching Users
**`su`**: Switch to another user account.
``` bash
su - <username>
```
**`sudo`**: Execute a command as another user (typically root).
``` bash
sudo <command>
```


