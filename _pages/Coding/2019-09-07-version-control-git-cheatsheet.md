---
title: "Git Cheatsheet"
date: "2019-09-07"
tags:
    - programming
    - coding
    - version-control
    - git
    - cheatsheet
thumbnail: "/assets/img/placeholder.jpg"
---
A three part article series on version control using Git and GitHub. This is the second article in the series in which I will share my Git cheatsheet. This will enable the reader to quickly recall important commands to aid development. 

---

# Key things to remember when using Git
- Always create a new branch for new features or bug fixes: When working on a new feature or bug fix, it's important to create a new branch in Git rather than making changes directly to the main branch. This keeps the main branch stable and allows for easier collaboration with other team members.
- Commit early and often: It's a good practice to commit changes to Git as often as possible, rather than waiting until the end of the day or the end of a coding session. This makes it easier to track changes and roll back to previous versions if needed.
- Write clear commit messages: When committing changes to Git, be sure to write clear and descriptive commit messages that explain the changes made. This makes it easier for other team members to understand the changes and can save time during code reviews.
- Use Git pull requests for code reviews: When working on a team, it's a good practice to use Git pull requests to review code changes. This allows other team members to review the code and provide feedback before changes are merged into the main branch.
- Keep your Git repository organized: Make sure that your Git repository is organized and easy to navigate, with clear file and folder structures. This makes it easier to find specific files and makes the code repository more manageable over time.

By keeping these five key things in mind when using Git for version control, you can help ensure that your codebase is well-organized, well-documented, and easy to collaborate on with other team members.

---

# Basic commands

## Getting & Creating Projects

| Command | Description |
| - | - |
| git init | Initialize a local Git repository |
| git clone ssh://git@github.com/[username]/[repository-name].git | Create a local copy of a remote repository |

## Basic Snapshotting

| Command | Description |
| - | - |
| git status | Check status |
| git add [file-name.txt] | Add a file to the staging area |
| git add -A | Add all new and changed files to the staging area |
| git commit -m "[commit message]" | Commit changes |
| git rm -r [file-name.txt] | Remove a file (or folder) |

## Branching & Merging

| Command | Description |
| - | - |
| git branch | List branches (the asterisk denotes the current branch) |
| git branch -a | List all branches (local and remote) |
| git branch [branch name] | Create a new branch |
| git branch -d [branch name] | Delete a branch |
| git push origin \-\-delete [branch name] | Delete a remote branch |
| git checkout -b [branch name] | Create a new branch and switch to it |
| git checkout -b [branch name] origin/[branch name] | Clone a remote branch and switch to it |
| git branch -m [old branch name] [new branch name] | Rename a local branch |
| git checkout [branch name] | Switch to a branch |
| git checkout - | Switch to the branch last checked out |
| git checkout \-\- [file-name.txt] | Discard changes to a file |
| git merge [branch name] | Merge a branch into the active branch |
| git merge [source branch] [target branch] | Merge a branch into a target branch |
| git stash | Stash changes in a dirty working directory |
| git stash clear | Remove all stashed entries |

## Sharing & Updating Projects

| Command | Description |
| - | - |
| git push origin [branch name] | Push a branch to your remote repository |
| git push -u origin [branch name] | Push changes to remote repository (and remember the branch) |
| git push | Push changes to remote repository (remembered branch) |
| git push origin --delete [branch name] | Delete a remote branch |
| git pull | Update local repository to the newest commit |
| git pull origin [branch name] | Pull changes from remote repository |
| git remote add origin ssh://git@github.com/[username]/[repository-name].git | Add a remote repository |
| git remote set-url origin ssh://git@github.com/[username]/[repository-name].git | Set a repository's origin branch to SSH |

## Inspection & Comparison

| Command | Description |
| - | - |
| git log | View changes |
| git log \-\-summary | View changes (detailed) |
| git log \-\-oneline | View changes (briefly) |
| git diff [source branch] [target branch] | Preview changes before merging |

Comments welcome!