---
title: "IT Infrastructure Mentorship Part 1"
author: "Myles"
---

# IT Infrastructure VLAB 1 

Part 1 of this series will focus on building the virtual environment from which we'll be installing our operating systems, roles, and services.

Below is a list of computing requirements I prefer your PC meet/exceed, however I've linked a site with a comprehensive list of the bare minimum requirements for our uses as well.

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
 
![Download options](assets\images\class_p1\Vboxdownload.PNG)


Proceed through VirtualBox's installation using default settings. This should be fairly easy but contact me if you run into any difficulties. Once the installation is complete start up the application. 

<br>

## Installing our OS Images within VirtualBox

Upon starting VirtualBox you should be met with a screen similiar to the one below.

![VirtualBox Start Up](assets\images\class_p1\VboxStart.PNG)

<br>

We will now build our first Virtual Machine. Select new from the menu top-center.

![New](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\Vboxnew.PNG)

For a name input Windows 2019 Server and be sure to select Windows 2019 64-bit as this is correct for even remotely modern CPUs.

![Settings](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\2016server.PNG)

Next we'll be provisioning the amount of RAM to be used by the Virtual Machine. Assuming you have at least 8 GBs and certainly if you have 16 GBs or more set the amount to 4096 MB aka 4 GBs.

![RAM](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\VboxRAM.PNG)

We're now creating our virtual hard drive, leave this to the default option which should be the same as shown below, if not change it to mirror the photo. Now select Create.

![VHD](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\VboxVHD.PNG)

Leave this to default selection as well.
![VDI](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\VboxVDI.PNG)

Select default option again this time - Dynamically allocate. The difference between the two is that by selecting dynamic allocation your virtual hard drive can grow beyond the size we provision for it without any user interaction. The alternate Fixed size means if our virtual hard drive fills up, we will need to manually expand it.

![Dynamic](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\VboxDynamic.PNG)

You may choose the file location for your hard drive or you can leave it at the default location. I suggest the former. Choose a hard drive size of 40 GB this should leave plenty of room for us to install services and applications as necessary.

![Hard Drive Size](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\VboxDriveSize.PNG)

Finally select create once more.

![FirstVM](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\VboxFirstVM.PNG)

You've done it you've created your first VM (virtual machine). Go ahead and start it up!

![GiveIso](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\GiveMeIso.PNG)

You were probably just met with this screen no? That's because we've only created the shell of the virtual machine, there's no operating system installed. Now it's time to put our Server 2019 ISO to good use. Sekect the folder icon to the right of the drop down menu, select add in the top left corner and navigate your downloads folder where the ISO most likely resides. Select this and press open. You should now see something like this 

![ODS](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\VbocODS.PNG)

I have a couple extra operating systems in there due to previous projects but you should see your Windows2019.iso file at least. Highlight it and select choose, then start. You've now fed your computer a virtual disk, that is basically what an ISO is, a virtual image of a disc.

If your screen looks the same as the image below congrat you've made it your OS installation screen. This concludes part 1 of the tutorial. You may close out of the screen and VirtualBox application. My suggestion is do two more like this soon after, except it'll be for our Windows 10 image instead. Make sure when you're building the VM you select an appropriate title and the correct operating system as show beneath.

![osoptions](C:\Users\Myles\Desktop\jekyll_real\midnight\assets\images\class_p1\osoptions.png)

I look forward to see you at part 2 of this series where we'll be installing our operating systems and possibly a role on our new Windows 2019 Server.









