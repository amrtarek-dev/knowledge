# What is Git and how to start with it?

Git is a revision control system that lets track changes you make to your files over time. With Git you can revert to various states of your files (Like a time machine).

You can also make a **copy of your file**. make changes to that copy, and then merge these changes to the original copy, and it is not limited to using Git just for source code files, you can also use it to **keep track of text files or even images**, which means that **Git is not just for developers - anyone can find it helpful**.

## History of Git
Git is a revision control system that arose out of the **Linux kernel development community**, which had a very specialized need. As thousands of developers spread worldwide, in many different time zones, working on a very complicated project, it was important **to be able to coordinate all that work rationally** and not lose track of what was going on, So Git was designed for that purpose and it was and it has grown to be used by **millions of other projects today**.

## Start with Git
Git has two ways to deal with it:
- Command-line
- Gui

We will cover here the command line way because I believe that this is the best way to learn it.

First, you need to install Git on your machine and you can do so from [Git -Downloads](https://git-scm.com/downloads), So After installing git on your system you can initialize your project simply by running :
```bash
git init test-project
```
where test-project is your project name. that will initialize an empty git repository in your current directory, or if the project is hosted on a server you can get it by running:
``` bash
git clone [URL]
# or with specific ssh key
GIT_SSH_COMMAND="ssh -i ~/.ssh/id_rsa" git clone [URL]
```
where [URL] is the repository link, so once you finish this step you will have a .git folder in your directory which has the repo details and history.

## Configure Git
The next thing you will need to do is to set your username and email address. Git will use this information to identify who made specific changes to files.
- To set username and email run:
```bash
git config --local user.name "your username"
git config --local user.email "your email address"
```

**So know your repo is ready to have a file and track its change**

## Adding files to git
To track files and folders you have to add them to the Git repo as an initial version, so for Git files there are 4 states for any file or folder:
- Untracked
- Staged
- Modified
- Committed

### Untracked
Untracked files are the files in the same Git repo but the git repo doesn't track them, there are two ways to do so:
- By don't add it to the repo.
- Or by intentionally un-track these files by adding them to a file called **.gitignore**
You can know what is the tracked and untracked file by running:
```bash
git status
```

### Staged
When you want to add files to be tracked by Git or if the files are already tracked but you edited them (Modified them) you have to add them again to the Git repo, you can **add files one by one** by:
```bash
git add [file]
```
or you can **add all files** in the current directory by
```bash
git add *
```
To **list** the staged files and folders by 
```bash
git diff --staged
```
To **reset** the staged files but keep them as modified
```bash
git reset [file]
```
where [file] is the file you want to reset.

### Modified
When you edit a file that is already tracked by Git its status is changed to be **modified (M)**, so the Git repo notices a change in the file but you did not add it to the repo yet, so you can **list the Modified files** by:
```bash
git status
```
Or you **list only the change that happened to the files**
```bash
git diff
```

### Committed
Committed is the last stage for the files in the Git repo which is saving the changed files locally in the **local Git repo**, you can commit the stages files and folders to the current local repository by:
```bash
git commit -m "A commit message"
```
The **commit message** is a description of the edit you have made to the files and folders, and you can **list all commit messages** by:
```bash
git log
```

**We will discuss the best way to write the commit message in the comming topics so stay tuned**

