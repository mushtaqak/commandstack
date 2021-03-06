# GIT commands / Issues

### Rebasing  
git rebase with master branch  
> git checkout <yourbranch>  
> git rebase -i master  

rebase abort  
> git rebase —abort  

rebase continue  
> git rebase —continue  

git rebase with itself  
> git rebase HEAD~2 -i (last 2 commits on head; `-i` means interactive)   

### New Remote branch  
> git checkout --track -b origin/mushtaq/abc-branch  
> git checkout -b LocalName origin/mushtaq/abc-branch  

### Revert a commit  
> git revert <commit-id>  

### Delete tag  
> git tag -d release  

### Onstage all changes from commits  
> git reset --soft HEAD^  

### Stash  
NEW: Save with name  
> git stash save "<stash name>"  
> git stash apply stash@{0}  

Stash current changes  
> git stash  

Apply latest stash ( this pops stash)  
> git stash apply  

Show all stashes  
> git stash show  

### Rename/capitalizee a file  
> git mv -f MAKEFILE Makefile  

### Clean fd  
> git clean -fd  

### Reset version history   
- Remove all the version history from the local Git repository  
- http://stackoverflow.com/questions/9683279/make-the-current-commit-the-only-initial-commit-in-a-git-repository  

Step 0 : save your .gitignore file, so that you can add ignore list later for ease.  
Step 1: remove all history  
> rm -rf .git  
Step 2: reconstruct the Git repo with only the current content  
> git init  
> git add .    
> git commit -m "Initial commit"  
Step 3: push to GitHub.  
> git remote add origin <github-uri>  
> git push -u --force origin master  

### Git Reflog  
- The easiest way would be to find the head commit of the branch as it was immediately before the rebase started in the reflog... and to reset the current branch to it (with the usual caveats about being absolutely sure before reseting with the --hard option).  
- Suppose the old commit was `HEAD@{5}` in the ref log  
- > git reset --hard HEAD@{5}  

### Update file permissions (esp. script files)   
> `git update-index --chmod=+x release.sh`   
