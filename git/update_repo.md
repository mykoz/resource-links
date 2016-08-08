
Thank you for being so responsive to our most recent pre-work email. I can see that you have already forked the repository and  hope the work is going well. Just a heads up that we made a final update on Thursday, so the statistics portion of your repo is out of date. Worry not! It’s a workable fix (and you’ll learn more GitHub).

NOTE: If you have not cloned the repo yet, do that before you do this. You will need to be in your cloned repo for this to work. 

Navigate in your terminal to your working directory. Copy and paste the following: 

git remote add upstream https://github.com/thisismetis/dsp

Let’s make sure everything went ok. Type:

git remote -v

You should see the following:

$ origin https://github.com/YOUR _USERNAME/dsp.git (fetch)
$ origin https://github.com/YOUR_USERNAME/dsp.git (push)
$ upstream https://github.com/thisismetis/dsp (fetch)
$ upstream https://github.com/thisismetis/dsp (push)

Now type/copy the following:

git fetch upstream

And then:

git merge upstream/master
