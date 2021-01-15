---
title: "IT Infrastructure Mentorship Part 1"
author: "Myles"
---

<br>

<br>

# Virtual Infrastructure Lab 1 

Part 1 of this series will focus on building the virtual environment from which we'll be installing our operating systems, roles, and services. One thing I want you to keep in mind while working through this and subsequent lab is: Attempt to work through issues! Don't waste two hours of your time on something, but given a solid try, and contact me only after that's failed. I've tried to be thorough in my documentation, but it is not exhaustive. There may be things I've overlooked or mistakes on your side. I would go so far as to say it's a good thing when you run across issues, you need the ability to work through problems. Problem-solving is an incredibly important part of working in IT, and most fields for that matter. That's it, I wish you the best of luck!

Below is a list of computing requirements that I prefer your PC to meet/exceed, however I've linked a site with a more comprehensive list of the absolute minimum requirements as well.

| [**Prerequisites**](https://www.techrepublic.com/article/virtualbox-everything-the-pros-need-to-know/#:~:text=Minimum%20system%20requirements%20are%3A,start%20at%2010%20GB%20each.) |
| :---:    |
| Windows 10 or Linux OS |
| 8GB RAM |
| 64-bit dual core CPU |
| 256 GB HDD |

<br>

There are three files we will initially need: a Windows 2019 ISO, a Windows 10 Enterprise ISO, and a virtualization software of some kind. For our purposes we'll be using Oracle's VirtualBox application. I've added links to them below
<br> 

[Windows Server 2019](https://www.microsoft.com/en-US/evalcenter/evaluate-windows-server-2019?filetype=ISO)
- Make sure you have the ISO selected, not Azure or VHD.

[Windows 10](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-10-enterprise)
- The same applies here, get the Enterprise ISO

 [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)
 - Select the appropriate download for your OS from here.

![Download options](\assets\images\class_p1\Vboxdownload.PNG)


Proceed through VirtualBox's installation using the default settings. This should be fairly easy, but contact me if you run into any difficulties. Once the installation is complete, start up the application. 

<br>

## Installing our OS Images within VirtualBox

Upon starting VirtualBox you should be met with a screen similiar to the one below.

![VirtualBox Start Up](\assets\images\class_p1\VboxStart.PNG)

<br>

We will now build our first Virtual Machine. Select new from the menu top-center.

![New](\assets\images\class_p1\Vboxnew.PNG)

For a name, input Windows 2019 Server and be sure to select Windows 2019 64-bit. This is correct for nearly all modern CPUs, if you have error while booting from your ISO later on in this lab contact me, as you may have a x86 processor.

![Settings](\assets\images\class_p1\2016server.PNG)

Next we'll be provisioning the amount of RAM to be used by our Virtual Machine. Assuming you have at least 8 GBs and certainly if you have 16 GBs or more, set the amount equal to 4096 MB which is equivalent to 4 GBs.

![RAM](\assets\images\class_p1\VboxRAM.PNG)

We're now creating our virtual hard drive, leave this to the default option which should be the same as shown below, if not change it to mirror the photo. Now select Create.

![VHD](\assets\images\class_p1\VboxVHD.PNG)

Leave this to default selection as well.

![VDI](\assets\images\class_p1\VboxVDI.PNG)

Select the default option again of - Dynamically allocate. The difference between the two is that by selecting dynamic allocation, your virtual hard drive can grow beyond the size we've provision without any user interaction. The alternate - Fixed size means if our virtual hard drive fills up, we will need to manually expand it.

![Dynamic](\assets\images\class_p1\VboxDynamic.PNG)

You may choose the file location for your hard drive or you can leave it at the default location. I suggest the former. Choose a hard drive size of 40 GB which should leave plenty of room for us to install services and applications as necessary.

![Hard Drive Size](\assets\images\class_p1\VboxDriveSize.PNG)

Finally select create once more.

![FirstVM](\assets\images\class_p1\VboxFirstVM.PNG)

You've done it, you've created your first VM (virtual machine). Go ahead and start it up!

![GiveIso](\assets\images\class_p1\GiveMeIso.PNG)

You were probably just met with this screen. No? That's because we've only created the shell of the virtual machine. Imagine you've just finished putting all the components of your new PC together, but **gasp** you forgot to *buy* a copy of an operating system! Fortunately, we have a handy dandy copy of Windows Server 2019 in the form of an ISO. Select the folder icon to the right of the drop down menu, select add in the top left corner, and now navigate to your downloads folder where the ISO likely resides. Select it and press open. You should now see something similar to this.

![ODS](\assets\images\class_p1\VbocODS.PNG)

I have a couple extra operating systems in there due to previous projects but you should see your Windows2019.iso file at least. Highlight it and select choose, then start. You've now fed your computer a virtual disk, essentially what an ISO is, a virtual image of a disc.

If your screen looks the same as the image below congrats you've made it to your OS installation screen. This concludes Part 1 of the Virtual Infrastructure tutorial. You are safe to close out of the screen and the VirtualBox application. You do need to attempt to install OS just yet. Instead, my suggestion is you create two more like this, except it'll be for our Windows 10 image this time around. Make sure when you're building the VM you select an appropriate title and operating system as show below.

![osoptions](\assets\images\class_p1\osoptions.png)


Please email me when you have successfully completed all three or are having issue with some part of the process.

<br>
<br>












