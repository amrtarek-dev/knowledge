A **Git patch** is a file that contains the differences (or "diffs") between two versions of a repository's files.
A patch includes the exact changes made to lines of code, making it useful for applying updates, fixes, or new features to other branches or different repositories.

## Create Patch
There are 2 ways to make patch in Git
1. git diff
2. git format-patch

`git diff` (only the current change)
``` bash
git diff > some-changes.patch
```
`format-patch` between commits
- the latest commit
``` bash
git format-patch -1 HEAD
```
- for a range of commits
``` bash
git format-patch <start_commit>..<end_commit>
```
## Apply Patch
There are 2 ways to apply patches
1. git apply
2. git am (apply multiple)

For a single patch
``` bash
git apply your_patch_name.patch
```
For multiple patches
``` bash
git am *.patch
```