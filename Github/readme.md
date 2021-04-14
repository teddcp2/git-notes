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
  