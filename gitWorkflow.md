# GitWorkFlow


# Step1: Clone a repository from Github

When you create a repository on GitHub, it exists as a remote repository. You can clone your repository to create a local copy on your computer and sync between the two locations.

This procedure assumes you have already created a repository on GitHub, or have an existing repository owned by someone else you'd like to contribute to.

1. On GitHub, navigate to the main page of the repository.

2. Under the repository name, click Clone or download.

3.  In the Clone with HTTPs section, click  to copy the clone URL for the repository.

4. Change the current working directory to the location where you want the cloned directory to be made.

5. Type git clone, and then paste the URL you copied in Step 2.

```bash
$ git clone <URL>
```
6. Type git clone, and then paste the URL you copied in Step 2.

```bash
$ git clone URL
Cloning into `Spoon-Knife`...
remote: Counting objects: 10, done.
remote: Compressing objects: 100% (8/8), done.
remove: Total 10 (delta 1), reused 10 (delta 1)
Unpacking objects: 100% (10/10), done.
```

# Step2: Create a new branch

Change into the newly-created afraid-to-commit directory, where you’ll find all the source code of the Don’t be afraid to commit project.

Now you’re in the working directory, the set of files that you currently have in front of you, available to edit. We want to know its status:

```bash
$ git status
# On branch master
nothing to commit (working directory clean)
```

Just as you did on GitHub, once again you’re going to create a new branch, based on master, for new work to go into:

```bash
$ git checkout -b amend-my-name
Switched to a new branch 'amend-my-name'
```

# Step3: Edit the files

## Make some modifications
Edit the file.

```bash
$ git status
# On branch amend-my-name
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#   modified:   attendees_and_learners.rst
#
no changes added to commit (use "git add" and/or "git commit -a")
```
What this is telling us:
* we’re on the amend-my-name branch
* that we have one modified file
* that there’s nothing to commit

These changes will only be applied to this branch when they’re committed. You can git add changed files, but until you commit they won’t belong to any particular branch.

## Stage your changes

Git has a staging area, for files that you want to commit. On GitHub when you edit a file, you commit it as soon as you save it. On your machine, you can edit a number of files and commit them altogether.

Staging a file in Git’s terminology means adding it to the staging area, in preparation for a commit.

Add your amended file to the staging area:

```bash
git add attendees_and_learners.rst
```

# Step4: Commit the changes

When you’re happy with your files, and have added the changes you want to commit to the staging area:

```bash
git commit -m "added my github name"
```

he -m flag is for the message (“added my github name”) on the commit - every commit needs a commit message.

# Step 4: Push your changes to GitHub

If you were pushing changes from master locally to master on GitHub, you could just issue the command git push and let Git work out what needs to go where.

It’s always better to be explicit though. What’s more, you have multiple branches here, so you need to tell git where to push (i.e. back to the remote repository you cloned from, on GitHub) and what exactly to push (your new branch).

The repository you cloned from - yours - can be referred to as origin. The new branch is called amend-my-name. So:

```bash
$ git push origin amend-my-name
Counting objects: 34, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (21/21), done.
Writing objects: 100% (28/28), 6.87 KiB, done.
Total 28 (delta 13), reused 12 (delta 7)
To git@github.com:evildmp/afraid-to-commit.git
 * [new branch]      amend-my-name -> amend-my-name
 ```

 # Step5: Push into Github

 When you made a change on GitHub, it not only saved the change and committed the file at the same time, it also showed up right away in your GitHub repository. Here there is an extra step: we need to push the files to GitHub.

If you were pushing changes from master locally to master on GitHub, you could just issue the command git push and let Git work out what needs to go where.

It’s always better to be explicit though. What’s more, you have multiple branches here, so you need to tell git where to push (i.e. back to the remote repository you cloned from, on GitHub) and what exactly to push (your new branch).

The repository you cloned from - yours - can be referred to as origin. The new branch is called amend-my-name. So:

```bash
$ git push origin amend-my-name
Counting objects: 34, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (21/21), done.
Writing objects: 100% (28/28), 6.87 KiB, done.
Total 28 (delta 13), reused 12 (delta 7)
To git@github.com:evildmp/afraid-to-commit.git
 * [new branch]      amend-my-name -> amend-my-name
 ```






