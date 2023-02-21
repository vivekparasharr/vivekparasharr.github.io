---
layout: post
title: "An Introduction to GitHub"
categories: programming, version control, github
permalink: /programming/github
---
A three part article series on version control using Git and GitHub. This is the third article in the series in which I will give a very brief introduction to GitHub. This will allow most readers to understand enough to utilize it for version control during development. 

GitHub is a popular platform for hosting and sharing code repositories, and is widely used for version control and collaborative coding projects. If you're new to using GitHub for version control, here are some key things to keep in mind:

- Create a GitHub account: The first step in using GitHub is to create an account. You can sign up for a free account, which gives you access to public repositories, or a paid account, which gives you access to private repositories and additional features.
- Create a new repository: Once you have an account, you can create a new repository by clicking the "New repository" button on your GitHub dashboard. You can choose to make the repository public or private, and can add a README file and other files as needed.
- Clone the repository to your local machine: Once you have created a repository on GitHub, you can clone it to your local machine using Git. This allows you to make changes to the code locally, and push those changes back to the remote repository on GitHub.
- Make changes and commit them: Once you have cloned the repository to your local machine, you can make changes to the code and commit those changes to Git. Be sure to write clear and descriptive commit messages that explain the changes made.
- Push changes to the remote repository: After committing changes to Git, you can push those changes back to the remote repository on GitHub. This allows other team members to see the changes and collaborate on the code.
- Use pull requests for code reviews: When working on a team, it's a good practice to use pull requests to review code changes before merging them into the main branch. This allows other team members to review the code and provide feedback before changes are merged.
- Use branches for new features or bug fixes: When working on a new feature or bug fix, it's important to create a new branch in Git rather than making changes directly to the main branch. This keeps the main branch stable and allows for easier collaboration with other team members.

By keeping these key things in mind when using GitHub for version control, you can help ensure that your codebase is well-organized, well-documented, and easy to collaborate on with other team members.

Now, let us explore some of the key components of GitHub. 

#### Repository, branch
- Repository is a project's folder and contains all of the project files (including documentation), and stores each file's revision history.
- Branch is a parallel version of a repository. It is contained within the repository, but does not affect the primary or master branch allowing you to work freely without disrupting the "live" version. When you've made the changes you want to make, you can merge your branch back into the master branch to publish your changes.

#### Commit, revert
- Commit, or "revision", is an individual change to a file (or set of files). When you make a commit to save your work, Git creates a unique ID (a.k.a. the "SHA" or "hash") that allows you to keep record of the specific changes committed along with who made them and when. Commits usually contain a commit message which is a brief description of what changes were made.
- Revert - when you revert a pull request on GitHub, a new pull request is automatically opened, which has one commit that reverts the merge commit from the original merged pull request. In Git, you can revert commits with git revert.

#### Push, pull, fetch, merge
- Push means to send your committed changes to a remote repository on GitHub.com. For instance, if you change something locally, you can push those changes so that others may access them.
- Pull refers to when you are fetching in changes and merging them. For instance, if someone has edited the remote file you're both working on, you'll want to pull in those changes to your local copy so that it's up to date. See also fetch.
	- Pull requests are proposed changes to a repository submitted by a user and accepted or rejected by a repository's collaborators. Like issues, pull requests each have their own discussion forum.
- Fetch - when you use git fetch, you're adding changes from the remote repository to your local working branch without committing them. Unlike git pull, fetching allows you to review changes before committing them to your local branch.
- Merge takes the changes from one branch (in the same repository or from a fork), and applies them into another. This often happens as a "pull request" (which can be thought of as a request to merge), or via the command line. A merge can be done through a pull request via the GitHub.com web interface if there are no conflicting changes, or can always be done via the command line.

#### Fork, clone, download
- Fork is a personal copy of another user's repository that lives on your account. Forks allow you to freely make changes to a project without affecting the original upstream repository. You can also open a pull request in the upstream repository and keep your fork synced with the latest changes since both repositories are still connected
- Clone is a copy of a repository that lives on your computer instead of on a website's server somewhere, or the act of making that copy. When you make a clone, you can edit the files in your preferred editor and use Git to keep track of your changes without having to be online. The repository you cloned is still connected to the remote version so that you can push your local changes to the remote to keep them synced when you're online.
- Download option allows to download project folder as a zip file from GitHub to your local machine. This does not bring the .git folder, so using the http link to download is a better option

Comments welcome!

{% include disqus_comments.html %}
