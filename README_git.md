# GIT

## Basics branching
### Switching Branches (checkout old way)
```bash
# list all branches (local and remote)
git branch -a
####
# git checkout replaced by: switch and restore
### switching branchwes
git switch <branch name>  # switch branchs
#### restoring files
git restore <file_name> # reset the file to the last staged or repo
git restore --staged <file_name
```
### New Branch
```bash
git switch -c <new_branchname>
# or old way
git checkout -b iss53
# shorthand for
$ git branch <new_branchname>
$ git switch <branchname>

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

## Tagging
```bash
# show all the tags
git tag
# show all the tag details
git tag -l -n

# adding an anootated Tag
# -a is for annotate 
git tag -a v0.9 -m "Initial release version"

# pusing all tags to origin
git push origin --tags
# pushing a specific tag
git push origin v0.9

# create a branch and checkout 
git checkout -b tag/v0.9 v0.9
```
