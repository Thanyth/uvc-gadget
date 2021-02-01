# Chapter II - Software

## 1 - Initial setup and Git

### Raspberry Pi OS setup

#### Update softare

  1. `sudo apt-get update`     
  1. `sudo apt-get upgrade -y`
  1. `sudo apt-get install git -y`

#### Enable camera

  1. `sudo raspi-config`
     - `3 Interface Options`
     - `P1 Camera`
       - `<Yes>`
     - `<Finish>`
       - Would you like to reboot now?
         - `<No>`
           > Here it's up to you if you want to reboot.  
           > Personnaly I didn't want to until I've reach the end of the configuration of UVC-GADGET.

### Get the repository from GitHub

1. Clone the repository to the home folder in your Pi:  
   ``` bash
   # Need to be test to see if some variable aren't change (like they should have been)
   git clone https://github.com/Thanyth/uvc-gadget.git
   ```  
   > In theory you shouldn't have move from the home foler (`/home/pi`).  
   > If somehow you are no longer there, before clonning the git you can verify that you are at the good directory by doing `cd /home/pi`.

### Rapberry Pi OS configuration

  - [next part](22RaspOSconfigs.md)
