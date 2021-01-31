# Chapter II - Software

## 0 - Git repository modification

> Everything is aim at mac compatibility. I do not own Windows PC so no test is or will be made.
> It should be note that **this doc is only to inform you on what change I've made to climberhunt fork**. All change bellow are integrated in the clone repo you are now. So it will contain more explaination than the other doc in the src folder.

#### General uvc-gadget setup

  1. Edit the piwebcam executable file `nano ~/uvc-gadget/piwebcam`. 
     - Scroll to the last line and change the parameter `-f1 -s2 -r1` to `-f1 -s1 -r1`
       > 0 = Full Speed (FS)
       > 1 = High Speed (HS)
       > 2 = Super Speed (SS)
     - Save with `CTRL[⌃]+[o]` follow by `[enter]` and exit with `CTRL[⌃]+[x]` 
  1. Edit the piwebcam system service file `nano ~/uvc-gadget/piwebcam.service`.
     - Change the description under `[Unit]` to `Start pi webcam service`.

#### Camera uvc-gadget setup

> Need to modify the `multi-gadget.sh` file first before copying the directory in the system and building the app. 
> That file name should really be change to something less pain to remember to type/long for no reason. Probably have impact elsewhere so... Search needed.

  1. `sudo nano ~/uvc-gadget/multi-gadget.sh`
  1. *Optional* change the name of the device. So when you connect via USB you will have a custon name
     > Scroll down to the 16th line and change `"PI4 USB Device"` to your taste
     >  You can change the manufacturer name at the line before if you desire
  1. At the 29 line, change `5000000` to `333333`
     The original git, other fork and the linux git mention the `dwFrameInterval` is in 100ns units. [see uvc_driver.c](https://github.com/torvalds/linux/blob/c4439713e82a0d746e533ae5ddd7dfa832e2a486/drivers/media/usb/uvc/uvc_driver.c#L381) 
     Thus far when you calculate the frame per second (fps) you want it add up.
     > 30fps is `1/30 * 10 000 000 = 333 333`
  1. Line 38, 41 and 44 change them to (respectively) `1658`, `3317`, `41472`
     > From what I found [Alex comment](http://www.davidhunt.ie/raspberry-pi-zero-with-pi-camera-as-usb-webcam/#comment-107218) it is the best bet on the speed to put at those variable. But from [peterbay doc](https://github.com/peterbay/uvc-gadget/blob/master/doc/src/frame-resolution.md) and other forum, those 3 line change aren't the best configuration. The only problem is that when those correct value are entered, the Pi don't want to work. So probably other config files need to be change to allow those right value. Those value might need to be change. Real value should be `165 888 000`, `331 776 000` and `4147200`

#### 
  >
  1. 
``` bash
# the clonse link will need to be change to my fork when all the setup guide is done. so it shoule be /thanyth/uvc-gadget.git
# Speed first apperance in github https://github.com/torvalds/linux/blob/bec4c2968fce2f44ce62d05288a633cd99a722eb/drivers/usb/gadget/function/f_uvc.c#L478
# Linux other mention https://github.com/torvalds/linux/blob/bec4c2968fce2f44ce62d05288a633cd99a722eb/drivers/usb/gadget/function/f_fs.c#L121
# Peterbay wanted to collab with that user who code is in his fork. Asking there? https://github.com/kinweilee/v4l2-mmal-uvc/blob/master/v4l2-mmal-uvc.c 
# Original git https://git.ideasonboard.org/uvc-gadget.git/blob/c4f79214e425ae26ec9c27cc0995122321631b87:/lib/uvc.c#l295
``` 

### Rapberry Pi OS configuration
<!--- Temporary file so no need for this part--->
  1. [next part] (src/22RaspOSconfigs.md)