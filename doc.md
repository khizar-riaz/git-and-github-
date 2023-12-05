# Git and Github documentation 

- Welcome to the foundational guide on Git and GitHub, your essential tools for version control and collaborative development. This documentation aims to provide you with a basic understanding of Git and GitHub concepts, accompanied by practical examples and exercises.

- In this comprehensive markdown file (doc.md), you'll find detailed explanations and examples covering the git commands alongside with github.

- This plain text file is the practical playground to implement the commands discussed in doc.md. 

*** 

## Introduction

- Git is a distributed version control system that allows you to track changes in your codebase over time.  It was created by Linus Torvalds in 2005.

- GitHub is a web-based platform that provides hosting for Git repositories. It was founded in 2008 and is now owned by Microsoft.


## Getting Started with Git

- Git is a version control system.

- Git helps you keep track of code changes.

- Git is used to collaborate on code.

## Git Installation

- To install Git on your computer, follow these steps based on your operating system.

#### Windows:

- Git for Windows:
- Download the installer from the official Git website: Git for Windows.
- Run the downloaded installer.
- Follow the installation steps, accepting the default options.
- Verify Installation:
- Open a Command Prompt or Git Bash.
- Type the following command and press Enter:

``` 

git --version

```

#### macOS:

- Open Terminal.
- Install Homebrew by running the following command:

``` 

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

```

- After installing Homebrew, run the following command to install Git:

``` 

brew install git

```

- Type the following command in Terminal:

``` 

git --version

```

## Configure Git

- Now let Git know who you are. This is important for version control systems, as each Git commit uses this information:

``` 

git config --global user.name "khizar-riaz"

git config --global user.email "khizarriaz012@gmail.com"

```
- Change the user name and e-mail address to your own.
- Use global to set the username and e-mail for every repository on your computer. If you want to set the username/e-mail for just the current repo, you can remove global

## Creating Git Folder

- let's create a new folder for our project:

```

mkdir myproject

cd myproject

```

- mkdir makes a new directory.
- cd changes the current working directory.

## Initialize Git

- After  navigation to the correct folder, you can initialize Git on that folder:

```

git init 

```
- It will Initialized empty Git repository in the particular folder and response is like (Initialized empty Git repository in /Users/user/myproject/.git/).
- Git now knows that it should watch the folder you initiated it on. Git creates a hidden folder to keep track of changes.

## Git Adding New Files

- In above section `Initialize Git` We just created in your out local Git repo. But it is empty.
- let's add some files, or create a new file.
- Here we have created test.txt file.
- Now Check the file in the current directory by using ls command:

```

ls

```

- ls will list the files in the directory. We can see that test.txt is there.
- Then we check the Git status and see if it is a part of our repo:

```

git status

```

- Now Git is aware of the file, but has not added it to our repository!
- Files in your Git repository folder can be in one of 2 states:
  1. Tracked - files that Git knows about and are added to the repository.
  2. Untracked - files that are in your working directory, but not added to the repository.
- When you first add files to an empty repository, they are all untracked. To get Git to track them, you need to stage them, or add them to the staging environment.

## Git Staging Environment

- concepts of `Staging Environment` and the `Commit` are One of the core functions of Git.
- Staged files are files that are ready to be committed to the repository you are working on.
- For now, we are done working with test.txt. So we can add it to the Staging Environment:

```

git add test.txt

```

- The file should be Staged. Let's check the status:

```

git status

```

- Now our test.txt file has added to Staging Environment.
- We can also stage more than one file at a time. Following is the command:

```

git add --all

```

- Now all files are added to the Staging Environment, and we are ready to do our first commit.

## Git Commit

- Adding commits keep track of our progress and changes as we work. 
- Git considers each commit change point or "save point".
- It is a point in the project you can go back to if you find a bug, or want to make a change.
- When we commit, we should always include a message.
- By adding clear messages to each commit, it is easy for yourself (and others) to see what has changed and when.

```

git commit -m "First release of text file"

```

