

```
# print present working directory
pwd
# create new directory
mkdir prework
# list files
ls
# change directory, go into prework directory
cd prework
# clone the repo
git clone https://github.com/reshama/dsp.git
# list files
ls
# change directory, go into dsp
cd dsp
ls
# see what the remotes are
git remote -v
# use editor to view and edit file
emacs 00-fork_repo.md
# check if any changes have been made to local repo; changed files will be in red
git status
# add a file, also means 'staging file'
git add 00-fork_repo.md
# check that file is staged, staged file will be in green
git status
# commit a file; adding message to commit to track changes made
git commit -m 'added emoji'
# check that file has been committed
git status
# push file to forked repo
git push
# clear screen
clear
# list files
ls
  657  emacs 00-fork_repo.md
  658  git remote -v
  659  git pull
  660  ls
  661  emacs 00-fork_repo.md
  662  clear
  663  history
  
  
  
