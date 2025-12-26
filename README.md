# Windows95 install procedure in 2025

¿why? </br>
because NTVDM was deprecated in W11 </br>
its very hard to [compile on Win8.1x64](https://github.com/leecher1337/ntvdmx64) </br>
is very easy to install in [Win10 32-Bit](https://learn.microsoft.com/en-us/windows/compatibility/ntvdm-and-16-bit-app-support) Only. </br>

    Enable NTVDM: PowerShell> DISM /online /enable-feature /all /featurename:NTVDM
    Disable NTVDM: PowerShell> DISM /online /disable-feature /featurename:NTVDM

Maybe Win8.1x32 also has NTVDM </br>

[NTVDMx64](https://github.com/leecher1337/ntvdmx64) based on OpenNT is hard to compile, Hard to Find dependencies, </br>
WineVDM [OTVDM](https://github.com/otya128/winevdm) is an alternative. </br>

NTVDM [story](https://github.com/leecher1337/ntvdmx64) is interesting to read, </br>
same as W95Fix CPU README. </br>

installing Real Win95 is easy & fast. </br>

#1. Download 95se "B" .iso haven't tested "C" </br>
#2. Download 1.44" Floppy Win95 Boot .img "Win95.iso does Not Boot" </br>
#3. Download [VirtualBox 6.1.50](https://www.virtualbox.org/wiki/Download_Old_Builds) or older, "6.1.50 VM driver install CD does Not work, NT3 drivers does Not work."
#4. install VBox or similar, VMware Fusion Player 11.2 "OSX Catalina" or VMware Workstation Player "Windows", QEMU, GEM5, 86Box, PCem.co.uk, ProxMox </br>
Parallels for OSX Not recommended because 1 time paid version "Non-Subscription" has a limit on Virtual SATA controller, speed is SATA-1 1.5Gbps or SATA-2 3Gbps cant remember. </br>
#5. create a small machine: 512MB RAM, 512MB IDE HDD, limit CPU speed as low as possible 350MHz less. </br>
#6. create Dynamic .vhd | .vhd can be mounted later in Win8.1x64 Disk Manager to transfer files fast & easy, unmount & Run VM again, VM partition where .vhd is, must be NTFS. </br>
exFAT is prefered for most other things, transfer files between OSX Linux & Windows R/W. </br>
#7. boot from W95 Floppy </br>

    FDISK

Create Primary Partition, Exit, Reboot. </br>

#8. Format is Not included on the 1.44MB W95 Boot Floppy, </br>
its on a folder in the W95 CD.iso </br>

      d:
      cd folder
      format c: /s 
Reboot, Remove Floppy, Boot from Win95se .iso </br>

#9. install Windows95 </br>
*Do Not change Generic VGA Display Adapter, wont boot, requires Safe-mode Boot. </br>

#10. Download & boot Win95 CPU FixCD.iso | Update Win95 B to Fix most problems with Faster Machines. </br>
there are different: [patcher9x](https://github.com/JHRobotics/patcher9x) & [Fix95CPU v3](http://lonecrusader.x10host.com/fix95cpu.html) + [PatchMem](http://lonecrusader.x10host.com/rloew/patchmem.html)</br>
#11. once Update is Done, reboot, remove CD.iso, reboot, Boot Win95, mount CD.iso again, has a partition with 1 software VMM.exe install that File, Unmount .iso, Reboot. </br>
#12. install [dotNet9x](https://github.com/itsmattkc/dotnet9x/releases) Backport of .NET 2.0 -> 3.5 to Windows 9x [video story here](https://www.youtube.com/watch?v=CTUMNtKQLl8) </br>
#13. increase VM CPU speed to 100%, if continues to have boot problems, dissable Nested Virtualization in VirtualBox 6.1.50 </br>
#14. install [SoftGPU driver](https://github.com/JHRobotics/softgpu) </br>
#15. install CPU-Z [Vintage Edition](https://www.cpuid.com/news/66-cpu-z-vintage-edition.html) Win9x [.zip](https://www.cpuid.com/downloads/cpu-z/cpu-z_1.04-win9x.zip) </br>


Basically thats it. </br>
to have Super VGA screen resolution, requires installing VirtualBox CD drivers, but v6.1.50 does Not work "Not W95 compatible" </br>
requires older VirtualBox driver CD or SoftGPU drivers </br>
VirtualBox 6.1.50 driver CD is more compatible with Win8.1x64 </br>

86Box try to have time accurate HW emulation "emulation of Old Hardware" requires Real Drivers. </br>
Win95 B has built-in audio drivers/support for VirtualBox SounBlaster16 </br>
some old software does Not run if Date is too far away in the future, </br>
requires to manually change the system clock or a software like [nirsoft RunAsDate v1.41](https://www.nirsoft.net/utils/run_as_date.html) </br>
