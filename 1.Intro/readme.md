
# 1.Intro

- checking version
  -  git --version

- Adding user name and email
    
    git config --global user.name "Your name"
    git config --global user.email "Yourname@mail.com"

- Terminal Commands
  - ls //OR// ls folder_name
  - cd directory
  - touch app.js red.py notes.txt
  - start . //OR// open .   [Opens in file Explorer]
  - cd .. , cd folder  
  - pwd
  - mkdir "folder name"
  - rm file    ,,,  rm -rf folder
  
- Basic [Adding and Committing]
  - git init
  - git status
  - git add file1 file2
  - git commit -m "Inline MSG"
  - git log  OR git log --oneline

- Commit in detail
  - Atomic commits [Keeping each commit focused on single feature/ bug fix]
  - Imperative Style for git commit comments e.g, make xyz do this rather than made xyz to do this
  - Changing the editor >> git config --global core.editor "code --wait"
  - modifying the commit msg typo or amending new files to previous commit ->> git commit --amend
  - ignore certain files with .gitignore

- Branching
  - viewing all branches `git branch`
  - creating branch > git branch branch-name 
  - switching branch > git checkout existing-branch  OR git switch existing branch-name or git switch -c "branch-name"
  - deleting branch (Change your branch) >> git branch -d name or with Force >> git branch -D name
  - Rename branch (stay on the branch where u want to rename) >> git branch -m name

- Merging
  -  different types : Recursive, Fast-Forward etc
  -  git merge branch-name
  - [Different Merging Strategy](https://stackoverflow.com/a/366940/12210002) and [Another link](https://www.atlassian.com/git/tutorials/using-branches/merge-strategy)

- Git Diff
  - Comparing the changes between commits,branches, files, staging area and working directory
  - git diff HEAD [Differences from last commit with respect to working directory, both staged and unstaged]
  - git diff [Differences between the working directory and staging area... unstaged changes]
  - git diff --staged [Differences between staging area with commit]
  - for a Specific file >> git diff filename  ... similarly... git diff --staged filename, git diff HEAD filename
  - Across branches >> git diff branch1 branch2
  - Comapring commits >> git diff commit1 commit2

- Stashing
  - Stashing the unsaved changes in working + staging area
  - git stash , a shortcut to git stash save
  - git stash pop... bringing back the changes deleting from stash
  - git stash apply... same as pop, but the changes will stay in stash
  - Follows Stack Pattern FIFO
  - Viewing the contetns : git stash list
  - Applying particular stack : git stash apply stash@{2}
  - Dropping and clearing Stash : git stash drop stash@{2} , Dropping ALL : git stash clear
  
- Travelling back
  - git checkout commit  (Known as DETACHED HEAD.. not pointing to any  branch)
  - brining back to branch commit >> git switch branch-name  OR git switch - 
  - HEAD~1 refers the commit previous to recent commit
  - Discarding the changes u made on the file compared to previous commit >> `git checkout HEAD file` OR `git checkout -- file1 file2`
  - same thing with restore : `git restore file` OR to a particular commit : `git restore --source HEAD~1 file`
  - Unstaging changes with GIT : `git restore --staged file1` 
  - undoing commits with reset : `git reset HEAD~1` i,e it will delete the commit only, but the changes will be there...so you can create a new branch and commit..then come back to oringinal branch. So the changes will disappear.
  - OR in one command to delete the commit and discarding the changes --> `git reset --hard commit`
  - With Revert : `git revert commit-hash`. the difference between reset and revert is the earlier one deletes the commit while the latter creates a new commit ...
  

