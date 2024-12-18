## Branches
**Git branches** are a fundamental concept in Git that allow you to diverge from the main line of development and continue to work without interfering with that main line. Think of a branch as a separate timeline of your project’s history. Branching in Git is a lightweight, versatile way to manage various aspects of your project’s development and collaboration.

## Listing branches
To list the branches you have locally on your machine you can use 
```bash
git branch
```
To list all the branches locally and remotely
```bash
git branch -a
```
To list only the remote branches
```bash
git branch -r
```

## New Branch
To create a new branch locally from the current working branch
```bash
git branch <new-branch-name>
```
> The new branch will include the commits of the current working branch

To switch to a local branch to make it the current use one
```bash
git checkout <new-branch-name>
```
We can merge the two above commands into one command by
```bash
git checkout -b <new-branch-name>
```

But to make a local branch from a remote branch
```bash
git checkout -t -b <new-branch> origin/<exitsted-remote-branch>
```
where `-b` to create a new branch and `-t` to track the remote branch (the Upstream)
## Rename Branch
To rename a local branch
```bash
git branch -m <old-branch> <new-name>
```

## Push Branch
 Pushing the branch means push it to a remote repository, so you can push a local branch by
```bash
git push -u origin <branch-name>
```
And this will make a new branch on the remote repo.

But if you want to push the changes of the tracked remote branch you can just use
``` shell
git push
```

## Delete Branch
To delete a local branch
```bash
git branch -d <branch-name>
```

## Sync remote branches
To delete the remote branches that is already deleted from the remote repo and make your local repo branch list up to date.
```bash
git fetch --prune
```
