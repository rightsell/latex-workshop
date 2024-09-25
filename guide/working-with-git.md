# Git basics

## Setup



## User interfaces

For Windows and Mac there's [GitHub Desktop](https://desktop.github.com/download/). 

For Windows, Mac, and Linux, there's [LazyGit](https://github.com/jesseduffield/lazygit), which is a very fast and easy to use terminal frontend for Git. 
Usage is much simpler than the Git terminal commands. 

## Use

When you start working, do a `git pull` to fetch the current state of the repository. 
If there's a conflict with any local changes you've made, git will warn you to merge the changes first. 

After you've made some changes you want to sync to the repository, save your files and run `git commit -a` to commit all changed files, instead of adding them one-by-one.
This will prompt you for a commit message. The subject should be a short description of what you changed. Optionally you can type a more detailed message in the body of the commit, or you can leave it blank. 

To send your changes, simply run `git push`.

### Merging conflicts


