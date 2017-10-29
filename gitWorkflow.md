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
 # More about GitWorkFlow

 ## Tagging

 Like most VCSs, Git has the ability to tag specific points in history as being important. Typically people use this functionality to mark release points (v1.0, and so on). In this section, you’ll learn how to list the available tags, how to create new tags, and what the different types of tags are.

### Listing Your Tags
Listing the available tags in Git is straightforward. Just type git tag
### Creating Tags
Git uses two main types of tags: lightweight and annotated.

#### A lightweight tag is very much like a branch that doesn’t change – it’s just a pointer to a specific commit.

Annotated tags, however, are stored as full objects in the Git database. They’re checksummed; contain the tagger name, email, and date; have a tagging message; and can be signed and verified with GNU Privacy Guard (GPG). It’s generally recommended that you create annotated tags so you can have all this information; but if you want a temporary tag or for some reason don’t want to keep the other information, lightweight tags are available too.

#### Annotated Tags
Creating an annotated tag in Git is simple. The easiest way is to specify -a .
#### Tagging Later
You can also tag commits after you’ve moved past them. 

#### Sharing Tags
By default, the git push command doesn’t transfer tags to remote servers. You will have to explicitly push tags to a shared server after you have created them. This process is just like sharing remote branches – you can run git push origin <tagname>.

#### Checking out Tags
If you want to view the versions of files a tag is pointing to, you can do a git checkout, though this puts your repository in “detached HEAD” state, which has some ill side effects.

### .gitignore
A gitignore file specifies intentionally untracked files that Git should ignore. Files already tracked by Git are not affected; see the NOTES below for details.

Each line in a gitignore file specifies a pattern. When deciding whether to ignore a path, Git normally checks gitignore patterns from multiple sources, with the following order of precedence, from highest to lowest (within one level of precedence, the last matching pattern decides the outcome):

Patterns read from the command line for those commands that support them.

Patterns read from a .gitignore file in the same directory as the path, or in any parent directory, with patterns in the higher level files (up to the toplevel of the work tree) being overridden by those in lower level files down to the directory containing the file. These patterns match relative to the location of the .gitignore file. A project normally includes such .gitignore files in its repository, containing patterns for files generated as part of the project build.

Patterns read from $GIT_DIR/info/exclude.

Patterns read from the file specified by the configuration variable core.excludesFile.

Which file to place a pattern in depends on how the pattern is meant to be used.

Patterns which should be version-controlled and distributed to other repositories via clone (i.e., files that all developers will want to ignore) should go into a .gitignore file.

Patterns which are specific to a particular repository but which do not need to be shared with other related repositories (e.g., auxiliary files that live inside the repository but are specific to one user’s workflow) should go into the $GIT_DIR/info/exclude file.

Patterns which a user wants Git to ignore in all situations (e.g., backup or temporary files generated by the user’s editor of choice) generally go into a file specified by core.excludesFile in the user’s ~/.gitconfig. Its default value is $XDG_CONFIG_HOME/git/ignore. If $XDG_CONFIG_HOME is either not set or empty, $HOME/.config/git/ignore is used instead.

The underlying Git plumbing tools, such as git ls-files and git read-tree, read gitignore patterns specified by command-line options, or from files specified by command-line options. Higher-level Git tools, such as git status and git add, use patterns from the sources specified above.

PATTERN FORMAT
A blank line matches no files, so it can serve as a separator for readability.

A line starting with # serves as a comment. Put a backslash ("\") in front of the first hash for patterns that begin with a hash.

Trailing spaces are ignored unless they are quoted with backslash ("\").

An optional prefix "!" which negates the pattern; any matching file excluded by a previous pattern will become included again. It is not possible to re-include a file if a parent directory of that file is excluded. Git doesn’t list excluded directories for performance reasons, so any patterns on contained files have no effect, no matter where they are defined. Put a backslash ("\") in front of the first "!" for patterns that begin with a literal "!", for example, "\!important!.txt".

If the pattern ends with a slash, it is removed for the purpose of the following description, but it would only find a match with a directory. In other words, foo/ will match a directory foo and paths underneath it, but will not match a regular file or a symbolic link foo (this is consistent with the way how pathspec works in general in Git).

If the pattern does not contain a slash /, Git treats it as a shell glob pattern and checks for a match against the pathname relative to the location of the .gitignore file (relative to the toplevel of the work tree if not from a .gitignore file).

Otherwise, Git treats the pattern as a shell glob suitable for consumption by fnmatch(3) with the FNM_PATHNAME flag: wildcards in the pattern will not match a / in the pathname. For example, "Documentation/*.html" matches "Documentation/git.html" but not "Documentation/ppc/ppc.html" or "tools/perf/Documentation/perf.html".

A leading slash matches the beginning of the pathname. For example, "/*.c" matches "cat-file.c" but not "mozilla-sha1/sha1.c".

Two consecutive asterisks ("**") in patterns matched against full pathname may have special meaning:

A leading "**" followed by a slash means match in all directories. For example, "**/foo" matches file or directory "foo" anywhere, the same as pattern "foo". "**/foo/bar" matches file or directory "bar" anywhere that is directly under directory "foo".

A trailing "/**" matches everything inside. For example, "abc/**" matches all files inside directory "abc", relative to the location of the .gitignore file, with infinite depth.

A slash followed by two consecutive asterisks then a slash matches zero or more directories. For example, "a/**/b" matches "a/b", "a/x/b", "a/x/y/b" and so on.

Other consecutive asterisks are considered invalid.





