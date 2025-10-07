There are many other advantages to using a CLI besides speed and efficiency. We will mention a few:

- **Lower resource usage**: CLIs require fewer system resources than graphics-intensive GUIs. In other words, you can run your CLI system on older hardware or systems with limited memory. If you are using cloud computing, your system will require lower resources, which in turn will lower your bill.
- **Automation**: While you can automate GUI tasks, creating a batch file or script with the commands you need to repeat is much easier.
- **Remote management**: CLI makes it very convenient to use SSH to manage a remote system such as a server, router, or an IoT device. This approach works well on slow network speeds and systems with limited resources.
we can only issue the commands within the Windows Path. You can issue the command `set` to check your path from the command line.

``` shell
set

ALLUSERSPROFILE=C:\ProgramData
APPDATA=C:\Users\user\AppData\Roaming
ChocolateyInstall=C:\ProgramData\chocolatey
CommonProgramFiles=C:\Program Files\Common Files
CommonProgramFiles(x86)=C:\Program Files (x86)\Common Files
CommonProgramW6432=C:\Program Files\Common Files
```

`ver`:  command to determine the operating system (OS) version

`systeminfo`: command to list various information about the system such as OS information, system details, processor and memory.

``` shell
systeminfo

Host Name:                 WINSRV2022-CORE
OS Name:                   Microsoft Windows Server 2022 Datacenter
OS Version:                10.0.20348 N/A Build 20348
OS Manufacturer:           Microsoft Corporation
OS Configuration:          Standalone Server
OS Build Type:             Multiprocessor Free
Registered Owner:          Windows User
Registered Organization:
```


First, you can pipe it through `more` if the output is too long. Then, you can view it page after page by pressing the space bar button. To demonstrate this, try running `driverquery` and compare it with running `driverquery | more`. In the latter, you can display the output page by page and you can exit it using `CTRL + C`.

- `help` - Provides help information for a specific command
- `cls` - Clears the Command Prompt screen.

## Network
`ipconfig` : check your network information
`ipconfig /all` for more information about your network configuration.

`ping`: Inspired by ping-pong, we send a specific ICMP packet and listen for a response. If a response is received, we know that we can reach the target and that the target can reach us.

`tracert` which stands for _trace route_. The command `tracert target_name` traces the network route traversed to reach the target. Without getting into more details, it expects the routers on the path to notify us if they drop a packet because its time-to-live (TTL) has reached zero.

`nslookup` It looks up a host or domain and returns its IP address. The syntax `nslookup example.com` will look up `example.com` using the default name server;
can be used with --type to specify a DNS record to retrieve it.

`netstat`This command displays current network connections and listening ports. A basic `netstat` command with no arguments will show you established connections
- `-a` displays all established connections and listening ports
- `-b` shows the program associated with each listening port and established connection
- `-o` reveals the process ID (PID) associated with the connection
- `-n` uses a numerical form for addresses and port numbers
``` shell
netstat -abon
```

## File and Disk Management
`cd` without parameters to display the current drive and directory. (like pwd in linux)

`dir` You can view the child directories. (like ls in linux)
- `dir /a` - Displays hidden and system files as well.
- `dir /s` - Displays files in the current directory and all subdirectories.

`tree`  to visually represent the child directories and subdirectories.

`mkdir`  stands for make directory
`rmdir` stands for remove directory

for Files:
`type` view content of text files

`copy` to copy file
`move` to move file
`del` to remove files
`erase` to remove files too


## Task and Process Management
`tasklist` : list the running processes
to filter on the process `tasklist /FI "imagename eq sshd.exe"`
Note that `/FI` is used to set the filter _image name equals_ `sshd.exe`

`taskkill` to terminate any task using its UID
- taskkill /PID 4567


## Others

- `chkdsk`: checks the file system and disk volumes for errors and bad sectors.
- `driverquery`: displays a list of installed device drivers.
- `sfc /scannow`: scans system files for corruption and repairs them if possible
- `shutdown /s` shutting down the system
	- `shutdown /r` to reboot the system
	- `shutdown /a` to cancel the shutdown/reboot process

It is important to remember all the commands covered in the previous tasks; moreover, it is equally important to know that `/?` can be used with most commands to display a help page.

In this room, we used the command `more` in two ways:

- Display text files: `more file.txt`
- Pipe long output to view it page by page: `some_command | more`