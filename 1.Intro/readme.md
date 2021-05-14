
### 1.Intro

* Distributed  Version Control System
* Tracking and managing the changes, saving the checkpoints/commits to revert back... collaboration...combining.. versioning
* Ex: in a video game, if u die, u can reborn to the previuos saved check-poiint.. u won't start from beginning 
* [Git vs github](https://stackoverflow.com/a/11820206/12210002) and [link2](https://stackoverflow.com/q/13321556/12210002)
* getting help : `git help init` or `git init -h`
* checking version
  -  git --version
*  Adding user name and email
  ```  
    git config --global user.name "Your name"
    git config --global user.email "Yourname@mail.com"
  ```
* [3 scopes](https://stackoverflow.com/a/66108560/12210002) >> system, global, local
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

    >> Local has the highest precendence and system has the lowest...


  ```

### Basic  Terminal Commands
  - ls //OR// ls folder_name
  - cd directory
  - touch app.js red.py notes.txt
  - start . //OR// open .   [Opens in file Explorer]
  - cd .. , cd folder  
  - pwd
  - mkdir "folder name"
  - rm file    ,,,  rm -rf folder

### Basic [Adding and Committing]
  - initializing git repo on ur local folder] `git init`
  - command to tell the changed file names and new files - `git status`
  - Adding files to staging area - `git add file1 file2`
  - Committing to repo - `git commit -m "Inline MSG"`
  - checking logs -  `git log`  OR `git log --oneline` or `git log --graph --oneline --decorate --all`
  - To see all the remote/local logs , we can use `git log --all` or to see a remote branch logs `git log origin/master`

###  Commit in detail
  - Atomic commits [Keeping each commit focused on single feature/ bug fix]
  - Imperative Style for git commit comments e.g, make xyz do this rather than made xyz to do this
  - Changing the editor >> `git config --global core.editor "code --wait"`
  - modifying the commit msg typo or amending new files to previous commit ->> `git commit --amend`
  - ignore certain files with `.gitignore`

### Branching 
  - Allows us to create  a alternative timeline to work on our tasks separately...
  -  [How Branches work??](https://stackoverflow.blog/2021/04/05/a-look-under-the-hood-how-branches-work-in-git/)
  -  Each commit contains a unique id, parent commit id (Pointer) and message... `old2 <- old1 <- new `
  - viewing all branches `git branch` , Seeing Remote/tracking branches`git branch -r`.. to show all `git branch --all`
  - creating branch > `git branch branch-name` 
  - switching branch > `git checkout existing-branch`  OR `git switch existing-branch-name` or `git switch -c "branch-name"`
  - deleting branch (Change your branch, don't stay on that branch which u want to delete) >> `git branch -d namex` or with Force >> `git branch -D name`
  - Rename branch (stay on the branch where u want to rename and delete) >> `git branch -m name`

  - HEAD >> its kind of active bookmark and it points to the current location of  active branch where the active branch points to the latest commit `Simply the opened bookmark page (HEAD) among all the bookmarks(branches) ` ([link1](https://stackoverflow.blog/2021/04/05/a-look-under-the-hood-how-branches-work-in-git/) and [link2](https://stackoverflow.com/a/2530000/12210002))
  
  - Switching branches with UnStaged changes - If same file got overwritten, git will produce a error while switching and suggesting to commit or stash them. For a new file , if you switch, that file will be added without any conflict/error.
  
### Merging
  - we merge branches , not specific commits... and we always merge to current HEAD branch...
  -  different types : Recursive (creates a merge Commit when u have a new commit that branch does not know), Fast-Forward etc
  -  `git switch branch; git merge branch-name-FromWhere-u-want to merge-here`
  - [Different Merging Strategy](https://stackoverflow.com/a/366940/12210002) and [Another link](https://www.atlassian.com/git/tutorials/using-branches/merge-strategy)
  - [Merging remote branch locally](https://stackoverflow.com/q/21651185/12210002)
  

### Git Diff - 
  - [link](https://stackoverflow.com/a/1587952/12210002)
  - Comparing the changes between commits,branches, files, staging area and working directory
  - `git diff file` -- shows the changed content between the files in working directory and staging area
  - `git diff HEAD` [Differences from last commit with respect to working directory, both staged and unstaged]
  - `git diff` [Differences between the working directory and staging area... unstaged changes]
  - `git diff --staged` [Differences between staging area with commit]
  - for a Specific file >> `git diff filename`  ... similarly... `git diff --staged filename`, `git diff HEAD filename`
  - Across branches >> `git diff branch1 branch2`
  - Comapring commits >> `git diff commit1 commit2`

### Stashing
  - Stashing the unsaved changes in working + staging area
  - `git stash` , a shortcut to git stash save
  - `git stash pop`... bringing back the changes deleting from stash
  - `git stash apply`... same as pop, but the changes will stay in stash
  - Follows Stack Pattern FIFO
  - Viewing the contetns : `git stash list`
  - Applying particular stack : `git stash apply stash@{2}`
  - Dropping and clearing Stash : `git stash drop stash@{2}` , Dropping ALL : `git stash clear`
  
### Undoing Changes / Travelling back
  - git checkout commit  (Known as DETACHED HEAD.. not pointing to any  branch)
  - brining back to branch commit >> git switch branch-name  OR git switch -  OR creating another branch and committing, thn switching back
  - HEAD~1 refers the commit previous to recent commit
  
  - Discarding the changes u made on the file compared to previous commit >> `git checkout HEAD file` OR `git checkout -- file1 file2`
  - same thing with restore : `git restore file` OR to a particular commit : `git restore --source HEAD~1 file`
  - Unstaging changes with GIT : `git restore --staged file1` 
  
  - undoing commits with reset : `git reset HEAD~1` i,e it will delete the commit only, but the changes will be there...so you can create a new branch and commit..then come back to oringinal branch. So the changes will disappear.
  - OR in one command to delete the commit and discarding the changes --> `git reset --hard commit`
  - With Revert : `git revert commit-hash`. the difference between reset and revert is the earlier one deletes the commit while the latter creates a new commit ...




### Rebasing
- [Rebasing vs merging](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
- [Pull with Rebase](https://stackoverflow.com/a/36148845/12210002)
- [visual difference between merge and rebase](https://stackoverflow.com/a/16666418/12210002)
- [atlassian note on rebase](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
- [link1](https://nathanleclaire.com/blog/2014/09/14/dont-be-scared-of-git-rebase/)
- [interactive rebase](https://stackoverflow.com/a/41464876/12210002)
- [Squashing with Rebase](https://stackoverflow.com/a/5201642/12210002)
- [Squashing with Merge](https://stackoverflow.com/a/5309051/12210002)

### Git workfllows
- [Atlassian site](https://www.atlassian.com/git/tutorials/comparing-workflows) 
- [link2](https://buddy.works/blog/5-types-of-git-workflows)


1. Forking
   - [forking vs branching](https://stackoverflow.com/a/3611349/12210002)
   - [description](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow)


2. GitFlow workflow
   - [feature vs release vs hotfix branch](https://stackoverflow.com/a/58096993/12210002) and [hostfix branch](https://stackoverflow.com/a/46912005/12210002)
   - [Description](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

3. Centralized workflow
4. Feature branch workflow...
  
### Extra notes
  - [Guidance on Git](https://stackoverflow.com/q/315911/12210002)
  - understanding mixed, soft, hard of [git reset](https://stackoverflow.com/a/50022436/12210002)
  - understanding [git revert](https://stackoverflow.com/a/19032493/12210002) and [2](https://stackoverflow.com/a/19032678/12210002)
  - [reset vs revert vs checkout](https://stackoverflow.com/a/8358039/12210002)
  - [reset vs revert](https://itnext.io/fixing-mistakes-using-git-reset-and-revert-3d68fab3176e)
  - [git diff](https://stackoverflow.com/a/1587952/12210002)
  - [HEAD](https://stackoverflow.com/a/2530000/12210002)
  - [Why Staging is required](https://stackoverflow.com/a/4878399/12210002)
  - [ git add . vs git add -A vs git add -u](https://stackoverflow.com/a/26039014/12210002)
  - [ git rebase vs merge ](https://www.atlassian.com/git/tutorials/merging-vs-rebasing#the-golden-rule-of-rebasing) and [Another link](https://stackoverflow.com/a/9147389/12210002)
  - [reset vs revert vs checkout -- 2](https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting)
  - [Git Merge Strategies](https://www.atlassian.com/git/tutorials/using-branches/merge-strategy)
  - [REFLOG vs LOG](https://stackoverflow.com/a/17860179/12210002)
  - [Undoing a GIT Rebase](https://stackoverflow.com/a/135614/12210002)
  - [Undoing a commit](https://stackoverflow.com/a/4114122/12210002)
  - [Recover a lost commit](https://stackoverflow.com/a/10099285/12210002)
  - [.git folder](https://stackoverflow.com/a/56026788/12210002)
  - [Git Internal Architecture](https://indepth.dev/posts/1168/becoming-a-git-pro-part-1-internal-git-architecture)
  - [Git Snapshot](https://stackoverflow.com/a/4964137/12210002) and [how .git stores](https://stackoverflow.com/a/8198276/12210002)
  - [Fetch and merge](https://stackoverflow.com/a/20103414/12210002) and `git fetch origin source-branch:destiniation-branch` [link](https://stackoverflow.com/a/16095458/12210002)
  - [Pushing from one branch to another remote branch](https://stackoverflow.com/a/13897728/12210002)
  - [Rebase basics](https://stackoverflow.com/a/11566503/12210002) and [rebasing remote branch](https://stackoverflow.com/a/7929499/12210002)
  - [When u will use rebase vs merge](https://stackoverflow.com/a/9147389/12210002)







## Custom Git Alias

  - Instead of typing complete commands, we can create alias through __command line__ or in __gitConfig file under alias__.
  - [Link](https://stackoverflow.com/a/2553799/12210002)
  - From command line
    ```
      > git config --global alias.ci "commit -m"
      > git ci "committing the message"

    ```
  - [With Shell Scripts](https://stackoverflow.com/a/7534289/12210002)
  - [Github Alias list 1](https://gist.github.com/mwhite/6887990) and [Github Alias list 2](https://github.com/GitAlias/gitalias)

## REFLOGS (Getting the Lost Work...)



## Tagging
- git tag  (Viewing Tags)
- git tag -l "*beta*" (Filtering Tags)
- git diff v17.0.0 v12.0.0 (Diffing the tags)
- LightWeight Tags
  - just name/label to a commit (Only Commit Info + diff )
  - `git tag tagName commit-id`

- Annonated Tags
  - Stored the meta data (Author, date, msg etc) + Commit Info
  - `git tag -a -m message tagName commit-id`
  - You can use __-m__ to pass the comment inline
  - Seeing the metaData >> git show tagName

- Tagging Previous Commit >> `git tag tagName Commit_Hash`
- Replacing the tags with Force (Updating the tag to another commit) - git tag -f tagName Commit
- Deleting tags - git tag -d TagName
- Pushing Tags >> `git push --tags` (All Tags) Or `git push Origin v1.5` (a Particular Tag)

## cloning
- `git clone url folder-name`
- creates a copy of remote repo to a local repo..
- pushing to remote : `git push -u repo branch`
- deleting remote branch labels : `git push -d remote branch` [link](https://stackoverflow.com/a/10999165/12210002)

## Extra notes
- continous improvement means of releasing small batch sizes where workflow model depicts to release a batch of features at a time
- A commit is a snapshot of the project in time, and the collection of commits contains the project's history
- A branch can be created to work on a version of the project that other branches do not know about >> _independent development_
- A pull request is a request for others to review and approve the changes made to the project on a branch.
-  The working tree, .git directory, staging area and local repository are in the project directory where remote repo stays in remote providers (Github etc)
- Git uses `DAG (Directed Acyclic Graph)` to represent commit history where each commit points to its parent commit and so on..
- `git hash-object file-name` creates a SHA-1 commit id 
- `git show commit-id` to get the details of that commit
- Branch label is a reference that points to the latest commit and HEAD points to current active branch.The tags place labels on specific commit.
- `HEAD~1` refers to the parent commit of HEAD where `HEAD^1 and HEAD^2` canbe used to refer the first and second parent in a merge commit.
-  Git ids are the SHA-1 hashes that used to name the objects (commit obj, tags etc..)
- _Tracking Branches_ : Local branches that represent remote branches e.g `origin/master`
-     
