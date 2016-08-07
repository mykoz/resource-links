#Git: working cleanly

[How do I copy a version of a single file from one git branch to another?](http://stackoverflow.com/questions/307579/how-do-i-copy-a-version-of-a-single-file-from-one-git-branch-to-another)  

###Copy file from one branch to current branch
Run this from the branch where you want the file to end up:  
```
git checkout otherbranch myfile.txt
```

###Copy directory from one branch to current branch
```
git checkout other-branch myfolder/** 
```

###More Commands
```
git diff --stat "$branch"
git checkout --merge "$branch" "$file"
git diff --stat "$branch"
```
