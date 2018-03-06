A simple git cheatsheet.

***

## Setup

### Initializing a repository
```
git init
```

### Cloning a repository
```
git clone repository-url.git
```

### Cleaning the cloned repository
```
rm -rf .git
```

### Adding a remote repository
```
git remote add origin repository-url.git
```

### Pushing to the remote repository
"origin" as the remote repository and "master" as the branch name
```
git push -u origin master
```
Typing `-u` allows the next pushes to be only `git push`

***

## Workflow

### Check actual status
```
git status
```

### Add files for staging area
```
git add filename
git add .
```

### Commit files
```
git commit -m "message"
```
Add modified files to staging area and commit (does not add untracked files)
```
git commit -am "message"
```

### Commit history
```
git log
git log --graph
```

### Reverting a file to the last commit stage
```
git checkout filename
```

***

## Reseting commits
All "resets" deletes the selected commits. The "commit-id" is the id refered to one commit below the commit(s) to be deleted.

### Reseting "soft"
Reverts the commit(s) and put files back in the staging area (modified files)
```
git reset --soft commit-id
```

### Reseting "mixed"
Reverts the commit(s) and put files back in the unstaged area (modified files)
```
git reset --mixed commit-id
```

### Reseting "hard"
Reverts the files back to the selected commit, without the modifications
```
git reset --hard commit-id
```

***

## Branches

### Creating a branch
```
git checkout -b branch-name
```

### Listing branches
```
git branch
```

### Changing from a branch to another
```
git checkout branch-name
```

### Merging branches
```
git merge branch-name
```
Checkout to master branch before

### Deleting branches
Delete a local branch
```
git branch -d branch-name
```
Delete a remote branch
```
git push origin --delete branch-name
```