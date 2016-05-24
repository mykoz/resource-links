
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
####
```bash
reshama$ git status
On branch master
Your branch is behind 'origin/master' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)
nothing to commit, working directory clean
reshama$ git pull
```


