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

if you want to remove the untracked files
``` bash
git clean -fd
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

If you want to undo change of files
``` bash
git checkout path/to/file
```
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


