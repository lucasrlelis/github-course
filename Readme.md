# Git & Github

## File Status Lifecycle
* **Untracked** -> file was created but is not tracked by git.
* **Unmodified** -> after a file is added/updated on git.
* **Modified** -> after editing the file.
* **Staged** -> ready for updating git with the current file version.
    * When the *commit* is made, the "Staged" files go back to being in and "Unmodified" status.

## Commands
### Basic Commands
* *git status* -> check file status
* *git diff* -> checks differences between current version and edited files
* *git add* -> adds Staged status to file.
* *git commit* -> commits changes.
    * git commit -m "Message" -> commits with a message. It's good practice to write about what was modified.
    * git commit -am "Message" -> adds Staged status to file + commits with a message.
* *git reset HEAD <file>* -> removes Staged status from file.
* *git checkout <file>* -> Removes all modifications (only before committing, otherwise you have to reset).
* **git stash** -> "stores" modifications to commit later (used to save a work in progress without comitting).
    * Commits with *git stash apply*
    * Used to keep a clean log, avoiding several small commits.

### Resetting
* To reset to a previous version:
    * *git reset --soft --mixed --hard*
        * *--soft* -> To undo previous modifications to a file, but keeping that file as Staged, ready to commit again.
        * *--mixed* -> To undo previous modifications, but returning that file to a Modified status (removes Staged status)
        * *--hard* -> To undo previous modifications and ignore everything.

### Reverting
* Reverts to a previous file version, but keeps that information on Git.
* If something goes wrong, you can use *git revert* to go back, and at a later time you can *checkout* on that commit to look into that code.

### Cloning a Repository
1. Copy a repository SSH address.
1. In Terminal/Bash: *git clone <SSH link> <local repository name>*

### Updating a Repository on Github
* *git push <destination> <source>* (**eg** *git push origin master*)

### Forking a Repository
* Useful for copying a repo made by someone else to work on it, and then send the changes back (with the owner's approval)
    * You can't clone a repository that isn't yours.
    * Technically you can, but you can't push the changes back.
* To fork, go to that repository's Github page.

### Branches
* Useful for editing files while making no changes to the main repository (master).
* Easily deletable.
* Allows for several people to work on the code simultaneously.
* Avoids conflicts.
* To create a branch:
    * *git checkout -b <branch name>*
* To check which are the current branches:
    * *git branch*
* To move to a different branch:
    * *git checkout <branch name>* (**eg** git checkout testing | git checkout master)
* To delete a branch:
    * git branch -D <branch name>

#### Merge
* Merges branches, such as testing + master.
* **Pros**:
    * Non destructive operation.
* **Cons**:
    * Requires extra commits.
    * Pollutes repository history (specially if there are several branches).

#### Rebase
* Moves commits to the end of a branch (easier to understand seeing an image).
* **Pros**:
    * Avoids extra commits.
    * Keeps a linear repository history.
* **Cons**:
    * Loses chronological order.

### .gitignore
* Used to make git ignore some files.
* Create a .gitignore file and specify in the file which files or file types should be ignored (eg *.json or <name>.<extension>).

### Tags
* You can use tags to create versions with git.
* *git tag -a 1.0.0 -m "Version 1.0.0: Readme done"*
    * -a: annotates
    * -m: message
* You can push tags to Github with *git push origin master --tags*

### Deleting Tags and Branches in Remote Repositories
* *git tag -d 1.0.0* - deletes tag 1.0.0 at the local repo.
* *git push origin :1.0.0* - pushes that deletion to the remote repo.

### Alias
* Create shortcut to commands.
* *git config --global alias.<shortcut> command*
    * Eg: *git config --global alias.s status* ('s' will work as a shortcut to status)