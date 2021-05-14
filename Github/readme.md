# Github

## What is it
- Hosting platform for git repos
- useful collaboration and sharing i.e open source project


### Notes

- Cloning : `git clone github_repo_url`
- Adding SSH keys to Github
  - [link1](https://www.freecodecamp.org/news/git-ssh-how-to/)
  - [link2](https://devconnected.com/how-to-setup-ssh-keys-on-github/)
- setting up Remote : `git remote add name url` and listing all remotes : `git remote -v`
- renaming and reomoving the remote : `git remote rename old new` and `git remote remove name`
- Push : `git push remote branch` and `git push origin local-branch : remote-branch`
- `git push -u origin master ` sets the upstream of local master branch to track the remote master branch and it will enable `git push` to do the same thing as a short-cut
- Seeing the remote branched -- `git branch -r`

- Fetching the changes : `git fetch remote-name branch` >> updates the local git repo with the remote with all contents and remote branches(remote-name/branch-name)
- Pulling the chnages : `git pull = git fetch + git merge`. [Fetch vs Merge](https://stackoverflow.com/a/7104747/12210002)


### About Github
  - Github Pages
  - Github Gists - for Sharing codes
  - Collaboration >> open source projects
  - [Git Fork](https://stackoverflow.com/a/6286877/12210002)
  - [Github Flow Guide](https://guides.github.com/introduction/flow/) and [Guide 2](https://www.atlassian.com/git/tutorials/comparing-workflows) , [Guide 3 Forking](https://guides.github.com/activities/forking/)
  - [Markdown Notes](https://guides.github.com/features/masterinsg-markdown/)
  - [Forking and Branching](https://stackoverflow.com/a/3611349/12210002)
  - 
  