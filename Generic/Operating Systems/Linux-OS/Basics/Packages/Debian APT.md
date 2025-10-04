APT (Advanced Package Tool)

APT (Advanced Package Tool) is a powerful tool used to manage software packages in Debian-based Linux distributions such as Ubuntu.

Install package
``` bash
sudo apt install <package-name>
```

update package lists
``` bash
sudo apt update
```

List Installed packages
``` bash
apt list --installed
```

Search in package lists
``` bash
sudo apt search htop
```

The `apt search` command supports regular expressions. 
For example, to search for packages starting with htop, you could do:
``` bash
sudo apt search ^htop
```

Remove package
``` bash
sudo apt remove <package-name>
```
The **remove** command does not delete the configuration files and deb files for **htop**. To remove those as well, you would use the **purge** command.

``` bash
sudo apt purge <package-name>
```