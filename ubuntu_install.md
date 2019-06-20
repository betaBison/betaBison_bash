# Installing Ubuntu 18.04.2 Desktop on Lenovo Ideapad 720
## Errors with mouse not moving and system hanging on reboot and shutdown
Seemed to be resolved by installing Nnvidia driver.  
  
Detect model and view recommended driver:  
`ubuntu-drivers devices`  
Install recommended driver:  
`sudo ubuntu-drivers autoinstall`

## Remove trash, other visual fixes
Install:  
`sudo apt install gnome-tweak-tool`  
run the gnome tweaks gui:  
`gnome-tweaks`
