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