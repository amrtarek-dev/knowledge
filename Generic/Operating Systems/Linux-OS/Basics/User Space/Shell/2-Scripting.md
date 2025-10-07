
Bash scripting allows us to automate frequently used commands, and customize commands for different scenarios using arguments and variables, often are in files ending with .sh (short for shell)

``` bash
nano first_script.sh
```

Every script should start from shebang. Shebang is a combination of some characters that are added at the beginning of a script, starting with `#!` followed by the name of the interpreter to use while executing the script.
## Shebang
`#!/bin/sh` is a comment which tells the shell which shell interpreter to use.
also can be `#!/bin/bash`