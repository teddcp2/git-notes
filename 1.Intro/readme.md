
# 1.Intro

* Version Control System
* Tracking the changes, saving the checkpoints/commits to revert back... collaboration...

- checking version
  -  git --version

- Adding user name and email
    
    git config --global user.name "Your name"
    git config --global user.email "Yourname@mail.com"

  - [3 scopes](https://stackoverflow.com/a/66108560/12210002) >> system, global, local
  ```
    # There are 3 levels of git config; project, global and system.

    # project: Project configs are only available for the current project and stored in .git/config in the project's directory.
    # global: Global configs are available for all projects for the current user and stored in ~/.gitconfig.
    # system: System configs are available for all the users/projects and stored in /etc/gitconfig.

    # Create a project specific config, you have to execute this under the project's directory.
    $ git config user.name "John Doe"

    # Create a global config
    $ git config --global user.name "John Doe"

    # Create a system config
    $ git config --system user.name "John Doe"


  ```

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
  - initializing git repo on ur local folder] `git init`
  - command to tell the changed file names and new files - `git status`
  - Adding files to staging area - `git add file1 file2`
  - Committing to repo - `git commit -m "Inline MSG"`
  - checking logs -  `git log`  OR `git log --oneline`

- Commit in detail
  - Atomic commits [Keeping each commit focused on single feature/ bug fix]
  - Imperative Style for git commit comments e.g, make xyz do this rather than made xyz to do this
  - Changing the editor >> `git config --global core.editor "code --wait"`
  - modifying the commit msg typo or amending new files to previous commit ->> `git commit --amend`
  - ignore certain files with `.gitignore`

- [Branching](https://stackoverflow.blog/2021/04/05/a-look-under-the-hood-how-branches-work-in-git/)
  - viewing all branches `git branch`
  - creating branch > `git branch branch-name` 
  - switching branch > `git checkout existing-branc`h  OR `git switch existing branch-nam`e or `git switch -c "branch-name"`
  - deleting branch (Change your branch) >> `git branch -d name` or with Force >> `git branch -D name`
  - Rename branch (stay on the branch where u want to rename) >> `git branch -m name`
  - HEAD >> its kind of bookmark and it points to the current location of  active branch where the active branch points to the latest commit ([link1](https://stackoverflow.blog/2021/04/05/a-look-under-the-hood-how-branches-work-in-git/) and [link2](https://stackoverflow.com/a/2530000/12210002))
  - Switching branches with UnStaged changes - If same file got overwritten, git will produce a error while switching and suggesting to commit or stash them. For a new file , if you switch, that file will be added without any conflict/error.
  

- Merging
  -  different types : Recursive, Fast-Forward etc
  -  `git merge branch-name`
  - [Different Merging Strategy](https://stackoverflow.com/a/366940/12210002) and [Another link](https://www.atlassian.com/git/tutorials/using-branches/merge-strategy)

- Git Diff - [link](https://stackoverflow.com/a/1587952/12210002)
  - Comparing the changes between commits,branches, files, staging area and working directory
  - `git diff file` -- shows the changed content between the files in working directory and staging area
  - `git diff HEAD` [Differences from last commit with respect to working directory, both staged and unstaged]
  - `git diff` [Differences between the working directory and staging area... unstaged changes]
  - `git diff --staged` [Differences between staging area with commit]
  - for a Specific file >> `git diff filename`  ... similarly... `git diff --staged filename`, `git diff HEAD filename`
  - Across branches >> `git diff branch1 branch2`
  - Comapring commits >> `git diff commit1 commit2`

- Stashing
  - Stashing the unsaved changes in working + staging area
  - `git stash` , a shortcut to git stash save
  - `git stash pop`... bringing back the changes deleting from stash
  - `git stash apply`... same as pop, but the changes will stay in stash
  - Follows Stack Pattern FIFO
  - Viewing the contetns : `git stash list`
  - Applying particular stack : `git stash apply stash@{2}`
  - Dropping and clearing Stash : `git stash drop stash@{2}` , Dropping ALL : `git stash clear`
  
- Undoing Changes / Travelling back
  - git checkout commit  (Known as DETACHED HEAD.. not pointing to any  branch)
  - brining back to branch commit >> git switch branch-name  OR git switch -  OR creating another branch and committing, thn switching back
  - HEAD~1 refers the commit previous to recent commit
  
  - Discarding the changes u made on the file compared to previous commit >> `git checkout HEAD file` OR `git checkout -- file1 file2`
  - same thing with restore : `git restore file` OR to a particular commit : `git restore --source HEAD~1 file`
  - Unstaging changes with GIT : `git restore --staged file1` 
  
  - undoing commits with reset : `git reset HEAD~1` i,e it will delete the commit only, but the changes will be there...so you can create a new branch and commit..then come back to oringinal branch. So the changes will disappear.
  - OR in one command to delete the commit and discarding the changes --> `git reset --hard commit`
  - With Revert : `git revert commit-hash`. the difference between reset and revert is the earlier one deletes the commit while the latter creates a new commit ...

- Extra notes
  - [Guidance on Git](https://stackoverflow.com/q/315911/12210002)
  - understanding mixed, soft, hard of [git reset](https://stackoverflow.com/a/50022436/12210002)
  - understanding [git revert](https://stackoverflow.com/a/19032493/12210002)
  - [reset vs revert vs checkout](https://stackoverflow.com/a/8358039/12210002)
  - [reset vs revert](https://itnext.io/fixing-mistakes-using-git-reset-and-revert-3d68fab3176e)
  - [git diff](https://stackoverflow.com/a/1587952/12210002)
  - [HEAD](https://stackoverflow.com/a/2530000/12210002)
  - [Why Staging is required](https://stackoverflow.com/a/4878399/12210002)
  - [ git add . vs git add -A vs git add -u](https://stackoverflow.com/a/26039014/12210002)
  - [ git rebase vs merge ](https://www.atlassian.com/git/tutorials/merging-vs-rebasing#the-golden-rule-of-rebasing) and [Another link](https://stackoverflow.com/a/9147389/12210002)
  - [reset vs revert vs checkout -- 2](https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting)
  - [Git Merge Strategies](https://www.atlassian.com/git/tutorials/using-branches/merge-strategy)
  - 

