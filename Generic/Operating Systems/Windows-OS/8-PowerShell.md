PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework.”

PowerShell is a powerful tool from Microsoft designed for task automation and configuration management. It combines a command-line interface and a scripting language built on the .NET framework.

Unlike older text-based command-line tools, PowerShell is object-oriented, which means it can handle complex data types and interact with system components more effectively.

Initially exclusive to Windows, PowerShell has lately expanded to support macOS and Linux, making it a versatile option for IT professionals across different operating systems.

To fully grasp the power of PowerShell, we first need to understand what an **object** is in this context.

In programming, an **object** represents an item with **properties** (characteristics) and **methods** (actions). For example, a `car` object might have properties like `Color`, `Model`, and `FuelLevel`, and methods like `Drive()`, `HonkHorn()`, and `Refuel()`.

Similarly, in PowerShell, objects are fundamental units that encapsulate data and functionality, making it easier to manage and manipulate information. An object in PowerShell can contain file names, usernames or sizes as data (**properties**), and carry functions (**methods**) such as copying a file or stopping a process.

The traditional Command Shell’s basic commands are text-based, meaning they process and output data as plain text. Instead, when a **cmdlet** (pronounced _command-let_) is run in PowerShell, it returns objects that retain their properties and methods. This allows for more powerful and flexible data manipulation since these objects do not require additional parsing of text.

## Basic Syntax: Verb-Noun

As previously mentioned, PowerShell commands are known as `cmdlets` (pronounced `command-lets`). They are much more powerful than the traditional Windows commands and allow for more advanced data manipulation.

Cmdlets follow a consistent `Verb-Noun` naming convention. This structure makes it easy to understand what each cmdlet does. The `Verb` describes the action, and the `Noun` specifies the object on which action is performed. For example:

- `Get-Content`: Retrieves (gets) the content of a file and displays it in the console.
- `Set-Location`: Changes (sets) the current working directory.

`Get-Command` to list all available cmdlets,
- to filter: 
	- `Get-Command -CommandType "Function"`
	- `Get-Command -Name Remove*`

`Get-Help`  it provides detailed information about cmdlets, including usage, parameters, and examples. It’s the go-to cmdlet
- `Get-Help Get-Date`
- `Get-Help Get-Date -examples`  to the command displayed above, we will be shown a list of common ways in which the chosen cmdlet can be used.


### PowerShell Alias
PowerShell includes aliases:
 `dir` -> `Get-ChildItem`
 `cd` -> `Set-Location`
You can list all alias by `Get-Alias`

### Download Cmdlets
 PowerShell is the possibility of extending its functionality by downloading additional cmdlets from online repositories

To search for modules (collections of cmdlets) in online repositories like the PowerShell Gallery, we can use `Find-Module`.
- `Find-Module -Name "PowerShell*"`

And to install the module `Install-Module`
- `Install-Module -Name "PowerShellGet"`


## File system
- `Get-ChildItem` like ls in linux, you can provide --Path to specify the list
- `Set-Location` like cd in linux, you should provide --Path
	- `Set-Location -Path ".\Documents"`
- `New-Item` create a new file or directory
	- `New-Item -Path ".\captain-cabin\captain-wardrobe" -ItemType "Directory"`
	- New-Item -Path ".\captain-cabin\captain-wardrobe\captain-boots.txt" -ItemType "File"
- `Remove-Item` remove file or directory
	- `Remove-Item -Path ".\captain-cabin\captain-wardrobe\captain-boots.txt"`
	- `Remove-Item -Path ".\captain-cabin\captain-wardrobe"`
- `Copy-Item` to copy item or directroy
	- `Copy-Item -Path .\captain-cabin\captain-hat.txt -Destination .\captain-cabin\captain-hat2.txt`
- `Get-Content` to get content of file, like `cat` in linux
	- `Get-Content -Path ".\captain-hat.txt"`

## Piping, Filtering and sorting data
**Piping** is a technique used in command-line environments that allows the output of one command to be used as the input for another.

`Get-ChildItem | Sort-Object Length`

`Get-ChildItem` retrieves the files (as objects), and the pipe (`|`) sends those file objects to `Sort-Object`, which then sorts them by their `Length` (size) property. This object-based approach allows for more detailed and flexible command sequences.

`Get-ChildItem | Where-Object -Property "Extension" -eq ".txt"`

`Where-Object` filters the files by their `Extension` property, ensuring that only files with extension equal (`-eq`) to `.txt` are listed.

The operator `-eq` (i.e. "**equal to**") is part of a set of **comparison operators** that are shared with other scripting languages (e.g. Bash, Python). To show the potentiality of the PowerShell's filtering, we have selected some of the most useful operators from that list:

- `-ne`: "**not equal**". This operator can be used to exclude objects from the results based on specified criteria.
- `-gt`: "**greater than**". This operator will filter only objects which exceed a specified value. It is important to note that this is a strict comparison, meaning that objects that are equal to the specified value will be excluded from the results.
- `-ge`: "**greater than or equal to**". This is the non-strict version of the previous operator. A combination of `-gt` and `-eq`.
- `-lt`: "**less than**". Like its counterpart, "greater than", this is a strict operator. It will include only objects which are strictly below a certain value.
- `-le`: "**less than or equal to**". Just like its counterpart `-ge`, this is the non-strict version of the previous operator. A combination of `-lt` and `-eq`.

`Get-ChildItem | Where-Object -Property "Name" -like "ship*"`

`Select-Object` is used to select specific properties from objects or limit the number of objects returned.
`Get-ChildItem | Select-Object Name,Length`

multiple piping:
`Get-ChildItem | Sort-Object Length -Descending | Select-Object -First 1`

`Select-String` This cmdlet searches for text patterns within files, similar to `grep` in Unix-based systems or `findstr` in Windows Command Prompt.
`Select-String -Path ".\captain-hat.txt" -Pattern "hat"`


## System and Network

`Get-ComputerInfo` : retrieves comprehensive system information, including operating system information, hardware specifications, BIOS details, and more. It provides a snapshot of the entire system configuration in a single command.

`Get-Localuser`: lists all the local user accounts on the system.

`Get-NetIPConfifuration` like the `ipconfig` command, provides detailed information about the network interfaces on the system, including IP addresses, DNS servers, and gateway configurations.

`Get-NetIPAddress` will show details for all IP addresses configured on the system, including those that are not currently active.



## Real-time analysis

`Get-Process` provides a detailed view of all currently running processes, including CPU and memory usage, making it a powerful tool for monitoring and troubleshooting.

`Get-Service` allows the retrieval of information about the status of services on the machine, such as which services are running, stopped, or paused.

`Get-NetTCPConnection` displays current TCP connections, giving insights into both local and remote endpoints. This cmdlet is particularly handy during an incident response or malware analysis task, as it can uncover hidden backdoors or established connections towards an attacker-controlled server.

`Get-FileHash` for generating file hashes, which is particularly valuable in incident response, threat hunting, and malware analysis, as it helps verify file integrity and detect potential tampering.


## Scripting

`Invoke-Command` is essential for executing commands on remote systems, making it fundamental for system administrators, security engineers and penetration testers

``` shell
Get-Help Invoke-Command -examples

-- Example 1: Run a script on a server --
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01

-- Example 2: Run a command on a remote server --
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }

```