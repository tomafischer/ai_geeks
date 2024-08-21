# GIT

## Basics branching
```bash
####
# git checkout replaced by:
####
# switching branchwes
git switch <branch name>  # switch branchs
# restoring files
git restore <file_name> # reset the file to the last staged or repo
git restore --staged <file_name
```

## Push new branch to remote
```bash
git push -u origin <branch>
```

## Rename a branch
```bash
git branch -m <old_name> <new_name>
```

## Delete branch
```bash
git push -d <remote_name> <branchname>   # Delete remote - usually <remote_name> will be origin
git branch -d <branchname>               # Delete local
```
