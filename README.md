# [A Deeper Look at Git](https://www.theodinproject.com/lessons/javascript-a-deeper-look-at-git)

### Changing The Last Commit | `git commit --amend`
first update the staging area to include the missing file, and then replace the last commit with our new one to include the missing file.
  ```
  git add <file>
  git commit --amend
  ```
**only amend commits that have not been pushed anywhere**

## Changing Multiple Commits | `rebase`
`git rebase -i HEAD~2` would allows us to edit the last two commits.
```
pick abc560f <msg>
pick c27a76d <msg>
```
changing the word `pick` to be `edit` would allow us to use commit, but stop for amending
```
We can amend the commit now, with
       git commit --amend
Once we're satisfied with the changes, run
       git rebase --continue
```
### Squashing Commits | `squash`
using the `rebase` tool change `pick` to `squash` for the commits we want to _squash_ together into a single commit
```
pick e30ff48 <msg>
squash 92aa6f3 <msg>
pick 05e5413 <msg>
```
this would squash the second commit into the first commit on the list
### Splitting Up a Commit | `reset`
using the `rebase` tool change `pick` to `edit` for the commit we’re going to split, then we will run `git reset`, which will reset the current branch by pointing HEAD at where we specified. At the same time, git reset also updates the index (the staging area) with the contents of wherever HEAD is now pointed.

- `git reset --soft` would only perform the first part of git reset where the HEAD is moved to point somewhere else.
- `git reset --hard` would perform all the steps of git reset, moving the HEAD and updating the index, but it also updates the working directory.

  (A hard reset overwrites the files in the working directory to make it look exactly like the staging area of wherever HEAD ends up pointing to)
```
git reset HEAD^
git add <file> && git commit -m <msg>
git add <file> && git commit -m <msg>
```
this would resets the commit to the one right before HEAD. This allows us to add the files individually, and commit them individually.

## Resources
- [Think Like a Git](https://think-like-a-git.net/)
- [Git Best Practices](http://sethrobertson.github.io/GitBestPractices/)
- [Git Cheat Sheet](https://training.github.com/downloads/github-git-cheat-sheet/) | Github
