---
layout: post
title: "An Introduction to Git"
categories: version control, git
---
A three part article series on version control using Git and GitHub. This is the first article in the series in which I will give a very brief introduction to Git. This will allow most readers to understand enough to utilize it for version control during development. 

Git is a popular version control system that allows developers to manage and track changes to their code over time. It's an essential tool for software development teams, as it helps to ensure that changes to code are properly tracked and documented, and makes it easier for developers to collaborate and work together. Here's an overview of what Git is and how it works.

What is Git?
Git is a distributed version control system, meaning that every developer working on a project has their own copy of the code repository on their local machine. This allows developers to work on their own changes and then merge them back into the main repository when they are ready. Git is also designed to be very fast and efficient, making it ideal for managing large codebases and complex projects.

How does Git work?
Git works by tracking changes to files and directories in a code repository. When a developer makes changes to the code, they create a new "commit" that documents the changes they made. Git stores these commits in a tree-like structure, with each commit representing a snapshot of the code at a particular point in time. This allows developers to easily view the history of changes to the code over time, and to revert to previous versions if necessary.

Git also allows developers to create branches, which are essentially separate versions of the code repository that can be worked on independently. Branches are useful for trying out new features or making experimental changes without affecting the main codebase. Once changes have been tested and reviewed, they can be merged back into the main branch.

Using Git for version control
To use Git for version control, developers typically create a new repository on a Git hosting service such as GitHub, GitLab, or Bitbucket. They then clone the repository onto their local machine and begin making changes to the code. To commit changes, developers use Git commands such as "git add" to add changed files to the commit, and "git commit" to create a new commit with a commit message that describes the changes.

To collaborate with other developers, developers can push their changes to the remote repository and create "pull requests" that allow other developers to review the changes and provide feedback. Once changes have been reviewed and approved, they can be merged back into the main branch.

#### Before we learn about Git, lets quickly look at a few basic terminal commands, as we will be using Git on terminal. 
- Terminal (for Unix or Mac) or Command Prompt for Windows allows us to type Git commands and manage project repositories. In this section we will be focusing on terminal commands.  
- By default we are in the /home/vivek directory. home and mnt folders are in the same directory (usually they are in the highest level directory signified by just a /)
- pwd shows the current directory
- clear is used to clear the command line
- cd + tab key is used to cycle between sub directories in a directory
- cd .. is used to move up a directory
- cd mnt/ is used to enter the mnt directory. In this directory we can find the windows c drive (basically it is a directory named c)
- ~ signifies that you are in your home directory 
- \.\. is used to move up one directory
- / signifies the highest level directory, you cant go back from there
- mkdir is used to create a new directory
- Directory names are case sensitive
- Right click is used to paste an absolute path name in the terminal
- ls is used to list all directories and files in a directory
- rm -rf is used to remove folders. rf tells that we are using the command to remove a directory, as by default rm is used to remove a file
- git \-\-version is used to see the version of git
- touch file_name.txt is used to create a file

#### Now, lets take a look at some basics Git commands.
- Git Repository is used to save project files and the information about the changes in the project. Repository can be created locally, or it can be a clone Git repository which is a copy of a remote Git repo.
- git init is used to initialize the directory as a git repository. This will create a .git folder in the directory and we can start using git features 
- git status shows staging area. You will see some files under "Untracked files:" header
- git add file-name is used to add a file to staging area. After this you will see the file under the "Changes to be committed:" header
- git add . is used to add all files in directory to staging area (. signifies all)
- git rm \-\-cached file.txt is used to unstage a file
- git rm -f file.txt is used to force remove a file from staging area and also deletes the file from directory (-f signifies force)
- git config \-\-global user.email "abc.xyz@email.com"
- git config \-\-global user.name "abc.xyz"
- git commit \-\-help  
- git commit -a -m "Initial commit" (-m to include a message; -a to automatically stage files that have been modified and deleted, but new files you have not told Git about are not affected)
- git log (if you want to see a shorter version then use git log \-\-oneline)
- Head is usually on master (most recent commit). Head is what the project directory looks like. 
- git checkout \<commit-id\> is used to see the contents of the folder as they looked during that particular commit
- git checkout master is used to restore the head to the most recent commit, hence the contents of the project directory are also restored to what they were at the time of the most recent commit 
- git revert \<commit-id\> is used to revert the contents of the project directory to what they were before that particular commit. This will still appear in the log and we can go back to that commit by using git revert again
- git reset - three kinds - soft (only goes back in time in the commit tree, so just moves the head back; this is similar to checkout), mixed (moving back in time in the project directory but still can come back, doesn’t remove files) and hard (moving back in time in the project directory and staying there, removes files)
- touch .gitignore, now open the .gitignore file with notepad and add the names of the files you don’t want to track in that. # can be used to comment in this file. Usually you create .gitignore during initializing the project. If you have committed files already before adding them into the .gitignore file, then you need to remove them from cache by using the following series of commands
	- git rm -r \-\-cached .
	- git add .
	- git commit -m "message"
- If there is a directory in your project folder and you want to ignore all files in the directory from future commits, you can add "directory-name/\*" in the .gitignore file

#### What are Git Branches and how to use them for fixing errors
- Lets say there is an error in one of the files in the project folder
- We can create a branch to fix the error while the master repository stays intact
- git checkout -b err01 (creates a new branch called err01)
- \<fix the error in one of the files in the project folder\>
- git add . (add all changes made to the err01 to the staging area, so they can be committed)
- git commit -m 'fixed error' (commit all changes made to err01 branch)
- git checkout master (switch back to master branch)
- git merge err01 (merge changes made in err01 to master branch; merging will only take last commit of err01 and weave it into the master branch commit timeline)
- git push (this will push master branch of project folder to remote repository)
- git push origin err01 (this will push err01 branch of project folder to remote repository)
- git push origin \-\-delete err01 (we delete the err01 branch as we don’t need it anymore)
	- git branch -d bugs (local branches can be deleted using -d)
- git branch -a (list all branches)

#### Finally, how can we collaborate effectively  using Remote Repositories
- First step is to create a new repository on GitHub (don’t add a read-me, gitignore or license). Copy the url of the repository
- Create a project folder in your local machine and browse into that folder using bash
- git init (you will see that the repository has not been initialized yet; git init is used to create a new repository)
- git remote add origin \<paste url here\>
- git remote -v (you will see that the repository has been initialized)
- In GitHub website
	- "Create new file" \> README.md
	- "Create new file" \> LICENSE
	- "Create new file" \> .gitignore \> in content of that file type /AutoGen to exclude all files that we keep in that folder
- pull - go back to bash
	- git pull origin master (we don’t need to specify origin master is we set master as the tracked branch)
		- git branch \-\-set-upstream-to=origin/\<branch\> master
	- Sometimes you might be prompted for a login at this stage
- \<make changes to the local repository\>
- git push -u origin master (push updates to remote repository on GitHub; will ask for username and password)
- You can add other developers as collaborators to this repository.

In summary, Git is a powerful tool for version control that allows developers to manage and track changes to code over time. With its distributed architecture, fast performance, and support for branching and merging, Git is an essential tool for software development teams of all sizes.

Comments welcome!

{% include disqus_comments.html %}
