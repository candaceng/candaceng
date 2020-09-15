---
title: "The Basics of Git on the Command Line"
date: 2020-07-23
tags: [Git]
excerpt: "The fundamentals of using git on the command line"
---

Git is a *distributed version control system*, where every developer on a project has a cloned repository stored on their local machine. Unlike *central version control systems*, you do not need to be connected to the network to access the repository since every developer has a local copy of the entire project. 

### Getting Started
After [installing Git](https://git-scm.com/), the first step is to open up the command line and configure your settings so that Git can associate you with the changes you make when working on a project.  
```bash
git config --global user.name "<name>"
git config --global user.email "<email>"
```

### Tracking a local project
Let's start simple by initializing a repository from existing code. First we navigate to the desired directory and use the `git init` command.
```bash
cd <directory>
git init
```
A *.git* file will appear, which means that Git is tracking the files in that particular directory. If you want to stop tracking the files, you can simply remove the *.git* file. If you only want to track a subset files in a directory, you can add a *.gitignore* file that lists the files that you don't want Git to track. In a project we typically track code files so that we can push updated changes to a repository. To view the current status of our tracked files we can use the command:
```bash
git status
```
Any files that have changes that are untracked (and are not listed in the *.gitignore* file) will show up in red. For example, this article was created in a markdown file that currently has untracked changes, so it shows up in red when I run `git status`. 
<br><br><img class="align-center" src="/images/git/git-status.PNG" style="border-radius: 5px; width: 75%;"><br>
To make it green, we need to add the file to the *staging area* with the command `git add`. We can add individual files at a time, or add all untracked files with the following commands: 
```bash
git add _posts/2020-07-23-git-basics.md
git add -A 
```
Now if we run `git status` again, we see that our file is now in green. 
<br><br><img class="align-center" src="/images/git/git-status2.PNG" style="border-radius: 5px; width: 75%;"><br>
If you've added a file to the staging area by mistake, you can unstage it:
```bash
git reset _posts/2020-07-23-git-basics.md
```
The staging area acts as the middle man between your working directory and the remote repository. Once you've prepared all the changes you want to make in the staging area, you're ready to commit these changes. You must include a commit message to describe the changes you've made.
```bash
git commit -m "<your description>"
```
Once committed, you'll want to push these changes to the remote repository. If changes to any file in your directory has been changed externally, you'll have to pull these new updates before pushing your own.
```bash
git pull origin master
git push origin master
```
Here, *origin* is just the name of our remote repository and *master* is the name of the main branch. We'll cover branches in more detail in the next section.

### Working in a team
This is where Git really becomes powerful. When multiple developers are working on a project, it becomes way easier to keep code tracked and organized. Each commit you make should only tackle one specific part of the project, and your commit messages should be clear and concise. As mentioned earlier, all developers will have a full history of the project on their local machine after they've cloned the repository. We do this with the `git clone` command, and specify the url of the repository. 
```bash
git clone <url>
```
Let's say our project is to create a calculator and we want to implement the multiply function. Whenever making a change to our remote repository, we want to split off from the *master branch*. This way, we can test out our multiply function and make sure it works before merging back with the master branch. Thus if we run into bugs, we won't be breaking the main code and other developers can continue working off the latest working version. 
```bash
git branch <branchname>
git checkout <branchname>
```
Here we created a new branch and can start working on it with `git checkout`, which is analogous to changing directories with `cd`. Now we use the same `git add` and `git commit` commands before pushing our branch to the remote repository. 
```bash
git push -u origin <branchname>
```
The `-u` flag essentially tells Git to associate the current branch with the remote branch. After doing this once, you can simply use `git pull` and `git push` without using the `-u` flag. 

To merge our branch with master, we need to switch to the master branch and pull down any new changes. 
```bash
git checkout master
git pull origin master
```
Once we've finished with the branch, we can delete it. Since our branch was pushed to the remote repository, we're going to have to delete it both locally and remotely. 
```bash
git branch -d <branchname>
git push origin --delete <branchname>
```

### Summary 
Git is great for working on agile projects at scale. Every developer has a full history of commits and can easily track changes in source code or modify parts of it, all while maintaining reliability. Though there are a lot of commands to learn, it should be quite easy to pick up once you start working with a few remote repositories with Git on the command line. 
