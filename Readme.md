# Git & Github

## File Status Lifecycle
* **Untracked** -> file was created but is not tracked by git.
* **Unmodified** -> after a file is added/updated on git.
* **Modified** -> after editing the file.
* **Staged** -> ready for updating git with the current file version.
    * When the *commit* is made, the "Staged" files go back to being in and "Unmodified" status.

## Commands
### Basic Commands
* *git status* -> vê o status dos arquivos
* *git diff* -> vê a diferença entre as versões
* *git reset HEAD <file>* -> tira o arquivo da fila do Stage.
* *git checkout <file>* -> remove toda a mudança, antes do commit.
### Resetting
* To reset to a previous version:
    * *git reset --soft --mixed --hard*
        * *--soft* -> To undo previous modifications to a file, but keeping that file as Staged, ready to commit again.
        * *--mixed* -> To undo previous modifications, but returning that file to a Modified status (removes Staged status)
        * *--hard* -> To undo previous modifications and ignore everything.
### Cloning a Repository
1. Copy a repository SSH address.
1. In Terminal/Bash: *git clone <SSH link> <local repository name>*

### Forking a Repository
* Useful for copying a repo made by someone else to work on it, and then send the changes back.