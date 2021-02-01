# Chapter III - Debug

**IMPORTANT**:  
I'aint a dev or know code language. I learn on the go. So here is all my note about issue I've stumble accross. And I wouldn't unbplug the Pi (except if feed dead?) before giving it the command to shutdown via SSH. I use `sudo shutdown now` or something like that. I wait for both my hub and Pi0w LED to turn off before unplugging it. I always SSH in the background as soon as the Pi is on, so whenever a bug happen, I will have the shutdown command fast. 

## Latency

If you find the video feed (webcam) with too much latency (behind your voice/mouvement), I'm unsure why exactly it's doing that. But one of the thing I've been doing is trial and error. It's pretty easy, you just change those value bellow with whatever you think will work.
``` bash
cat <<EOF > /sys/kernel/config/usb_gadget/pi4/functions/uvc.usb0/streaming/mjpeg/m/1080p/dwMinBitRate
1658 
# The best one I've try is 100
EOF
cat <<EOF > /sys/kernel/config/usb_gadget/pi4/functions/uvc.usb0/streaming/mjpeg/m/1080p/dwMaxBitRate
3317
# Less latancy would be 1000
EOF
cat <<EOF > /sys/kernel/config/usb_gadget/pi4/functions/uvc.usb0/streaming/mjpeg/m/1080p/dwMaxVideoFrameBufferSize
41472
# I don't remember the last time I've try it but if I'm not mistaken it was 4147 the less problem
EOF
```
But in any of those modification, you will see (only tested in Discord) more artefact and the feed will crash faster. Could be a hardware limitation on my end. 

Playing around with the value bellow in the `uvc-gadget.c` could help. It's known on many forum that the 55 value shouldn't be change if you want your MacOS to have a webcam feed.  
``` bash
define PU_BRIGHTNESS_MIN_VAL 0
define PU_BRIGHTNESS_MAX_VAL 255
define PU_BRIGHTNESS_STEP_SIZE 1
define PU_BRIGHTNESS_DEFAULT_VAL 55  # this value is either 127 for PC or 55 for Mac 
```

Someting that doesn't add up is the USB speed of `uvc-gadget.c` when you compare it to either the linux github or peterbay fork. Those value are *surprise* use for MacOS `-s1`. If I understand correctly what High Speed USB Mode is, the `1024` should be at `2048`. Even though from [kinweilee](https://github.com/kinweilee/v4l2-mmal-uvc/blob/1bd2f3eda562da631365c05fa55379065b358310/README#L143) it can even be at `3072`. And it's not the only source, I just forgot to include all the other (about 3).
``` bash
    switch (speed) {
    case USB_SPEED_FULL:
        # /* 0 Full Speed */
        if (bulk_mode)
            udev->maxpkt = 64;
        else
            udev->maxpkt = 1023; # /* ok */
        break;

    case USB_SPEED_HIGH:
        # /* 1 High Speed */
        if (bulk_mode)
            udev->maxpkt = 512;
        else
            udev->maxpkt = 1024; # /* could it be that simple */
        break;

    case USB_SPEED_SUPER:
    default:
        # /* 2 Super Speed */
        if (bulk_mode)
            udev->maxpkt = 1024;
        else
            udev->maxpkt = 1024; # /* could concern PC user */
        break;
    }
```

## General issue

*under construction*
