# Git Commits

Commit is the saving point for the git, so every save moment has a commit message and commit tag.
When you make a commit, Git records the state of your files in the repository and creates a unique identifier for that specific state. This allows you to track changes, revert to previous versions, and collaborate with others effectively

## List commit
To list the commits you have on your branch you can use
```bash
git log
```

## Get latest commits
To get the latest commits from the upstream branch you can do so by:
```bash
git fetch
# or
git pull
```
`git fetch` vs `git pull` Both bring data from remote repositories, but `git fetch` is like previewing, while `git pull` is like downloading and updating your files in one go.

## Edit a commit message
You can edit a commit message in git by **--amend** command

```bash
git commit --amend -m "The new commit message"
```
this will change the commit message to the latest local commit, 
to just add file to commit and do not change the commit message you can use:
```bash
git commit --amend --no-edit
```

to change a really old commit message you can use **rebase** command, when you use rebase it will open an editor and then you can select the required commit first line from "pick" to "reword" or just "r", and then save.

```bash
git rebase -i HEAD~10
```

The rebase will rebase your current branch to the requested commit, then you can change the commit message by **--amend** command.
Once you finished you can rebase your branch to the latest commit by
```bash
git rebase --continue
```
Do so until it is back to the latest commits, then you need to force push it to the upstream to save the remote repo, do not worry we will cover `push` command in the next topic.