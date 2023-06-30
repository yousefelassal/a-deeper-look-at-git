# [A Deeper Look at Git](https://www.theodinproject.com/lessons/javascript-a-deeper-look-at-git)

### Changing The Last Commit | `git commit --amend`
first update the staging area to include the missing file, and then replace the last commit with our new one to include the missing file.
  ```
  git add <file>
  git commit --amend
  ```
**only amend commits that have not been pushed anywhere**

### Changing Multiple Commits | `rebase`
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
commits would get squashed together into a single commit
```
pick e30ff48 <msg>
squash 92aa6f3 <msg>
pick 05e5413 <msg>
```
this would squash the second commit into the first commit on the list
