**BitBake** is the build engine and task scheduler that automates the process of compiling, assembling, and creating software packages.

There are 4 components bitbake dealing with:
1. **Images:** End products of the build, such as complete Linux images or packages, which are defined by special recipe types (e.g., `core-image-minimal`).
2. **Layers:** Collections of recipes, configuration files, and other metadata. Layers organize the build metadata by functionality, like board support, applications, or configuration.
3. **Recipes (.bb files):** Define instructions on how to build a specific software component, including where to fetch the source, dependencies, build steps, and packaging.
4. **Tasks and Dependencies:** BitBake breaks down the build process into tasks, such as fetching, configuring, compiling, and installing. It then schedules and runs tasks based on dependencies.

## bitbake
To use bitbake :
``` bash
bitbake --help
```
will list 6 categories:
### General & image
``` bash
-u UI # user interface
--version # version
-h # help message
```

### Execution control
``` bash
-n # dry run
-k # continue as much as possible
-p # parse only
-P # profile the command and save reports
```

### Logging
``` bash
-D # debug level
-v # verbose 
-q # quiet
```

### Server
``` bash
-B # bind the name/address for the bitbake
-m # terminate any running bitbake server
```

### Configuration
``` bash
-r # prefile
-R # postfile
```


