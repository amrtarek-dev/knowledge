# Git Push
Push command is used to upload local repository content to a remote repository. When you have made changes to your local repository (such as new commits) and want to share those changes with others or save them on a remote server, you use `git push`.
## Push a commit

To push the current staged changes you can use:
``` bash
git push
```

To edit the last commit you can use: 
```bash
git commit --amend
```

And you have to use `force` push incase you need to push the edited commit to the remote repo.
``` bash
git push --force
```

## Delete Pushed commit
To delete the last commit that has been pushed to the remote repo
```bash
git reset --hard HEAD~1
git push origin --force HEAD
```
If you want to delete the last five commits
```bash
git reset --hard HEAD~5
git push origin --force HEAD
```
If you want to remove a specific commit by it commit id
```bash
git reset --hard <sha1-commit-id>
git push --forced HEAD
```
Where < sha1-commit-d > is the commit id, that you can git by `git log`

## Pull commit
To update your current repo with the latest update from the remote repo, you can use:
```bash
git pull
```
and if it was already forced push, you can pull it by
```bash
git pull --rebase
```


> Push with specific ssh key by
``` bash
git config core.sshCommand "ssh -i ~/.ssh/your_specific_key"
```

## Edit the last commit
Edit the last files
``` bash
git commit --amend
```
Edit only the commit message without files change
``` bash
git commit --amend --no-edit
```
Edit the Author
``` bash
git commit --amend --no-edit --author "Amr Tarek <amr.tarek@example.com>"
```
> You have to force push after using `--amend` by using `git push --force`