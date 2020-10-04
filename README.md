# github-cheatsheet
github cheatsheet with specific use cases and examples

git version 2.28.0

`git version`

####
* stage part of a file
  `git add -patch <filename>`
* list deleted commit
  `git reflog`
* show difference history for a file
  `git log -p -- <filename>`
* change old commit message, in this example the 5 last commit
  `git rebase -i HEAD~4`
  change `pick` in front of the required commit to `reword` and save. another editor will popup to change the commit message
* squash commits
  `git rebase -i HEAD~4`
  change `pick` to `squash`
* get remote branches
  `git branch -r`
* get all branches
  `git branch -a`
* git clean up/garbage collection
  `git gc`
* reset last commit, keep changes unstaged
  `git reset --soft HEAD~1`
* go back from detached HEAD
  `git switch -` or `git switch <branch-name>`
* re-pull a force pushed branch.
  0. reset local branch back to where it starts to differ with the remote branch. for many cases, it may just be enough to reset it back to `master`. **WARNING** all changes made to this branch locally will be erased.
    `git reset --hard master`
  0. pull the changes from remote branch
    `git pull`
* rebase onto
  o---o---o---o---o  master
     \
      o---o---o---o---o  next
                       \
                        o---o---o  topic


  `git rebase --onto master next topic

  o---o---o---o---o  master
      |            \
      |             o'--o'--o'  topic
       \
        o---o---o---o---o  next