- The commit command performs a commit, and the -m "message" adds a message.
- The Staging Environment has been committed to our repo, with the message:"First release of text file"

#### Git Commit without Stage

- Sometimes, when you make small changes, using the staging environment seems like a waste of time. It is possible to commit changes directly, skipping the staging environment. The `-a` option will automatically stage every changed, already tracked file.
- Let's add a small update to text.txt: add new line

```

git status --short

git commit -a -m "Updated text.txt with a new line"

```

- Skipping the Staging Environment is not generally recommended.
- Skipping the stage step can sometimes make you include unwanted changes.

#### Git log

- To view the history of commits for a repository, you can use the log command:

```

git log

```

- Note: Short status flags are:

| File Status           | File Sign |
| --------------------- | ----------|
| Untracked files       | ??        |
| Files added to stage  | A         |
| Modified files        | M         |
| Deleted files         | D         |

## Git Help

- Git help can be use to remember commands or options for commands.
- There are a couple of different ways you can use the help command in command line.
- `git command -help` is use to see all the available options for the specific command.
- For example if we need help regarding `git commit` command:

```

git commit -help

```

- `git help --all` is use to see all possible commands

```

git help --all

```

## Git Branch

- In Git, a branch is a new/separate version of the main repository.
- Branches allow you to work on different parts of a project without impacting the main branch.
- When the work is complete, a branch can be merged with the main project.
- You can even switch between branches and work on different projects without them interfering with each other.
- Branching in Git is very lightweight and fas.

#### New Git Branch

- Let add some new lines to our test.txt file.
- We are working in our local repository, and we do not want to disturb or possibly wreck the main project.
- So we create a new branch:

```

git branch development

```

- Now we created a new branch called `development`.
- To confirm that we have created a new branch:

```

git branch

```

- We can see the new branch with the name `development`, but the * beside master specifies that we are currently on that branch.
- checkout is the command used to check out a branch. Moving us from the current branch, to the one specified at the end of the command:

```

git checkout development

```

- Now we have moved our current workspace from the master branch, to the new branch
- now we are adding a new line `2. new line for making a new branch` in text.txt file.
- Now check the status of the current branch:

```

git status

```

- So let's go through what happens here:
- There are changes to our `test.txt`, but the changings in file is not staged for commit 
- So we need to add both files to the Staging Environment for this branch:

```

git add --al

```

- Using `--all` instead of individual filenames will Stage all changed (new, modified, and deleted) files.
- We are happy with our changes. So we will commit them to the branch:

```

git commit -m "Added new line in test.txt file"

```
- Now we have a new branch development that is different from the master branch.

#### Switching Between Branches

- Now let's see just how quick and easy it is to work with different branches, and how well it works.
- We are currently on the branch `development`. We added a line to this branch, so let's list the files in the current directory:

```

ls

```

- We can see the new line in the file `test.txt` as `2. new line for making a new branch`.
- Now, let's see what happens when we change branch to master by using below command.

```

git checkout master

```

- The new line is not a part of this branch.
- we can see the code reverted to what it was before the alteration.

#### Emergency Branch

- Now imagine that we are not yet done with `development` branch, but we need to fix an error on master.
- we don't want to mess with `main` directly, and we do not want to mess with `development`, since it is not done yet.
- So we create a new branch to deal with the emergency:

```

git checkout -b emergency-fix

```

- Note: Using the -b option on checkout will create a new branch, and move to it, if it does not exist
- Now we have created a new branch from master, and changed to it. We can safely fix the error without disturbing the other branches.
- Let's fix our imaginary error:
- We have made changes in this file test.txt with a line `error solved`, and we need to get those changes to the master branch.



```

git status

```
- it shows that On branch `emergency-fix` Changes not staged for commit so stage the file and commit.

```

git add test.txt

git commit -m "updated test.txt with emergency fix"

```

- Now we have a fix ready for master, and we need to merge the two branches i.e  `main` and `emergency-fix`.

