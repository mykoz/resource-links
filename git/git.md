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
```
$ git show
$ git checkout featurebranch
$ git cherry-pick 1d5b2e
```





