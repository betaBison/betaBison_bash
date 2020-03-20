# Installing Ubuntu 18.04.2 Desktop on Lenovo Ideapad 720
Problems and fixes found in the dual boot process


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
## Force Linux to use local time
This fixes the issue of the clock in dual booted windows being off  
```
timedatectl set-local-rtc 1
```

## System Driver Update Mayhem
Windows requested to update system drivers. After the BIOS updated, mayhem ensued.  
Windows no longer would boot and showed the black screen of death  
```
Stop code: INACESSIBLE_BOOT_DEVICE
```  
Ubuntu also no longer would boot.  
```
Gave up waiting for suspend/resume device
Gave up waiting for rooot file system device. Common problems:
- Boot args (cat /proc/cmdline)
- Check rootdelay= (did the system wait long enough?)
- Missing modules (cat /proc/modules; ls /dev)
ALERT! UUID=bb36<***>b85c does not exist. Dropping to a shell!
(initramfs)
```
The solution was to adjust parameters in the UEFI firmware settings:
```
Security > Secure Boot > Disabled
Configuration > SATA Controller Mode > AHCI
Boot > Boot order > 1) Ubuntu 2) Windows
```
I then rebooted windows into safe mode (reached through startup settings).

```
