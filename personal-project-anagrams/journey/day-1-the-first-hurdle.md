---
description: Settin' it all up.
---

# Day 1: The first hurdle

My original plan to set up an instance of MacOS on VirtualBox and code there turned out to not only be complicated, but also inefficient and illegal.&#x20;

VirtualBox does not have native support for MacOS, and getting a MacOS iso file requires shady and illegal downloads from websites like Mega.

## A forbidden setup

I spent over an hour sifting through articles and reddit threads about iOS development on windows. In order to get an instance of MacOS on VirtualBox, I would need to download the extension package and utilize this very appealing block of code:

```
cd "C:\Program Files\Oracle\VirtualBox\"
VBoxManage.exe modifyvm "Type Your Virtual Machine Name Here" --cpuidset 00000001 000106e5 00100800 0098e3fd bfebfbff
VBoxManage setextradata "Type Your Virtual Machine Name Here" "VBoxInternal/Devices/efi/0/Config/DmiSystemProduct" "iMac11,3"
VBoxManage setextradata "Type Your Virtual Machine Name Here" "VBoxInternal/Devices/efi/0/Config/DmiSystemVersion" "1.0"
VBoxManage setextradata "Type Your Virtual Machine Name Here" "VBoxInternal/Devices/efi/0/Config/DmiBoardProduct" "Iloveapple"
VBoxManage setextradata "Type Your Virtual Machine Name Here" "VBoxInternal/Devices/smc/0/Config/DeviceKey" "ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc"
VBoxManage setextradata "Type Your Virtual Machine Name Here" "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC" 1
```

Even so, people were complaining about how laggy and slow the eventual development environment would be. Other options included renting a Mac through the cloud via this website: [https://www.macincloud.com/](https://www.macincloud.com/). However, the impermanence and limitations of this method turned me away.

## Next steps

I honestly shouldn't be surprised; Apple's dedication to maintaining their ecosystem has always been apparent. Bottom line: for iOS development, I need a Mac.&#x20;

Luckily I was able to get one powerful enough to run XCode for very cheap; however, it will be a few days until I can get my hands on it.&#x20;

This is a blessing in disguise however, as I now have forced planning time. In this waiting period, I can start to plan the architecture of the app with user stores, class diagrams, and activity diagrams so that when I get my hands on the right coding environment, much of the heavy lifting has already been done.

My current plan is to use [https://www.drawio.com/](https://www.drawio.com/) to build the different diagrams as I am familiar with the software from my intro to software dev college course. However, tomorrow I will look into possible alternatives as I remember drawio's interface being a bit of a hassle.
