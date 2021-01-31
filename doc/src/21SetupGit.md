# Chapter II - Software

## 1 - Initial setup and Git

### Raspberry Pi OS setup

> Don't forget to connect to your Pi with your favorite method. Either via Wi-Fi (headless) or other. Method show below is my personnal way of doing it.
  - `ping raspberrypi.local`
    > Once you see result, `CTRL[⌃]+[c]` to stop terminal.app from his task
  -  

#### Update softare

  1. `sudo apt-get update`     
  1. `sudo apt-get upgrade -y`
  1. `sudo apt-get install git -y`

#### Enable fonction

  1. `sudo raspi-config`
      - `3 Interface Options`
      - `P1 Camera`
          - `<Yes>`
      - `<Finish>`
          - Would you like to reboot now?
            - `<No>`
               > Here it's up to you if you want to reboot. Personnaly I didn't want to until I've reach the end of the configuration of UVC-GADGET.

### Get the repository from GitHub

1. Clone the repository to the home folder in your Pi:
``` bash
# the clonse link will need to be change to my fork when all the setup guide is done. so it shoule be /thanyth/uvc-gadget.git
git clone https://github.com/climberhunt/uvc-gadget.git
``` 
  > In theory you shouldn't have move from the home foler (`/home/pi`). If somehow you are no longer there, before clonning the git you can verify that you are at the good directory by doing `cd /home/pi`.

### Rapberry Pi OS configuration

<!--- Temporary get to the other part [git modification] (src/20climberhuntSetup.md)--->
  - [next part] (src/22RaspOSconfigs.md)
