# Test repository
## This readme-file contains the tutorial for convenient work with git and zsh.

## sub header

### brew

* intall brew https://brew.sh

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

* install python 3.9

```
brew search python
brew install python@3.9
```

### ssh

* generate ssh id RSA key private and public

```
ssh-keygen
```

~/.ssh/id_rsa - private part
~/.ssh/id_rsa.pub - public part (to be uploaded to github)

```
cat ~/.ssh/id_rsa.pub
```

### github

* upload public part to github https://github.com/settings/keys
* create new empty repository "saved url"

### git

* Set git global params 
```
git config --global user.name "Your Name"
git config --global user.email your@email.com

```

* create folder
```
mkdir ~/Projects/test-repository
cd ~/Projects/test-repository
```

* init repository
```
git init
```

* create file
```
touch README.md
git add README.md
```

* commit to local repository
```
git commit -m 'added README.md'

```

* push to remote repository
```
git remote add origin "saved url"
git push --set-upstream origin master

```

* git check status

```
git status

```

## Second floor

### Installing themes oh-my-zsh: themes for zsh

https://ohmyz.sh/#install # Themes for terminal
```
compaudit | xargs chmod g-w,o-w # after installing, remove permissions on writing for
                                # owner and group

``` 
                                
### Instructions for Mark-down 
### https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

#### Print space before command to hide it in history

### Install command-line tools to BBEdit: open BBEdit and BBEdit=>Install
### Command Line tools

```
bbedit ~/.zshrc # Settings for shell (11 raw is shell name)
# if delete dir in 5-th raw, all settings will be deleted 
# (ex /Users/avo888/.oh-my-zsh)
```

> correcting of theme (ex /Users/avo888/.oh-my-zsh/themes) robbyrussell.zsh-theme

> Example of settings. 
> Docs: http://zsh.sourceforge.net/Doc/Release/Prompt-Expansion.html

```
# PROMPT="%(?:%{$fg_bold[green]%}➜ :%{$fg_bold[red]%}➜ )"
# PROMPT+=' %{$fg[cyan]%}%c%{$reset_color%} $(git_prompt_info)'

PROMPT="%D %* %{$fg[red]%}%n%{$reset_color%}@%{$fg[blue]%}%m %{$fg[yellow]%}%~ %{$reset_color%}%% "
PROMPT+='$(git_prompt_info)'

ZSH_THEME_GIT_PROMPT_PREFIX="%{$fg_bold[blue]%}git:(%{$fg[red]%}"
ZSH_THEME_GIT_PROMPT_SUFFIX="%{$reset_color%} "
ZSH_THEME_GIT_PROMPT_DIRTY="%{$fg[blue]%}) %{$fg[yellow]%}✗"
ZSH_THEME_GIT_PROMPT_CLEAN="%{$fg[blue]%})"
```
### Settings for Terminal:
### Terminal: Terminal => Preferences => Homebrew (make default
### in down the screen) 
### Right column: Font => Fixed width => PT mono => Bold and Size = 13

### Quit from Less (linux pager): Q or ctrl+c
### Turn off pager in terminal:
```
git config --global core.pager ''
```
### Turn on pager in terminal:
```
git config --global core.pager '' 
```
### Set editor to BBEdit (from vim to BBEdit):
```
git config --global core.editor 'bbedit --wait --resume' # wait and resume parametres
                                                # are for wait in command line and
                                                # resume after close file
```
### Set editor to VIM:
```
git config --global core.editor 'vim'
```

### Branches
### Master - only approved code = Production
### Develop - developers branch. Used by developers for test-approved developings.
###           Code which builds without problems, test passes etc

### Feature branche - individual branche for each task and each developer.

### Creating new branch from master:
```
git checkout master # switch to master
git pull # get last changes from server. Strategy merge (by default)
git branch feature_themes # add feature brunch with branch name
                          # it's recommended to name feature branch
                          # like feature_ + 'name of branch'
git checkout feature_themes # switch to created branch
# making changes
git add ...
git commit 
git push --set-upstream origin feature_themes
# You can open showed link, or go to  github and create pull-request
# (in gitlab merge-request, that equal pull-request in github)
```

## pip-env
## To look at all commits in current branch:
```
git log
```
## To look at selected commit:
```
git show selected_commit_hash
```
