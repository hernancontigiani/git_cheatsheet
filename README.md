# Git cheatsheet
GIT cheatsheet

## submodules
Add git submodule from <repository>/<branch>
```sh
$ git submodule add -b <branch> --name <folder_name> -- <repository_branch_link> <folder_name>
```
Update submodule to last commit
```sh
$ git submodule update --remote --merge
```
