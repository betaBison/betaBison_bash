# betaBison_bash
simple bash solutions to problems

## mousemouse
moves the mouse over and back a pixel every 5 minutes so monitior never sleeps.  

Install Dependencies:  
`sudo apt install xautomation`  

Add the following to the end of .bashrc:   
`~/<betaBison_bash repo location>/betaBison_bash/mousemove.bash &`

## common bash history
creates common bash history among multiple termninals  

Add the following to the end of .bashrc:  
```
# don't duplicate
export HISTCONTROL=ignoredups:erasedups
# append to history file
shopt -s histappend
```
## shorten directory location
displays `<username>@<hostname>:<current directory>$`

Replace the similar looking lines of code in .bashrc with the following:  
```
if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u\[\033[00m\]:\[\033[01;34m\]\W\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u:\W\$ '
fi
unset color_prompt force_color_prompt
```
## rename multiple files
Setup:  
`sudo apt install mmv`  
use:  
`mmv ~/old_name\* ~/new_name\#1`
