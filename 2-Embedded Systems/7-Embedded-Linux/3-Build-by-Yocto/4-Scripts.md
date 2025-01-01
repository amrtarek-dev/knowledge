The `scripts` directory contains various scripts that automate tasks and enhance the usability of the build environment.

## Images
list the available images from all meta layers
``` bash
find . -name "*.bb" | grep image
```

To list only the added to the layers.conf
``` bash
bitbake -s | grep image
```

## Layers
Add layers
``` bash
bitbake-layers add-layer <layer-path>
```
List Layers
``` bash
bitbake-layers show-layers
```
## Machines
list the current machines
``` bash
bitbake -e | grep "^MACHINE="
```

List the supported machines at specific layer
``` bash
find . -type f -name "*.conf" | grep "machine"
# OR
find meta-* -name "*.conf" | grep "machine"
```
### Recipes
You can list the recipes tasks by:
``` bash
bitbake -c listtasks core-image-minimal
```
And you can execute specific task by call it without `do_` part
``` bash
bitbake -c fetch busybox
```
Or 
``` bash
bitbake -c fetchall core-image-minimal
```
And to clean a built recipe:
``` bash
bitbake -c cleanall busybox
```

To debug a recipe
``` bash
bitbake -c devshell <recipe name>
```
