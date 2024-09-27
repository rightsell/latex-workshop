# Git basics

## Setup

See the [installation page](https://git-scm.com/downloads) for the Windows installer or options for MacOS installation. For MacOS, homebrew is probably the easiest method.

For linux, the easiest method is to install the git package using your distribution's package manager as usual.

## User interfaces

For Windows and Mac there's [GitHub Desktop](https://desktop.github.com/download/).

There are also a variety of [graphical user interfaces](https://git-scm.com/downloads/guis) available.

For Windows, Mac, and Linux, there's [LazyGit](https://github.com/jesseduffield/lazygit), which is a very fast and easy to use terminal frontend for Git.
Usage is much simpler than the Git terminal commands.

## Authenticating

To push to your repository from the command-line client, you'll need to either setup a [personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) or use [ssh keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).
With ssh keys you can use ssh-agent or the keychain in MacOS to store your credentials so that you only need to enter your password once after logging in to your computer.
If using access tokens, you can use the [git credential storage](https://git-scm.com/docs/git-credential-store) feature to simplify things.

## Use

When you start working, do a `git pull` to fetch the current state of the repository. 
If there's a conflict with any local changes you've made, git will warn you to merge the changes first.

After you've made some changes you want to sync to the repository, save your files and run `git commit -a` to commit all changed files, instead of adding them one-by-one.
This will prompt you for a commit message. The subject should be a short description of what you changed. Optionally you can type a more detailed message in the body of the commit, or you can leave it blank.

To send your changes, simply run `git push`.

### How to use pull requests to collaborate

Assume the first author has ownership of the repository and wants to review and control which changes are merged. Rather than have each co-author push directly to the main branch, each co-author should instead pull the latest version of the repository, and create a new branch. Once changes are made, a pull request is then submitted to the main branch. The repository owner (first author) will get a notification, and can then review the changes and differences, and determine which to merge.

Each co-author can keep working on their own branch, and when they want to update their branch with the latest changes from the main branch, they simply need to make sure they have their branch checked out, and then do a `git rebase main`.
If there are any conflicts with changes made on the co-author branch, they can be merged by the co-author into their own branch at this time.
Once the co-author has made more changes and wants to submit them to the main branch, they submit a pull request which can then be approved, rejected, or merged in case of conflicts.

### Merging conflicts

When a pull results in some conflicts to your local version that must be merged manually (i.e. the same line has been changed locally and remotely with different content), you will be warned by git that the remote has conflicts with your local copy.
In this case you can do a `git merge --no-ff`, which will pull the remote changes while preserving your local changes, placing indicators in the file so that you can manually fix the conflicts.

You will see something that looks like this after doing a `git merge --no-ff` which has conflicts that need to be merged:
```
<<<<<<< HEAD
This is the line that is going to have conflicts. This the change made locally.
=======
This is the line that is going to have conflicts. This is change made remotely.
>>>>>>> refs/remotes/origin/main
```

Everything at the top between the `<<<<<<<` and `=======` is the 'head' version which is your current branch with your locally made changes.
Underneath that, between the `=======` and `>>>>>>>` are the changes that were made in the repository (remote) that conflicted with your changes.
To resolve this, all you need to do is delete one or the other, or manually edit the line if you want to incorporate part of the remote change with some of your local change.

Note that after doing this there will be a conflict should you try to push to the main repository, so you should submit it as a pull request from your personal branch to the main branch. When the pull request is received, someone with control of the main branch of the repository (such as the first author) will then be shown the differences and just as you merged conflicts in your branch, they will have the same options for resolving any conflicts in your pull request.
