---
layout: post
title: Rebuild a UEFI boot partition
date: 2020-02-26
---

## Preface  
There may come a day when you need to rebuild the boot partition.  In my case took a [Disk2VHD](https://docs.microsoft.com/en-us/sysinternals/downloads/disk2vhd) capture of a laptop and it would not boot when I hooked it up to Hyper-V.  The following got me running.
  
## Rebuilding the boot partition  
Boot into a Windows installation disk and select **Repair your computer**  
Now select **Troubleshoot**  
Then **Command Prompt**  
Now enter  
```
1  diskpart  
2  list vol  
3  sel volume 3  
4  assign letter=L:  
5  exit  
6  L:  
7  format L: /fs:fat32  
8  bcdboot c:\windows /s L: /f UEFI
9  exit
```  
Now you can select **Continue** or **Turn off your PC**  
Hopefully now your new VM can boot
