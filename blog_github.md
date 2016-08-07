##Blog Hosted on GitHub

####References

[barryclark/jekyll-now repo on GitHub](https://github.com/barryclark/jekyll-now)

[Building a Blog with Jekyll and GitHub Pages](https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/)

Tufte theme:
http://jekyllthemes.org/themes/tufte-jekyll/


https://mmistakes.github.io/minimal-mistakes/docs/configuration/  

####What is Jekyll?
A static website builder.  
Process:  make template + make content --> run Jekyll --> get site of static HTML pages  
Pros:
 * faster site (simple, no database connection)
 * more secure
 * less maintenance
 * lower cost
 * free hosting on GitHub
 * blog aware - can write content in markdown

Jekyll - ruby app you install on your system  

---

http://jekyllrb.com/

####Install Jekyll on your machine
`$ sudo gem install jekyll`  

```console
reshama$ gem install jekyll
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /Library/Ruby/Gems/2.0.0 directory.
reshama$ sudo gem install jekyll

```
####Check which version of Jekyll is installed
`$ jekyll -v`  

```console
reshama$ jekyll -v
jekyll 3.1.6
reshama$ 
```

####Create project
`$ jekyll new blog`  

```console
reshama$ jekyll new blog
New jekyll site installed in /Users/reshamashaikh/ds/metisgh/blog. 

reshama$ cd blog
reshama$ pwd
/Users/reshamashaikh/ds/metisgh/blog
```

####Run Jekyll
`$ jekyll serve`  

```console
reshama$ jekyll serve
Configuration file: /Users/reshamashaikh/ds/metisgh/blog/_config.yml
            Source: /Users/reshamashaikh/ds/metisgh/blog
       Destination: /Users/reshamashaikh/ds/metisgh/blog/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
                    done in 0.275 seconds.
 Auto-regeneration: enabled for '/Users/reshamashaikh/ds/metisgh/blog'
Configuration file: /Users/reshamashaikh/ds/metisgh/blog/_config.yml
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
[2016-05-28 12:55:38] ERROR `/favicon.ico' not found.
[2016-05-28 12:55:38] ERROR `/favicon.ico' not found.
```
My site is up and running at:  
http://127.0.0.1:4000/



####Are there different website themes I can choose from with Jekyll?
Yes, lots.  
http://jekyllthemes.org/

####Where do I begin?
1. Go to your github homepage.  (For me, it is:  https://github.com/reshama)  
2. Search in the upper left box for keyword.  We'll try the 'emerald' theme:  emerald
3. This is the theme you're looking for:  https://github.com/KingFelix/emerald
4. Fork the repo under your account name. 
5. Change branch to:  gh-pages
6. Go to:  Settings  
      a.  /Options    Change repo name to:  `yourgithubusername.github.io`. This is a GitHub convention for making a "user page".  (For me, it will be:  `reshama.github.io`  
      b.  /Branches.   Change default branch to: gh-pages.  Select:  "Update"  
7. We will close the repo in the following directory.  (Change your username from "reshamashaikh".)  
```bash
reshama$ pwd
/Users/reshamashaikh/ds/metisgh
reshama$ 
```


 * Fork the [barryclark/jekyll-now](https://github.com/barryclark/jekyll-now) repo to your GitHub account.
 * Rename your fork to be called `yourgithubusername.github.io`. This is a GitHub convention for making a "user page".
 * Notice you now have a web site at `yourgithubusername.github.io`.
 * Clone your fork to your local machine with `git clone`.
 * Edit the files locally (both configuration and markdown files), commit, and push back up to your fork on GitHub.
 * Break the "fork" relationship on GitHub by deleting the repo on GitHub, creating a new blank repo, and pushing back from your local machine.

https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/




[How to create Jekyll blog using Github Pages - Tutorial 4 (8-minute video)](https://www.youtube.com/watch?v=U0idtvxVo9I)

[How to edit and add new posts in Jekyll blog online - Github Pages Tutorial 8 (10-minute video)](https://www.youtube.com/watch?v=E0RbrYSMw3g)

Search at home page:  emerald
https://github.com/

KingFelix/emerald
A minimal and mobile-first blog theme for Jekyll 

https://github.com/KingFelix/emerald

---

jekyll serve - converts markdown to HTML

colons in table - centers left  
collections - [another webpage or drop down]  
default menus:  Posts, About  

book:  Fluent Python  (recommended by LM)  

mathjax  
* data options: data/options.yml
* 

