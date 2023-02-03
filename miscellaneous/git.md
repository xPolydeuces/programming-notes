# Git basics

Git is a distributed version control system for tracking changes in source code during software development.

## Setting up Git Configuration

Enter the following commands in the terminal to set up Git configuration:

```bash
$ git config --global user.name "User Name"
$ git config --global user.email "user.email@example.com"
```

## Initialize a Git Repository

Initialize a Git repository in an existing project directory by entering the following command:

```bash
$ git init
```

## Track Files in the Repository

Track files in the repository by adding them to the staging area using the following command: 

```bash
$ git add <file>
```
Or add all files in the directory using:
```bash
$ git add .
```

## Commit Changes to the Repository

Commit the changes to the reposity with a message describing the changes:

```bash
$ git commit -m "Commit message"
```

## Connect to a Remote Repository

Connect local repository to a remote repository on a hosting service such as GitHub, GitLab or Bitbucket using the following command:

```bash
$ git remote add origin <remote repository URL>
```

## Push Changes to the Remote Repository

Push changes to the remote repository using the following command:

```bash
$ git push -u origin master
```

## Update Local Repository

To update the local repository with the latest changes from the remote repository, use the following command:

```bash
$ git pull
```

