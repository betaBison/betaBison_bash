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

