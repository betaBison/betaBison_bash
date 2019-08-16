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

## Force overwrite of conflicting package
`sudo apt-get -o Dpkg::Options::="--force-overwrite" install <pkg_name>`

## Pip package location
`pip3 install <pkg_name> --user`  
The `--user` tag means that the package will be installed in `~/.local/bin`

## Simple Screen Recorder
```
sudo add-apt-repository ppa:maarten-baert/simplescreenrecorder
sudo apt-get update
sudo apt-get install simplescreenrecorder
```
