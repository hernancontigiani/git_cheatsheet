# Git cheatsheet
GIT cheatsheet

## remove folder from history
In this example we remove node_modules from history:
```sh
$ git rm -r --cached node_modules
$ git commit -m "Updated the .gitignore file"
$ git push origin main
```

## submodules
Add git submodule from <repository>/<branch>
```sh
$ git submodule add -b <branch> --name <folder_name> -- <repository_branch_link> <folder_name>
```
Update submodule to last commit
```sh
$ git submodule update --remote --merge
```
