###PyGotham talk

tells current status of repo; will not change files
```bash
git status
```

gets basic information about commit
```bash
git show
```

hash:  totally unique identifier of a commit  

blame:   
* commit hash
* author's name
* date of commit
```
$git blame path/to/file.py
```

###cherry-pick 
How do I move my commit from one branch to another?  
save to use, only adding a commit, not deleting any commit
```
$ git show
$ git checkout featurebranch
$ git cherry-pick 1d5b2e
```

###reset
changes the pointers back one feature
HEAD - whatever commit I am currently sitting on  
HEAD == current commit  
HEAD~ == back one commit  
HEAD~~ == 
```
$ git checkout master
$ git reset --hard HEAD~
```

###rebase
command for changing history  
important to treat it with respect  
never change history when other people are using your branch (unless they know you're doing so)  
Never change history on master branch  
Best practice:  only change history for commits that you haven't pushed to git  

problem with merge  
find the merge base between 
```bash
$ git checkout featurebranch
$ git rebase master
$ git status
```

```
$ git push -f
```

###rebase - sometimes you get conflicts
fix conflicts  
```bash
$ git rebase --continue

```

###reflog
`git log`  
`git reflot`  shows commits in the order in which you referenced them  

Step 1:  find the commit you want  
Step 2:  `checkout` the commit 
Step 3:  `reset`


###squashing commits
```bash
$ git add missing-file.txt
$ git commit --amend
```

```bash
$ git rebase --interactive HEAD~5
```









###
