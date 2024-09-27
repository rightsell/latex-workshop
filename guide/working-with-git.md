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


