---
title: "Alias command"
date: 2020-07-08T02:26:10+05:30
tags: ["shell", "commands"]
---


Writing long commands is boring. Essentially shortening the commands or chaining of commands helps. This can be achieved using `alias` command. [Alias](https://en.wikipedia.org/wiki/Alias_(command)) command is mainly used for abbreviating a system command, or for adding default arguments to a regularly used command.   
  
Example, instead of writing:

```bash
git add .  
git commit -m "COMMIT MESSAGE"
git push
```  
we can write following to achieve the same goals.
```bash
gc "COMMIT MESSAGE"  
gp  
```

In the example, chaining of git commands has been done. Git doesn't allow chaining using `git alias` command but we can simply overcome that by `alias` command shown. Do visit  [git-scm.com](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases) to evaluate what's best for your use case.
 
Implementation of `alias` command can be found in [usage](#usage) section. Some use cases can be found in [use case](#use-cases) section.

## Usage
### For GNU/Linux (bash)

1. Add `.bash_aliases` in `~` (`/home/USER_NAME`) 

```bash
$ touch ~/.bash_aliases
```

2. Open the file using editor and add

```bash
alias gc='git add . && git commit -m '
alias gp='git push'
```
_Bear in mind, no spaces between the alias target and alias input commands and single quotes only._

3. In terminal 

```bash
$ source ~/.bash_aliases
```
4. Restart terminal.


### For Windows (Git Bash)

1. Run git bash in administrator mode.

2. Navigate to `C:\Program Files\Git\etc\profile.d` .

```bash
 cd ../../Program\ Files/Git/etc/profile.d/
```

3. Open `aliases.sh` using nano 

```bash
nano aliases.sh
```

4. Add following in the end:

```bash
# CUSTOM ALIASES

alias gc='git add . && git commit -m'
alias gp='git push'
```
_Bear in mind, no spaces between the alias target and alias input commands and single quotes only._

5. For saving and exiting nano

```bash
CTRL+O 
# PRESS ENTER
CTRL+X 
```
6. Restart terminal.

## Use Cases

Some useful aliases can be:

```bash
alias update='sudo apt update && sudo apt upgrade'
alias rm='rm -i'
alias gc='git add . && git commit - '
alias gp='git push'
alias gr='git restore --staged'
```

My bash aliases can be found [here](https://github.com/sahilister/dotfiles/blob/master/.bash_aliases).







