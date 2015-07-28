---
published: true
title: VMware Player in Headless Mode
layout: post
---
As most of you might know, <a href="https://my.vmware.com/web/vmware/free#desktop_end_user_computing/vmware_player/7_0"VMware Player</a> is a free (albeit limited) alternative to VMware Workstation.  One of the most significant limitations that I was always annoyed with was you can’t run a guest virtual machine without keeping it's console window open.  Recently, I discovered a work around for this and I figured I’d pass it along.  Please note that these instructions are for VMware Player 7.1.2 and Windows 7 x64, so you might have to modify the instructions based on your particular situation.

Go to the %UserProfile%\Application Data\VMware\preferences.ini file, and open it with notepad. Add the following lines to the file (or modify the existing entry if one of these values exists already):  

pref.vmplayer.exit.vmAction = "disconnect"
pref.vmplayer.confirmOnExit = "FALSE"

Restart VMPlayer and launch your guest VM.  You can now close the window and the VM will continue to run without interruption.  Obviously, if you turn off your PC or terminate the vmware-vmx.exe process it will kill any guest VMs.
