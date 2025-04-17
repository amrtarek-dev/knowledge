# How to make a remote repo on Shared host
How to making a remote repository on remote server or shared server (shared host like Hostgator for example) and make it works as a Git server.

## 1. SSH key:
At the beiging you have to have a public ssh key to connect to the server via ssh rather than username and password.

### SSH generating:
Assumption that you have ssh client and have your public key, if not you can see how to do so from [SSH client configuration](https://www.varapps.com).
- then copy your ssh public key from your local machine (~/.ssh/id_rsa.pub) into your server (~.ssh/authorized_keys) file and if the file is not exist make it, then copy it.

## 2. Server side
In case shared server or a local server the implementation will not different.
- Go to the folder where you want to use it as git repo (you can name it with *.git or any other file) then run this command:
``` bash 
git init --bare
```
this will initalize a git repo on current folder, and you can find multiple files have been created.
- Go to folder called "**hooks**" and creat file "**post-receive**" then add this line to it
``` bash
cd hooks
echo "GIT_WORK_TREE=../ git checkout -f" > post-receive
```
this will allow push and clone from the repo, then give an executable permission for the file by
``` bash
chmod +x post-receive
```

## 3. Local machine

**Warning**: if you try to clone the repo before the first push it will not work until the first push, (You always can try it :) )

#### Make your local repo:
Go to the directory of your project and run the following commands in the bash shell terminal
``` bash
git init
git add -A
git config --local user.email "youremail@example.com"
git config --local user.name "Your Name"
git commit -m "init commit"
```
Now your repo is ready to be pushed

#### Push the repo
- Add a remote point to your repo
``` bash
git remote add origin ssh://user-name@your-domain.com:port-number/full/path/www/your-domain.com
git push -u origin master
```
Don't forget to replace 
- "user-name" with your remote machine user name
- "your-domain" with your remote machine domain.
- "port-number" with the ssh port number
- "full/path/www/your-domain.com" with the full remote repo path, you can get it by "pwd" from the repo folder.

#### clone the repo

``` bash
git clone ssh://user-name@your-domain.com:port-number/full/path/www/your-domain.com
```

And now you are ready to use your remote repo as normal repo on github for example but on your server.