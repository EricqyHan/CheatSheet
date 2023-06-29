# Git and Github

Git is an important tool that allows developers to track and store versions of content and enables you to collaborate and share code with others.

## Git Intro Table of Contents

| Command                       |                        Description                         |   Cool |
| ----------------------------- | :--------------------------------------------------------: | -----: |
| [`git version`](#Git-Version) |                     Check Git Version                      | Basics |
| [`git status`](#Git-Status)   |      Gives information on the current status of repo       | Basics |
| [`git init`](#Git-Init)       | Lets us to turn any existing project into a Git repository | Basics |

### Git Version

`git --version` - To check version of git currently installed
`git config --global init.defaultBranch main` - To change default branch of git to main from master

### Git Status command

`git status` - git status gives information on the current status of a git repository and it's contents. It is a harmless command

Possible Error messages you may encounter

- fatal: not a git repository (or any of the parent directories): .git
  - This just means that your don't have git setup on the project
    - You will have to initialize a git repository with [`git init`](#git-init)

![Git Status](Images/Git/gitStatus.png)

### Git Init
