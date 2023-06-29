# Git and Github

Git is an important tool that allows developers to track and store versions of content and enables you to collaborate and share code with others.

## Git Intro Table of Contents

| Command                       |                        Description                         |   Cool |
| ----------------------------- | :--------------------------------------------------------: | -----: |
| [`git version`](#Git-Version) |                     Check Git Version                      | Basics |
| [`git status`](#Git-Status)   |      Gives information on the current status of repo       | Basics |
| [`git init`](#Git-Init)       | Lets us to turn any existing project into a Git repository | Basics |
| [`git commit`](#Git-Commit)   |            Commit changes from the staging area            | Basics |
| [`git add`](#Git-Add)         |           Add specific files to the staging area           | Basics |

### Git Version

`git --version` - To check version of git currently installed
`git config --global init.defaultBranch main` - To change default branch of git to main from master

### Git Status command

`git status` - git status gives information on the current status of a git repository and it's contents. It is a harmless command

Possible Error messages you may encounter

- fatal: not a git repository (or any of the parent directories): .git
  - This just means that your don't have git setup on the project
    - You will have to initialize a git repository with [`git init`](#Git-Init)

![Git Status](Images/Git/gitStatus.png)

### Git Init

`git init` - Lets us to turn any existing project into a Git repository. Before we can do anything git-related, we must initialize a git repo first! Done once per poject.

- Notice how now we see `git:(main)`? This shows that the folder is now a git repo.

![Git Init](Images/Git/gitinit.png)

Also note that git files are hidden
![Git Hidden Files](Images/Git/gitHiddenFiles.png)

Warning!
Running `rm -rf .git` in your project folder will removes all the git stuff form the folder
Also don't run `git init` inside a folder that already has git. Always make sure you are not in a git repo already.

- Run `rm -rf .git` if you initialize a git repo side a folder that already has git setup

## Git Commit

`git commit` - are "checkpoints" - command to actually commit changes from the staging area.

`git commit -m "insert message here" - The -m flag allows us to pass in an inline commit message, rather than launching a text editor

- When making a commit, you need to provide a commit message that summarizes the changes and work snapshotted in the commit
- If you get stuck in VIM editor because you typed in "git commit" then `:q` to exit

Note that `git status` will let you know of untracked changes when you are working on a file and will know of new files.
![Git Status](Images/Git/gitStatusNewFiles.png)

Here we see git committed and a clean working tree
![Git Commit](Images/Git/gitCommitMessage.png)

## Git Add

`git add` - Add specific files to the staging area. Separate files with spaces to add multiple at once
`git add .` - will stage all changes at once. We use this less because we want to be more precise on what we are adding.

- Notice how files went from red to green? The files are now added to staging area
  ![Git Add](Images/Git/gitAdd.pngs)

## Git Log

`git log` - Provides us a log of all our commits and messages
![git log](Images/Git/gitLog.png)
