# How to guide (ish) for installing uvc-gadget on Pi W (webcam)

> **READ FIRST**: I must warn you that this repository isn't the most up to date out there. I don't know a better way of saying it than how [geerlingguy] (https://github.com/geerlingguy/uvc-gadget/blob/master/Readme.md) wrote it : 
> « This repository was originally forked from [climberhunt] (https://github.com/climberhunt/uvc-gadget), which itself was forked from [whle] (https://github.com/wlhe/uvc-gadget), which is a fork from the [original project] (http://git.ideasonboard.org/uvc-gadget.git)... so it's a little bit of a mess here. »
>
> I must agree with him on his next point. I hate misleading, unfinished or hard-to-read documentation. So by doing documentation, I'm kinda doing exactly the opposite. Well... Yeah in a way. My goal is to make it so you don't have long paragraph that can [mislead you really easy] (http://www.davidhunt.ie/raspberry-pi-zero-with-pi-camera-as-usb-webcam/#comment-105545).
>
> Combining whatever I found into one big folder his my method. Everytime I found new information that I think can help, I'm adding it to the references. I might not have directly use it, but I prefer having more than not enougth. But all the instruction will be *almost* free of documentation. I will directly write what to do, if no explanation is needed, it won't be there. 
>
> I have no clue on what I'm doing, I'm learning on the go. I have tested my method and it is working with a somewhat caveat. The end result output a feed with some glitch (only tested over a USB 2.0 Hub) and isn't perfectly "live". The other caveat is the video feed can crash after a period of time, even though your Pi is still connected over SSH. 
>
> **WARNING**: This repository is using "outdated" upstream. Meaning that Peter Bay upstream is now where many people are centralizing there time. This pretty sweet idea is an (and cheep) alternative to webcam. As of writing, webcam here in Canada are still overprice (beginning of 2021. I *might* update some file whenever I found error or someone his pointing out better variable. But in an overall look, It won't be maintained for long. 
>
> I will try in the near futur to install peterbay repository without the showmewebcam firmware. Since peterbay himself have installed it without the need for the custom firmware [see issue 1] (https://github.com/peterbay/uvc-gadget/issues/1#issuecomment-723582852). So this clone is like a practice since I *will* make one for peterbay since none exist. 
>
> *- Thanyth* 

## Introduction

Why make a guide if many already exist like by [David Hunt] (http://www.davidhunt.ie/raspberry-pi-zero-with-pi-camera-as-usb-webcam/), [Jeff Geerling] (https://www.youtube.com/watch?v=8fcbP7lEdzY), [Whle] (https://github.com/wlhe/uvc-gadget) and many more unknown to me. I love Jeff Geerling approach, but I'm not a fan of installing Ansible on my Mac (or any other software never heard before). So my goal his to *try* to combine the guide by Mr. Hunt with Mr. Geerling way into one quick guide simple to follow with no explanation on every step.

**LINUX-BASED FIRMWARE PACKAGE**
If you want a maintained firmware package with faster boot time and *known to work* user in the wild, please check out [showmewebcam] (https://github.com/showmewebcam/showmewebcam). As of writing, that firmware is using PeterBay fork of uvc-gadget that are both maintained. 

**IF YOU ARE CURIOUS AND DIY TYPE** I will still recommend you to go to peterbay fork since it's not outdated and faster. And I've only test it on a Raspberry Pi Zero W with HQ camera. I won't test it on other Pi. It is known to **not** work on Pi4. See [geerlinggue issue 5] (https://github.com/geerlingguy/pi-webcam/issues/5) for more information. 

## Chapter 0 - Hardware requirements

*TO BE DONE*

## Chapter 1 - RapberryPi OS Installation

I will cover it in another git project. Or a gist. Or in the doc folder of this project. TBD 
*. / UNDER CONSTRUCTION / .*

## Chapter 2 - Software
<!--- (OK) COMPLETED SECTION ---> 

   0. [climberhunt modification] (src/20climberhuntSetup.md)
     > If you want to know the difference between my fork and his. **Informational purpose only**. All modification are already made.
   1. [Initial setup and Git] (src/21SetupGit.md)
   2. [RaspOS configuration] (src/22RaspOSconfigs.md)
   > *part 2 and 3 can be switch if you want (untested)*
   3. [App install] (src/23AppInstall.md)

## Chapter 3 - Debug



## SOURCES, HELP, MATERIAL... ORIGINAL OWNERS CREDITS

#### INSPIRATIONS/CREDITS 

> Section on where you could have seen some word use, exemple or any other thing worth mentionning. Little bit like an archive purpose so whenever I'm asking myself where I got the info, I have one place to go. Even though it will probably be unsorted, at least there are in one spot. And all author should be mentionned. 
    - Base on the idea of [mbruggmann] (https://github.com/mbruggmann/uvc-gadget/blob/master/Readme.md)  
    - Markdown comments [jonikarppinen] (https://gist.github.com/jonikarppinen/47dc8c1d7ab7e911f4c9) 
    - This `Readme.md` layout was inspire by [geerlingguy] (https://github.com/geerlingguy/pi-webcam/blob/master/README.md)
    - How to exit command line [text-editors.md] (https://www.raspberrypi.org/documentation/linux/usage/text-editors.md) 
    - 

#### FORKS 
<!--- (OK) COMPLETED SECTION --->

All forks *somewhat* used from the previous fork until David Hunt (this fork is based on his fork). So I don't include what he already quote as source in his *now archived* fork.  
   - Original [uvc-gadget.git](http://git.ideasonboard.org/uvc-gadget.git)
   - Fork(copy) [uvc-gadget.git - wlhe](https://github.com/wlhe/uvc-gadget)
   - Fork(copy) [uvc-gadget.git - climberhunt / Dave Hunt](https://github.com/climberhunt/uvc-gadget)

#### GUIDES/INFORMATION ABOUT UVC-GADGET OR USB WEBCAM WITH RASPBERRY PI

All source that I don't know where to put them or just a general information source. Tottaly unclassed.
   - 

#### QUOTE USED

This is all source/quote use somewhere in my take on the code. They *should* all have the same number has those reference bellow. 
   1. Source for parameter of [uvc-gadget] (src/20climberhuntSetup.md) [KWLee] (https://www.raspberrypi.org/forums/viewtopic.php?f=38&t=148361&sid=f7f6f624b3bb82a93bca7e493cf07f8d&start=50#p1731113) 
   1. 

#### REFERENCES

The difference about this section sit on the "code" use. So everything in reference *should* only be the general website on where I got my information. For comment/forum that have been copy-paste will be either in this general reference section or in the quotations one. `If you have an idea on how better classified it hit me up`
  - [Explaination](https://gist.github.com/justinschuldt/36469e2a89d95ef158a8c4df091e9cb4) (somewhat) on how Mr. Hunt decide to include or exclude
    > This is the "original" documentation that many people base there Pi Webcam over USB on if I'm not mistaken. 
  - Base on the guide/how to provided by [David Hunt](http://www.davidhunt.ie/raspberry-pi-zero-with-pi-camera-as-usb-webcam/)
    > Many comments used are from his website.
  - [Forum](https://www.raspberrypi.org/forums/viewtopic.php?t=148361) where the discussion first took place


## Author notes
<!--- (OK) COMPLETED SECTION --->

French Canadian!  
I don't do typo on purpose, I'm just not here for the grammar. If something is really bothering you (or the way I wrote it is really confusing), please feel free to comment bellow.

*`Thanyth` everywhere (Twitter, GitHub, RaspberryPi Forum...)*

