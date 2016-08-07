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

--

##Tips for Working Cleanly

###Launch your notebook from your working branch (not `master` branch)

###Adding files
* Do this:  `git add filename`
* DON'T do this:  `git add . `

-- 

#Git:  Proposed Workflow

1.  Fork, clone, git remote add upstream 
2.  Branching
3.  Work in reshama_wip branch, Launch notebook from reshama_wip branch
4.  Copy file to be merged into thisismetis/ds8 repo by copying into master branch from working branch
5.  
