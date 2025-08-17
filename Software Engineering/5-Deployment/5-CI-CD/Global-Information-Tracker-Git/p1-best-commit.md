**Commit message** is a description of what the contributors to the repository did and it shows whether a developer is a **good collaborator**, so it is a crucial skill for any developer to write a good Commit message.


## The six rules
We have 6 rules for writing a good git commit message
- Split it to title and body with a blank line.
- (Title) Use the imperative mood in the title.
- (Title) Limit the title to 50 characters.
- (Title) Capitalize the title and do not end it with a period.
- (Body) Use the body to explain what and why vs. how.
- (Body) Limit the body lines to 72 characters

### 1) Title and body
Firstly, not every commit requires both a title and a body, sometimes a single line is fine, especially when the change is so simple that no further context is necessary, like fixing a typo for example, And this will be easy to commit by the **git commit -m** command :
```bash
$ git commit -m "Fix typo in the README.md file"
```


But if the edit is large and you need to add more details, you have to split the commit message into two parts:
- The Title
- The body

Commit messages with bodies are not so easy to write with the **-m** option, so it is better to write it in a text editor like **vim** for example, In any case, the separation of body from title pays off when browsing the log.

```bash
$git log
commit 42e23bdjhweh2323450934n34345jn345gh3be
Author: Amr <hi@amrtarek.dev>
Date: Fri Jan 01 00:00:00 1982 -0200

  Derezz the master control program

  MCP turned out to be evil and had become intent on world domination.
  This commit throws Tron's disc into MCP (causing its de-resolution)
  and turns it back into a chess game.
```
Split the title and body with a blank line will make it suitable for the git command **git log --oneline** which prints out just the title line
```bash
$ git log --oneline
42e23b Derezz the master control program
```
Or **git shortlog** which groups commits by the user, and shows only the title line

```bash
$git shortlog
Kevin (1):
        Add Testcases unit testing

Amr (3):
        Rename chess program to "MCP"
        Modify chess program
        Upgrade chess program
```

### 2) Imperative Title
Imperative mood means "Order or command instruction", like **Clean your room**, or **Close the door**, one reason for this is that **Git itself uses the imperative whenever it creates a commit on your behalf** for example, the default message that it makes when you use **git merge** is
```bash
Merge branch 'Develop'
```
To make it easy to use, the title should always be able to complete the following sentence:
- if applied, this commit will **your title line here**

for example
- If applied, this commit will **Remove deprecated methods**
- It applied, this commit will **Release version 1.0.0**

>Remember: Use of the imperative is important only in the body line, you can relax this restriction when you are writing the body.

### 3) 50 characters for Title
50 characters is not a hard limit, just a rule of thumb, that will ensure that the title is readable, and forces the author to think for a moment about the most concise way to explain what's going on.

>If you are having a hard time summarizing, you might be committing too many changes at once, it is recommended to make atomic commits to be easy to track and revert in case of problems.

### 4) Capitalize Title, no end period
This is as simple as it sounds, begin all title lines with capital and do not end them with periods, because we are trying to keep them to 50 characters or less.
```bash
Adding a GUI layer
```

### 5) Body to explain what, why
Use the body if you need to write more details about your commit, like what has been changed and why, this will save a lot of time figuring it out from the code again.
This commit from Bitcoin Core is a great example of explaining what changed and why:
```bash
commit eb0b56b19017ab5c16c745e6da39c53126924ed6
Author: Pieter Wuille <pieter.wuille@gmail.com>
Date:    Fri Aug 1 22:57:55 2014 +0200

    Simplify serialize.h's exception handling

    Remove the 'state' and 'exceptmask' from serialize.h's stream
    implementations. as well as related methods.

    As exceptmask always included 'failbit', and setstate was always
    called with bits = failbit, all it did was immediately raise an
    exception. Get rid of those variables, and replace the setstate
    with direct exception throwing (which also removes some dead
    code).

```

### 6) 72 characters for body line
The recommendation is to do this at 72 characters so that Git has plenty of room to indent text while keeping everything under 80 characters. A good text editor can help here, it;s easy to configure Vim to wrap text at 72 characters when you are writing a Git commit.


**So,  good practice is producing great quality, so by implementing these rules you will get great results for your Git to commit messages.**
