---
published: true
title: VMware Player - Headless Mode
layout: post
---
As most of you might know, VMWare Player is a free (albeit limited) alternative to VMware Workstation.  One of the limitations that I was always annoyed with was you can’t run a guest vm without having the console window open.  I just discovered a little work around for this and I figured I’d forward it out to you guys in case anyone else might find it useful…

Go to the %UserProfile%\Application Data\VMware\preferences.ini file, and open it with notepad.

Add the following lines to the file (or modify the existing entry if one of these values exists already):  

pref.vmplayer.exit.vmAction = "disconnect"
pref.vmplayer.confirmOnExit = "FALSE"

Restart VMPlayer and launch your guest VM.  You can now close the window and the VM will continue to run without interruption.  Obviously, if you turn off your PC or terminate the vmware-vmx.exe process it will kill any guest VMs.

(Directions tested on Windows 7 x64, your mileage my vary.)