The Git protocol
================

# Overview

This document provides a quick tutorial to the Git protocol for those unfamiliar with it. Git is a decentralised version control system. It manages the different versions a document goes through during its lifetime (from creation to deletion and through the various updates applied to the document). To get a good grasp of Git, I encourage you to read the [Pro Git](https://git-scm.com/book/en/v2) book. It offers detailed information about Git from installation to complex workflows.

# Setup

Once you successfully install Git on your machine, you need to configure your user details for all future repositories. It is recommended to configure at least the user name and email address.

The command `git config --global user.name "MyFirstname MyLastName"` assigns a name for the current user. Every subsequent commit will attach that name and thus give credit to the author of the changes being committed. `git config --global --user.email "emailaddress"` will link the valid email address to the current user. For more configurations, please chack the documentation.

# Initialisation

You can initialise a Git repository in two possible ways. First, you can change directory to an existing folder that does not a Git repository yet. Type the command `git init` and a directory tree (and some additional information) will be created for you. The second way of initialising a repository is by cloning an existing repository as follows `git clone url [local-name]`. This command will copy a repository at location url and create a folder local-name if you provided that argument or use the same folder name as the original repository.

# General Usage

Your general usage of the Git protocol consists in adding a new file to working tree and committing changes. The command `git add file-name` will add file-name to the directory in the working tree. To commit recent changes, use the command `git commit -m "commit message"`. The best practices in how to draft a commit message abound on the Internet. Please look them up and adopt them. It proves very useful in the context of a collaboration to structure commit messages following an agreed upon format.

Other usual commands that you might need include `git diff` and `git status`.

# Branching

Branching can prove quite handy when using the Git protocol. It can help you explore different lines of thoughts without collapsing them. By default the master branch is created in the repository after initialisation. To list all local branches type the command `gir branch`. To include the remote branches, simply add the argument a `git branch -a`.

To create a new branch, use the command `git branch new-branch-name`. Please note that this command does not switch to the newly created branch. There are several variants of the command, please check the documentation for further exploration. Finally, to switch to another branch, use the command `git checkout branch-name`.

# Collaboration

A way to setup collaboration in Git is to create copy of the repository, which all collaborators can sync their versions with. Because Git is decentralised, collaborators might asymmetrical views in their local working directories.

To add a remote branch to your repository, use the command `git remote add branch-name bracnh-url`. You can now merge a remote branch wuth your current branch as follows `git merge remote-bracnh-name`. Commonly, you can pull from and push to a remote branch by using the `git pull` and `git push` commands. Caution! With these two commands you will have to specify the local and remote branches involved.
