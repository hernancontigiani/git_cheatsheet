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

## Change author commit
For example, if your commit history is A-B-C-D-E-F with F as HEAD, and you want to change the author of C and D, then you would...
- Specify git rebase -i B (here is an example of what you will see after executing the git rebase -i B command)
- if you need to edit A, use git rebase -i --root
- Change the lines for both C and D from pick to edit
- Exit the editor (for vim, this would be pressing Esc and then typing :wq).
- Once the rebase started, it would first pause at C
- You would git commit --amend --author="Author Name <email@address.com>"
- Then git rebase --continue
- It would pause again at D
- Then you would git commit --amend --author="Author Name <email@address.com>" again
- git rebase --continue
- The rebase would complete.
- Use git push -f to update your origin with the updated commits.

Reference:
https://stackoverflow.com/questions/3042437/how-to-change-the-commit-author-for-a-single-commit
