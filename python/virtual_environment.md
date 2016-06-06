###Virtual Environment

  1. `$  python --version` - Outputs the current version of Python in this system package, should be `Python 2.7.6`.
  2. `$  mkdir mlworkshop` - Creates a directory (folder) named `mlworkshop`
  3. `$  cd mlworkshop` - Changes the current path to the `mlworkshop` directory just created
  4. `00:00 ~/mlworkshop $  virtualenv --system-site-packages --python python3 venv` - Creates a Python 3 virtual environment named `venv`
  5. `00:00 ~/mlworkshop $  source venv/bin/activate` - Activates the `venv` virtual environment just created
  6. `00:00 ~/mlworkshop $  python --version` - Outputs the current version of Python in this virtual environment, should be `Python 3.4.0`.

*:notebook: Notice that in the next step (venv) appears at the left indicating we are now in the virtual environment. :notebook:*

  7) `(venv)00:00 ~/mlworkshop $  pip install statsmodels mpld3` - installing some extra Python packages to make data analysis more interesting.

  8) `(venv)00:00 ~/mlworkshop $  alias ipython="python -c 'import IPython; IPython.terminal.ipapp.launch_new_instance()'"` - ensures correct version of `ipython` is used, only valid while the bash shell is active (you may need to retype this if you restart the PythonAnywhere shell) ([details here](http://stackoverflow.com/a/26482258))

  9) `(venv)00:00 ~/mlworkshop $  echo alias ipython=\""python -c 'import IPython; IPython.terminal.ipapp.launch_new_instance()'\"" >> ~/.bashrc` - makes sure that the correct version of `ipython` is used in every bash shell ([details here](http://unix.stackexchange.com/questions/129143/what-is-the-purpose-of-bashrc-and-how-does-it-work))

---

http://chrisstrelioff.ws/sandbox/2014/09/04/virtualenv_and_virtualenvwrapper_on_ubuntu_14_04.html
```
$ workon

$ workon tree
$ pip list

$ rmvirtualenv test_env01

$ deactivate
```

