# Bash Configuration

This is a collection of Bash things I need to smooth out.

## `.bashrc`

In the fourth to last section of `.bashrc`, there is:
```
# some more ls aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
```
Change `la` to:
```
alias la='ls -al'
```

...

## Bash Aliases

There is no need to make Bash compatible with aliases in `.bashrc`, since this
is already included in the penultimate "section" of `.bashrc`:
```
# Alias definitions.
# You may want to put all your additions into a separate file like
# ~/.bash_aliases, instead of adding them here directly.
# See /usr/share/doc/bash-doc/examples in the bash-doc package.

if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi
```

Simply create `~/.bash_aliases` to get started.

I will post `.bash_aliases` so I don't have to struggle so much with a vanilla\
install ever again.

[//]: # (10:27pm on May 30, 2022)
