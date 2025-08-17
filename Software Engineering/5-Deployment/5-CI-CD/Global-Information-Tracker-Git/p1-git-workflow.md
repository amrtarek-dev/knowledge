# Git workflow

Git, a distributed version control system, has become the industry standard for managing code changes and collaboration. However, mastering Git involves more than just knowing commands; it requires understanding the various workflows that can optimize your development process.

Let's jump into Git flow by giving you a reference point as you continue to explore and leverage Git for your version control needs.
``` mermaid
%%{
  init: {
    "theme": "dark"
  }
}%%
sequenceDiagram
 Untracked->>Staged {Index}: git add
 Staged {Index}->>Local Repo {HEAD}: git commit -m "Message"
 Untracked->>Local Repo {HEAD}: git commit -a -m "Message"
 Local Repo {HEAD}->>Remote Repo: git push
 Remote Repo->>Local Repo {HEAD}: git featch
 Local Repo {HEAD}->>Staged {Index}: git merge
 Remote Repo->>Staged {Index}: git pull
 
 Note over Untracked,Remote Repo: Get the differences in the files
 
 Untracked->Staged {Index}: git diff
 Staged {Index}->Local Repo {HEAD}: git diff --staged [<commit>]
 Staged {Index}->Local Repo {HEAD}: git diff --cached [<commit>]
 Untracked->Local Repo {HEAD}: git diff <commit or branch>
```

## Get start

`git init` Kick things off with this command that creates a new git repository right where you are.

`git clone <repo>` want to get cracking on an existing project? This command copies it over to your local machine.

## Making Changes

`git status` Take a quick peek at what's changed with this command. it's good practice to check in before and after you make changes.

`git add <file-name>` Made some tweaks? Stage them for a commit with this command that adds your files to the lineup.

`git commit -m "Commit message"` Seal the deal on your changes with a commit and a handy message to remind you what you did.

## Branching out

`git branch` Curious about your branches? List them all out with this simple command

`git branch <branch-name>` Grow your project with a new branch using this command.

`git checkout <branch-name>` Jump over to another branch to keep working seamlessly

`git merge <branch-name>` Done with changes on your side branch? Bring them back to the main branch with a merge

## Working with Remotes

`git push origin <branch-name>` Send your latest commits up to the cloud with this push command.

`git pull`  Stay up-to-date with the rest of the team's work by pulling in their changes.

`git remote -v` Check your connections with this command that lists remote repositories linked to your local repo.

## Important Differences
`git fetch` vs `git pull` Both bring data from remote repositories, but `git fetch` is like previewing, while `git pull` is like downloading and updating your files in one go.

`git merge` vs `git rebase` Both integrate changes from one branch to another, but `git merge` makes a new commit for it, while `git rebase` keeps your history neat and tidy.

`git reset` vs `git revert` Need to backtrack? Use `git reset` to discard changes to `git revert` to undo while keeping your commit history intact.