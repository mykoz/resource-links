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




