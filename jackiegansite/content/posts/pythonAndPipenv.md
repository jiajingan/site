---
title: "Python and Pipenv"
date: 2022-09-19T13:16:52-04:00
draft: false
---

Python is a great language for everyone. Easy to understand, and a lot of libraries to mess around with.<br>
However, managing packages in python can be a pain. Also, installing it the right way. 
* I had to personally witness this myself.......
---
# Installing Python (on macOS)
I'm a big fan of [brew](https://brew.sh/), brew is a Package Manager for macOS (something like apt-get in linux). More info please check out [this](https://docs.python-guide.org/starting/install3/osx/).
1. Open terminal and run this command to install homebrew
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
2. Also add this path to dotfile and `source` it
```
# Python with brew PATH
export PATH="/usr/local/opt/python/libexec/bin:$PATH"
```
3. install python with brew
```
brew install python
```
# Install and use Pipenv
Pipenv is a virtual environment to isolate your pip packages. I use it to for all my classwork and personal projects.
1. Open terminal and run this command, for more info visit [pipenv page](https://pipenv.pypa.io/en/latest/install/).
```
pip3 install --user pipenv
```
2. Find your pipenv path, your path is usually '/Users/joe/Library/Python/3.10' (yours might differ).
```
python3 -m site --user-base
```
3. Add your path (pipenv is in bin directory, remember to add /bin) and source it.
```
export PATH="$PATH:/Users/joe/Library/Python/3.10/bin"
```
or add this
```
export PYTHON_BIN_PATH="$(python3 -m site --user-base)/bin"
export PATH="$PATH:$PYTHON_BIN_PATH"
```
4. Pipenv is actually pretty easy to use
    * To install packages, `pipenv install <package>` such as django, numpy
    * To start environment, `pipenv shell`
    * Install development packages, `pipenv install <package> --dev`
    * Uninstall packages, `pipenv uninstall <package>`
    * Install packages with 'requirements.txt', `pipenv install -r ./requirements.txt`
    * To check if pipenv works and vulnerabilities in packages, `pipenv check`
    * To update packages pipfile and lock file, `pipenv install`
    * To display packages and dependencies on those packages, `pipenv graph`
    * When you are in another environment (For Example you pull from github), your pipenv packages will get messed up.
        * run `pipenv lock`, looks into the pipfile.lock file
        * then run `pipenv install --ignore-pipfile`, this will install everything from pipfile.lock(where you left off)
    * To remove pipenv from current dir, `pipenv --rm`
    
