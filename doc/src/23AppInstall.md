# Chapter II - Software

## 3 - App installation and service

At this point you should already have the fork clone on your Pi. If not, you might have skip one or more step so go back to [Initial setup and git](21SetupGit.md)

### Running the service

  1. `sudo cp ~/uvc-gadget/piwebcam.service /etc/systemd/system/`
  1. `sudo systemctl enable piwebcam`  
     If it don't work you might want to go in the `uvc-gadget` folder and try there  
     > ``` bash
     > cd ~/uvc-gadget
     > sudo systemctl enable piwebcam
     > ```

### Installation 

  1. `cd ~/uvc-gadget && make`  
     Building the uvc-gadget app
  1. `sudo ln -s /lib/systemd/system/getty@.service  /etc/systemd/system/getty.target.wants/getty@ttyGS0.service`  
     Adding a serial to allow the service to run at boot  
     > Note: you can take the long road with the [jonikarppinen](https://gist.github.com/jonikarppinen/47dc8c1d7ab7e911f4c9) gist  
     > You are able to not reboot until this last step and it work.

### Debug

  1. [next chapter](31Debug.md)
