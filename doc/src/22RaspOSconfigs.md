# Chapter II - Software

## 2 - Raspberry Pi OS configuration (system)

### Boot kernel setup

  1. `sudo nano /boot/config.txt`
      > Scroll all the way down to the last line (whatever you have has a last line)
    - Add an extra line at the end. Then add `dtoverlay=dwc2`
      ``` bash
      # Exemple withouth the extra line
        [all]
        #dtoverlay=vc4-fkms-v3d
        start_x=1
        gpu_mem=128
      
      # Exemple with the extra content
        [all]
        #dtoverlay=vc4-fkms-v3d
        start_x=1
        gpu_mem=128
        dtoverlay=dwc2
      ```
    - Save and quit the "nano" command
      > `CTRL[⌃]+[o]` follow by `[enter]` and `CTRL[⌃]+[x]`
  1. `sudo nano /boot/cmdline.txt`
      > Scroll to the end of the **single** line
      > **Important** do not add new lines
    - Find the last `rootwait`
      > Should be near the end.
    - Add a space (`[spacebar]`) follow by `modules-load=dwc2,libcomposite`
    - Save and quit the "nano" command
      > `CTRL[⌃]+[o]` follow by `[enter]` and `CTRL[⌃]+[x]`

### Application install

  1. [next part] (src/23AppInstall.md) 

<!--- Rapberry Pi OS configuration --->
<!--- NB Note for me while doing this guide. Will be included if you want to start from climberhunt fork. Should be done before the app install but after the setup git since you need his clone git to work on it. --->
<!--- [before app install] (src/22RaspOSconfigs.md) --->

