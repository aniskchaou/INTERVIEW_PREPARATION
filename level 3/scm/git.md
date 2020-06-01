

## Git

**Git**  is an  **open-source distributed version control system**.

Git is foundation of many services like  **GitHub**  and  **GitLab**, but we can use Git without using any other Git services.

**We do not need to connect to the remote repository; the change is just stored on our local repository. If necessary, we can push these changes to a remote repository.**
![enter image description here](https://res.cloudinary.com/practicaldev/image/fetch/s--D7nJOADN--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://cl.ly/569e7f0bbfaf/download/Image%25202018-08-29%2520at%25208.26.35%2520PM.png)


# Git Terminology



### HEAD

HEAD is the **representation of the last commit** in the current checkout branch.

### Index

The Git index **is a staging area** between the working directory and repository.

### Master

Master is a naming convention for Git branch. It's a default branch of Git. 

### Origin

In Git, "origin" **is a reference to the remote repository** from a project was initially cloned. 

### Pull/Pull Request

The term Pull is used to receive data from GitHub. It fetches and merges changes on the remote server to your working directory. The  **git pull command**  is used to make a Git pull.

Pull requests are a process for a developer to notify team members that they have completed a feature. Once their feature branch is ready, the developer files a pull request via their remote server account. **Pull request announces all the team members that they need to review the code and merge it into the master branch.**
### Git Fork

A fork is a rough copy of a repository. **Forking a repository allows you to freely test and debug with changes without affecting the original project.**
## Ignoring files

    -   .gitignore 
    Specify intentionally untracked files that Git should ignore. Create .gitignore:  
    $ touch .gitignore List the ignored files:  
    $ git ls-files -i --exclude-standard

## Commands

Here are the Git commands which are being covered:

-   **git config**
-   **git init**
-   **git clone**
-   **git add**
-   **git commit**
-   **git diff**
-   **git reset**
-   **git status**
-   **git rm**
-   **git log**
-   **git show**
-   **git tag**
-   **git branch**
-   **git checkout**
-   **git merge**
-   **git remote**
-   **git push**
-   **git pull**
-   **git stash**

So, let's get started!

## **Git Commands**

### git config

Usage: `git config –global user.name “[name]”`

Usage: `git config –global user.email “[email address]”`

This command sets the author name and email address respectively **to be used with your commits.**

![Git Config Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/1-9.png)

**Check the setting:**  

    $ git config -list

### git init

Usage: `git init [repository name]`

This command is used **to start a new repository**.

![GitInit Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/2-6.png)

### git clone

Usage: `git clone [url]`

This command is used **to obtain a repository from an existing URL.**

![Git Clone Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/4-4.png)

### git add

Usage: `git add [file]`

This command adds **a file to the staging area**.

![Git Add Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/5-4.png)

Usage: `git add *`

This command adds **one or more to the staging area.**

![Git Add Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/6-3.png)

### git commit

Usage: `git commit -m “[ Type in the commit message]”`

This command records or snapshots the file permanently in the version history.

![Git Commit Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/7-3.png)

Usage: `git commit -a`

This command commits **any files you’ve added with the git add** command and also commits any files you’ve changed since then.

![Git Commit Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/8-2.png)
**Changing the Last Commit:**

 

    git commit --amend

The git commit --amend command is a convenient way to modify the most recent commit. 


### git diff

Usage: `git diff`

This command shows the file differences **which are not yet staged.**

![Git Diff Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/9-2.png)

`Usage: git diff –staged`

This command shows the differences between the files **in the staging area and the latest version present.**

![Git Diff Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/10-2.png)

Usage: `git diff [first branch] [second branch]`

This command shows the differences **between the two branches mentioned.**

![Git Diff Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/43.png)

    Track the changes that have not been staged: $ git diff  
    Track the changes that have staged but not committed:  
    $ git diff --staged  
    Track the changes after committing a file:  
    $ git diff HEAD  
    Track the changes between two commits:  
    $ git diff Git Diff Branches:  
    $ git diff  < branch 2>

### git reset

Usage: `git reset [file]`

This command **unstages the file**, but it preserves the file contents.

![Git Reset Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/11-1.png)

Usage: `git reset [commit]`

This command undoes all the commits after the specified commit and preserves the changes locally.

![Git Reset Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/14-1.png)

Usage: `git reset –hard [commit]`  This command discards all history and goes back to the specified commit.

![Git Reset Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/13-1.png)
**Git revert**  

    Undo the changes:  
    $ git revert  
    Revert a particular commit:  
    $ git revert

### git status

Usage: `git status`

This command lists all the files that have to be committed.

![Git Status Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/15-1.png)

### git rm

Usage: `git rm [file]`

This command deletes the **file from your working directory** and stages the deletion.

![Git Rm Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/16-2.png)

### git log

Usage: `git log`

This command is used to **list the version history** for the current branch.

![Git Log Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/18.png)

Usage: `git log –follow[file]`

This command lists version history for a file, including the renaming of files also.

![Git Log Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/19.png)

### git show

Usage: `git show [commit]`

This command shows the metadata and content changes of the specified commit.

![Git Show Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/20.png)

### git tag

Usage: `git tag [commitID]`

This command is used to give tags to the specified commit.

![Git Tag Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/22.png)

### git branch

Usage: `git branch`

This command lists all the local branches in the current repository.

![Git Branch Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/23.png)

Usage: `git branch [branch name]`

This command creates a new branch.

![Git Branch Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/24.png)

Usage: `git branch -d [branch name]`

This command deletes the feature branch.

![Git Branch Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/25.png)

### git checkout

Usage: `git checkout [branch name]`

This command is used to switch from one branch to another.

![Git Checkout Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/27.png)

Usage: `git checkout -b [branch name]`

This command creates a new branch and also switches to it.

![Git Checkout Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/28.png)

### git merge

Usage: `git merge [branch name]`

This command merges the specified branch’s history into the current branch.

![Git Merge Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/31-1.png)

### git remote

Usage: `git remote add [variable name] [Remote Server Link]`

This command is used to connect your local repository to the remote server.

![Git Remote Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/32.png)

### git push

Usage: `git push [variable name] master`

This command sends the committed changes of master branch to your remote repository.

![Git Push Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/33.png)

Usage: `git push [variable name] [branch]`

This command sends the branch commits to your remote repository.

![Git Push Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/34.png)

Usage: `git push –all [variable name]`

**This command pushes all branches** to your remote repository.

![Git Push Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/36.png)

Usage: `git push [variable name] :[branch name]`

**This command deletes a branch on your remote repository**.

![Git Push Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/37.png)

### git pull

Usage: `git pull [Repository Link]`

This command fetches and merges changes on the remote server to your working directory.

![Git Pull Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/38.png)

### git stash

Usage: `git stash save`

This command temporarily stores all the modified tracked files.

![Git Stash Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/39.png)

Usage: `git stash pop`

This command restores the most recently stashed files.

![Git Stash Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/40.png)

Usage: `git stash list`

This command lists all stashed changesets.

![Git Stash Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/44.png)

Usage: `git stash drop`

This command discards the most recently stashed changeset.

![Git Stash Command - Git Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/07/42.png)

    Switch branches without committing the current branch. Stash current work:  
    $ git stash  
    Saving stashes with a message:  
    $ git stash save ""  
    Check the stored stashes:  
    $ git stash list  
    Re-apply the changes that you just stashed:  
    $ git stash apply  
    Track the stashes and their changes:  
    $ git stash show  
    Re-apply the previous commits:  
    $ git stash pop  
    Delete a most recent stash from the queue:  
    $ git stash drop  
    Delete all the available stashes at once:  
    $ git stash clear  
    Stash work on a separate branch:  
    $ git stash branch

## Git rebase
![Git Stash Command - Git Commands - Edureka](https://miro.medium.com/max/2682/1*MUDSg35O-XJCP3EN-kNsUg.png)
![Git Stash Command - Git Commands - Edureka](https://miro.medium.com/max/1736/1*g48HJkKNsZwNlWEM6Z82ig.jpeg)
![enter image description here](https://i.stack.imgur.com/fb6L4.png)
 Before merge/rebase:

```
A <- B <- C    [master]
^
 \
  D <- E       [branch]

```

After  `git merge master`:

```
A <- B <- C
^         ^
 \         \
  D <- E <- F

```

After  `git rebase master`:

```
A <- B <- C <- D' <- E'

```

(A, B, C, D, E and F are commits)

    -   **Git rebase**  
        Apply a sequence of commits from distinct branches into a final commit.  
        $ git rebase  
        Continue the rebasing process:  
        $ git rebase -continue Abort the rebasing process:  
        $ git rebase --skip
    -   **Git interactive rebase**  
        Allow various operations like edit, rewrite, reorder, and more on existing commits.  
        $ git rebase -i
### git remote
**Git remote**  

    Check the configuration of the remote server:  
    $ git remote -v  
    Add a remote for the repository:  
    $ git remote add Fetch the data from the remote server:  
    $ git fetch  
    Remove a remote connection from the repository:  
    $ git remote rm  
    Rename remote server:  
    $ git remote rename  
    Show additional information about a particular remote:  
    $ git remote show  
    Change remote:  
    $ git remote set-url
### git fetch
![enter image description here](https://miro.medium.com/max/600/1*SKR0Zz4S0M_0Rp-aPsZw0Q.png)
    Transfer the commits from your local repository to a remote server. Push data to the remote server:  
    $ git push origin master Force push data:  
    $ git push -f  
    Delete a remote branch by push command:  
    $ git push origin -delete edited
## Git Squash Commits

In Git, the term squash is used to squash the previous commits into one. It is not a command; instead, it is a keyword. The squash is an excellent technique for group-specific changes before forwarding them to others. You can merge several commits into a single commit with the compelling interactive rebase command.

![enter image description here](https://miro.medium.com/max/1200/1*8GsjZXPaKv-C_1eFK0D1XQ.png)