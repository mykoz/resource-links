##Process for Having a Most Amazing Bash Prompt

1.  This is what my terminal prompt used to look like (boring but safe):  
`reshama$ `

2.  Go to this website and choose an emoji.  Copy it.  
http://getemoji.com/

####Update bash profile 

3.  Go to your bash profile.  
`reshama$ emacs ~/.bash_profile`

4a.  Add this line.  (Of course, you copy and paste the emoji of your choice and whatever name you like to see.)  
`export PS1="reshama 🐘  $ “`

4b.  Save and exit.
ctrl-x ctrl-s  (to save file using Emacs)  
ctrl-x ctrl-c  (to exit Emacs)

5.  Run your updated bash profile file.  
`reshama$ source ~/.bash_profile`

6.  Voila!  My terminal prompt now looks like:  
`reshama 🐘  $ `

*Note:*  I used Emacs editor here, but you can use any editor of your choice.  
