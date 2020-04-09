# Git

## Definitions

- Git - a distributed version control system (VCS).

## Common commands

```bash
git init
git status
git add .
git commit -m "Some message"
git checkout -b <branch-name>
git merge <branch-name>
git branch -d <branch-name>
```

## 1. Checking the status

Command to check the status of our repository:

```bash
    git status
```

Indicates which files have been changed, which files are tracked, etc.

## 2. Staging files

Use the `git add` command to add files to the staging area, which allows them to be tracked.

Add specific files to the staging area:

```bash
  git add file.js
```

To add multiple files:

```bash
  git add file.js file2.js file3.js
```

Can also add all the files inside the project folder to the staging area:

```bash
  git add .
```

## 3. Making commits

A **commit** is a snapshot of our code at a particular time, which we are saving to the commit history of our repository.

The following command commits the files from the staging area:

```bash
    git commit -m "Commit message"
```

Inside the quotes, we should write a **commit message** which is used to identify it in the commit history.

I recommend checking out [semantic commits](SEMANTIC-COMMITS.md).

## 4. Commit history

To see all the commits that were made for our project:

```bash
    git log
```

To go back to a previous state of your project code that you committed, you can use the following command:

```bash
    git checkout <commit-hash>
```

Replace `<commit-hash>` with the actual hash for the specific commit that you want.

To go back to the latest commit (the newest version of our project code), you can type this command:

```bash
    git checkout master
```

## Ignoring files

Ignore files that you don't want to be tracked or added to the staging area by creating a file called `.gitignore` in your main project folder.

# Branches

A **branch** could be interpreted as an individual timeline of our project commits.

With Git, we can create many of these alternative environments (i.e. we can create different **branches**) so other versions of our project code can exist and be tracked in parallel.

That allows us to add new (experimental, unfinished, and potentially buggy) features in separate branches, without touching the '_official'_ stable version of our project code (which is usually kept on the **master** branch).

When we initialize a repository and start making commits, they are saved to the **master** branch by default.

## Creating a new branch

Create a new branch using the following:

```bash
    git branch <new-branch-name>
```

The new branch that gets created will be the reference to the current state of your repository.

It's a good idea to create a **development** branch where you can work on improving your code, and adding new experimental features.

## Changing branches

To switch to a different branch, you use the **git checkout** command:

```bash
    git checkout <branch-name>
```

With that, you switch to a different isolated timeline of your project by changing branches.

To create a new branch and change to it at the same time, you can use the **-b** flag:

```bash
    git checkout -b <new-branch-name>
```

List the branches for your project with: `git branch`

Get back to the master branch with:

```bash
    git checkout master
```

## Merging branches

To merge the changes from a different branch into your current branch, you can use this command:

```bash
    git merge <branch-name>
```

You would replace `<branch-name>` with the branch that you want to integrate into your current branch.

## Deleting a branch

To delete a branch, you can run the **git branch** command with the **-d** flag:

```bash
    git branch -d <branch-name>
```
