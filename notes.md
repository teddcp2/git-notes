
### section 3 : working with Github repo, SSH Authentication

1. Setting up the ssh keys with github 
    * [link1](https://www.freecodecamp.org/news/git-ssh-how-to/)
    * [link2](https://gist.github.com/developius/c81f021eb5c5916013dc)

2. cloning from remote
    * git clone url folder_name  [Íf you dont specify folder name, git will create as per the remote]

3. Pushing to remote
    * git push -u origin master --tags  [-u is required only one time to set up a tracking type]'

```
Note

- when you hv set up a tracking type, and u try `git push` 

1. push is of 2 types : matching and simple. 
    * [link 1](https://stackoverflow.com/a/21865319/12210002)
    * [link 2](https://stackoverflow.com/a/13148313/12210002)

2.  Matching 
    * It is like git will by default send out all the changes to all the remote tracking    	 branches
    * It will push all the branches to the remote branch and would merge them. If you don’t want to  push all branches, you can push the current branch only.

    * git config --global push.default matching

3. simple will only push to the current tracking branch with the same branch name. so it must hv a remote tracking upstream, but current will work regardless of the tracking.
    * It will push branches one by one. It Mostly connected with current branch.
    
    * git config --global push.default simple

    * simple vs current - [link](https://stackoverflow.com/a/23918418/12210002)

- Upstream vs downstream
    * [link1](https://stackoverflow.com/a/2739476/12210002)

- Difference between upstream and origin when you clone
    * [link](https://stackoverflow.com/a/9257901/12210002)

- understanding `git push -u origin master`
    * [link](https://stackoverflow.com/a/17122300/12210002)
    * [link](https://stackoverflow.com/a/37770744/12210002)
    * [link](https://stackoverflow.com/a/18032014/12210002)
```

4. Fetch and pull

    * pull - Fetch and merge .. it can fail when there is a merge conflict. Destructive
    * fetch - non-destructive, then we have to merge
    * [link](https://stackoverflow.com/a/7104747/12210002)

5. working with remote
    * git remote add oring url
    * if you have updated the repo and it has different url, then 
        git remote set-url origin url
    * git remote -v (All the available remotes)
    * git remote show orign  (detailed description of a remote )

7. seeing a particular commit
    * git show id

