

###References

[Stack Overflow:  How do you undo the last commit](http://stackoverflow.com/questions/927358/how-do-you-undo-the-last-commit)  
[Stack Overflow:  Remove files from last commit](http://stackoverflow.com/questions/12481639/remove-files-from-git-commit)  

---


Where you are:  
 * you've committed some files, pushed to your local repo, and want to delete the commit

####View the commit log
```console
reshama$ git log -1
commit f2e80f37be66f7cc17f88c642c736ecf5e227ace
Author: reshama <rs2715@gmail.com>
Date:   Tue May 24 10:02:57 2016 -0400

    updating links
reshama$ 
```
####How to undo a commit
```console
git reset --soft HEAD^     # use --soft if you want to keep your changes
git reset --hard HEAD^     # use --hard if you don't care about keeping the changes you made
```
```
reshama$ git reset --soft HEAD~1    #use --soft to preserve changes that were made and undo last commit (~1 = back 1 commit)
```

####Check status of files
```
reshama$ git status
On branch master
Your branch is behind 'origin/master' by 3 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   test1.md
	new file:   test2.md

reshama$ 
```


####
```bash
reshama$ git status
On branch master
Your branch is behind 'origin/master' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)
nothing to commit, working directory clean
reshama$ git pull
```


