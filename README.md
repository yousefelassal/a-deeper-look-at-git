# [A Deeper Look at Git](https://www.theodinproject.com/lessons/javascript-a-deeper-look-at-git)

### Changing The Last Commit | `git commit --amend`
first update the staging area to include the missing file, and then replace the last commit with our new one to include the missing file.
  ```
  git add <file>
  git commit --amend
  ```
**only amend commits that have not been pushed anywhere**
