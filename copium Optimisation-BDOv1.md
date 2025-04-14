
# Updating for 2025

# General windows / BDO setup -  

General PC setup and tweaks for the avg BDO gamer, along with BDO setup i personally do, will cover a basic general setup and will go more in depth down the rabbit hole of trying to optimise  your PC. 

Taken info from many resources and put them together in this guide for the avg bdo gamer / casual trying to improve their experience.

this is about 95% of what i do there are some other tweaks but its way to trihard for the avg person and i cba explaining how to do them if you wanna know what else i do ask me in discord ig


## Windows installation 


## DISABLE Mouse acceleration!!!!
- Press Win + R to open the Run Command dialog box. paste the command into the box that pops up i will only say this once you're not this dumb to not realise you need to do this.
 ```powershell
 main.cpl
 ```
Untick this

![image](https://github.com/Tungrad/BDO/assets/126987283/66252b28-5463-46c4-93d5-c64bcbfefff0)


## Install Visual C++ Redistributable Runtimes

Download and install the [Visual C++ redistributable runtimes](https://github.com/abbodi1406/vcredist).

## Install .NET 4.8 Runtimes

Download and install the [.NET 4.8 runtimes](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net48). NET 4.8 already ships with Windows 10 1909+.

## Install DirectX Runtimes

Download and install the [DirectX runtimes](https://www.microsoft.com/en-gb/download/details.aspx?id=8109).


## Remove Bloatware Natively

- Windows 10+ Only:

    - Windows 10:

        - Uninstall bloatware in ``Apps -> Apps and Features`` by pressing ``Win+I`` uninstall programs you will not be using

        - In the ``Optional features`` section, uninstall everything apart from ``Microsoft Paint``, ``Notepad`` and ``WordPad`` if applicable (these do not exist in earlier Windows 10 versions)

    - Windows 11:

        - Uninstall bloatware in ``Apps -> Installed apps`` by pressing ``Win+I`` uninstall programs you will not be using

        - In the ``Apps -> Optional features`` section, uninstall everything apart from ``WMIC``, ``Windows PowerShell ISE``, ``Notepad (system)`` and ``WordPad``
     



- Open your start menu with windows key and unpin and uninstall items left over in here you will typically see tiktok etc
-  Restart your PC once to apply the changes above but i would hold off on restarting your pc till the end.


## Configure Memory Management Settings (Windows 8+)

If you are on an old system you may see some benefit as alaways i would test with this being off or on and see which gives you the best performance 

- Open PowerShell as admin and enter the command below

  ```powershell
    Disable-MMAgent -MemoryCompression
  ```
 ```powershell
    Disable-MMAgent -ApplicationPreLaunch
  ```

- Paste the next 2 in CMD
  
 ```powershell
    reg add "HKLM\SYSTEM\CurrentControlSet\Services\SysMain" /v "Start" /t REG_DWORD /d "4" /f
  ```
 ```powershell
    reg add "HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management\PrefetchParameters" /v EnablePrefetcher /t REG_DWORD /d 0 /f

  ```

## Configure Audio Settings
- Press Win + R to open the Run Command dialog box.
 ```powershell
 mmsys.cpl
 ```
The sound control window should pop up now, Follow [This](https://imgur.com/a/IpVCXBG) to configure your sound settings 

## Device manager/network settings
Open device manager

if you do not use wifi or bluetooth right click on the devices and disable them like so 

![image](https://github.com/Tungrad/BDO/assets/126987283/22d77a4b-6742-45c4-a1dd-120a6a153c30)

To disable all the powersaving features on devices fast and easy paste the following command into Powershell - if you care about powersaving features skip this i guess

 ```powershell
Get-WmiObject MSPower_DeviceEnable -Namespace root\wmi | ForEach-Object { $_.enable = $false; $_.psbase.put(); }
 ```

Now right click on your Network adapter that you will be using, be it  Wifi or lan one whichever and go to properties and click advanced i will list below what i change in here copy if you so wish up to you

- Advanced EEE - Disabled
- ARP Offload - Disabled
- EEE Max Support Speed - ﻿1.0 Gbps Full Duplex
- Energy-Efficient Ethernet - Disabled
- Flow Control - Disabled
- Gigabit Lite - Disabled
- Green Ethernet - Disabled
- Interrupt Moderation - Disabled
- IPv4 Checksum Offload - Rx & Tx Enabled
- Jumbo Frame - Disabled
- Large Send Offload v2 (IPv4) - Disabled
- Large Send Offload v2 (IPv6) - Disabled
- Maximum Number of RSS Queues - 4 Queues
- Ns Offload - Disabled
- Power Saving Mode - Disabled
- Priority & VLAN - Disabled
- Receive Buffers - 512
- Receive Side Scaling - Enabled
- Shutdown Wake-On-Lan - Disabled
- Speed & Duplex - Auto
- TCP Checksum Offload (IPv4) - Disabled
- TCP Checksum Offload (IPv6) - Disabled
- Transmit Buffers - 1024
- UDP Checksum Offload (IPv4) - Disabled
- UDP Checksum Offload (IPv6) - Disabled
- Wake on Magic Packet - Disabled
- Wake on pattern match - Disabled
- WOL & Shutdown LinkSpeed - Disabled

 Now do the following

- Open ``Network Connections`` by typing ``ncpa.cpl`` in ``Win+R``

- Disable any unused network adapters if you disabled wifi before hand you will see it being disdabled here also, then right-click your main one and select ``Properties``

- Disable all items except ``QoS Packet Scheduler`` and ``Internet Protocol Version 4 (TCP/IPv4)``

![image](https://github.com/Tungrad/BDO/assets/126987283/dc32d641-0089-4846-b12e-1244e469b33b)

- Disable ``NetBIOS over TCP/IP`` in ``Internet Protocol Version 4 (TCP/IPv4) -> Properties -> General -> Advanced -> WINS`` to [prevent unnecessary system listening](https://github.com/djdallmann/GamingPCSetup/blob/master/CONTENT/DOCS/NETWORK/README.md) for all network adapters


## Geforce

If you installed the driver normally or went via the NVcleaninstall route and manually installed geforce

You will want to disable these 3 in the Alt + z menu
- broadcast live
- Highlights
- Photo mode / game filter ( if you use this you can keep it on if not turn it off)

## Nvidia control panel 
Open nvidia control panel then head to program settings located in Manage 3D settings
![image](https://github.com/Tungrad/BDO/assets/126987283/d69ad0af-ed54-4759-8616-b57bf40eeee0)

Click Add and the browse head to C:\Windows\System32 and look for DWM.exe and add it
![image](https://github.com/Tungrad/BDO/assets/126987283/6350cffe-cadc-435e-9a9b-d4572bb2aed9)

Find the power management settings and set it to max performance instead of Nvidia  rec and click apply 
![image](https://github.com/Tungrad/BDO/assets/126987283/48c52111-9141-4da5-9e3d-802d5898b2ea)

Then do the same but for Explorer.exe which is located in C:\Windows

## Scaling 

tldr lower latency depending on which option you set it to it will provide lower latency 
typcally ppl suggest if you have a good gpu setting it to GPU scaling will provide the lowest lvl latency and if you have a weak / old gpu setting it to display would provide lower latency 

I got a decent GPU so i have it set to GPU scaling on both of my monitors

![image](https://github.com/Tungrad/BDO/assets/126987283/62c0cc45-38e9-4d29-9cc3-91d3c642c264)





## Nvidia inspector 
(currently reworking profiles) but base n tweaked should still be fine

Gonna be making a zip file with the different inspector profiles n shit u can fuck around with these i have uploaded

Download [inspector](https://github.com/Orbmu2k/nvidiaProfileInspector/releases)
This is standard [Base normal profile](https://cdn.discordapp.com/attachments/200251993766363136/1133172575997014068/Base_Profile.nip) that should be fine for everyone and this is my [Tweaked Base](https://cdn.discordapp.com/attachments/200251993766363136/1133172576512917734/slight_tweak.nip) you dont need to make any changes to bdo profile specifically unless you want to go potato mode the general tweaks are set into the base profile, low latency mode and threaded you must experiment yourself with it on or off, low / ultra and see whats best for your system.

If you have your own base profile you prefer, here are 2 of the bdo profiles i switch between [1st BDO Profile](https://cdn.discordapp.com/attachments/200251993766363136/1163455037423485009/BDO1.nip?ex=653fa2f0&is=652d2df0&hm=1b278fa94cb401ca6a1158aac5ec777c4814f70bee2e8cd82b87f57234097abe&) [2nd BDO Profile](https://cdn.discordapp.com/attachments/200251993766363136/1163455037050200184/BDO2.nip?ex=653fa2f0&is=652d2df0&hm=81886a577f5992c81b54c0fdf88801d298f52ef85e77a38e82dca82f1748c031&)

If you playing BDO play around with this setting Off, On, Ultra and see what feels the best.![image](https://github.com/Tungrad/BDO/assets/126987283/f51a5a43-8c12-47fa-950d-20f06d434ce4) 

## Disable  Core Isolation
Search for Core Isolation in windows search 
![image](https://github.com/Tungrad/BDO/assets/126987283/f8326b29-2912-4469-8786-1c66ff1168e3)

Disable it 
![image](https://github.com/Tungrad/BDO/assets/126987283/672b99ed-e2b7-440f-9e61-860650f3f7f7)


# Game Mode

For some games Having this Off improves FPS and performance like in cs go this was the case for me while in bdo the performance was the same so you should test this on your own 

If you wanna be lazy and cba testing just turn this off 

![image](https://github.com/Tungrad/BDO/assets/126987283/fc5c30ca-9b63-4c15-ae2a-ea4bcbbf56a7)


![image](https://github.com/Tungrad/BDO/assets/126987283/ac4df746-629f-45c9-98a4-40e09621eadc)

# HAGS
you will need to test with your hardware if its worth having this on or off for the games you play most often but general rule of thumb is 
- Balanced Hardware - Off
- Strong CPU, Weak GPU - Off
- Weak CPU, Strong GPU - On

![image](https://github.com/Tungrad/BDO/assets/126987283/d777bff5-3504-4b93-9587-1762edcd2d68)




## Powerplan / unpark cpu / cpu freq 100%
Download [This](https://bitsum.com/parkcontrol/) tool 
once open 
copy my settings and click apply
![image](https://github.com/Tungrad/BDO/assets/126987283/47f57c2c-864e-46de-9f60-46a3ed1dd3cc)

Then install the power plan 
![image](https://github.com/Tungrad/BDO/assets/126987283/f3d50838-fb3c-4159-bda9-819112fd6c67)

Select it at the top and make active once all done click apply again to make sure 
![image](https://github.com/Tungrad/BDO/assets/126987283/27573ed1-0565-4a22-8bcd-b0f10a3ddd69)

then at the top disable this 
![image](https://github.com/Tungrad/BDO/assets/126987283/fdb01a96-63e4-4b95-940e-358ed246b0ec)

click okay and close the application you're done with this 


# Group policy edit cope

If you have windows pro version you can click ``windows key + r`` and type ``gpedit.msc`` like so to open the application

![image](https://github.com/Tungrad/BDO/assets/126987283/c5053516-cc36-4cbb-b71e-cc4d1b4da9a6)

if you are not on a pro version you an use [This](https://github.com/Fleex255/PolicyPlus) to do the same thing basically 

one you have one of the 2 programs open first you are going to go to ``Administative templats`` -> ``Network`` -> ``QoS Packet Scheduler`` on here you will see these 3 options 


open set timer resolution and copy what i have again dont forget to click apply and okay

![image](https://github.com/Tungrad/BDO/assets/126987283/f62ec2c2-e8c8-47ef-a2cd-34ff0b27427e)



## MSI AFTERBURNER
Download [msi afterburner](https://download.msi.com/uti_exe/vga/MSIAfterburnerSetup.zip?__token__=exp=1686574187~acl=/*~hmac=76ef0d51e24860e0101c2c76cba86e3ffab24219ab8a6fbd4bedd5ba98c73163)

enable the fan curve and adjust it to your preference 
![image](https://github.com/Tungrad/BDO/assets/126987283/bb02743b-209f-4c5b-83a9-6346b2c01d5e)

for the BDO gamers my performance has improved quite a bit from overclocking my memoryclock a bit so play around with adding a bit more to the mem clock and see if you see positive results 



## W32 Priority Seperation

open regedit and  go to this reg directory at the top - ``Computer\HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Control\PriorityControl`` if you would like to read up on this here is the original source post [guide/post](https://forums.blurbusters.com/viewtopic.php?t=8535)

change the value to the ranges listed below, you do not need to restart for this to take effect, so for example defualt value is 2 change it to 26 apply it and play your games / stream whichever you do with your pc and see which feels best. 

The 2 best performing ones for me are `` 16 `` or `` 26 `` just to give you an idea.



```
2A Hex = Short, Fixed , High foreground boost.
29 Hex = Short, Fixed , Medium foreground boost.
28 Hex = Short, Fixed , No foreground boost.

26 Hex = Short, Variable , High foreground boost.
25 Hex = Short, Variable , Medium foreground boost.
24 Hex = Short, Variable , No foreground boost.

1A Hex = Long, Fixed, High foreground boost.
19 Hex = Long, Fixed, Medium foreground boost.
18 Hex = Long, Fixed, No foreground boost.
16 Hex = Long, Variable, High foreground boost.
15 Hex = Long, Variable, Medium foreground boost.
14 Hex = Long, Variable, No foreground boost.``` 
```


![image](https://github.com/Tungrad/BDO/assets/126987283/b45224dd-ef22-4135-bd54-077818ff2477)


# Autoruns

Download autoruns [here](https://learn.microsoft.com/en-us/sysinternals/downloads/autoruns)
Open it as admin and wait for everything to load on the bottom left will say ready once its done.

I typically Search in the top for edge and disable everything as i do not use it for example 

![image](https://github.com/Tungrad/BDO/assets/126987283/3e1442ff-5e5d-495e-a071-f91fdb9066e2)


if you're not familiar with services and tasks I wouldnt disable more than edge unless you actually use it then skip this ofc


# Disable GameBar Presence Writer
follow this [short](https://youtube.com/shorts/vaRdiUOZklA?si=zf8ScD1fSstcyVAL)

if hes yapping too fast follow [this](https://www.youtube.com/watch?v=103jcfT9dmc) instead




# Set high performance windows setting

in the graphics tab in windows select both launcher and bin64 client and set both to High Performance like in the image shownm, you should be able to figure it out where this is if you dont know exactly by looking at the image below im lazy.

![image](https://github.com/Tungrad/BDO/assets/126987283/f4874ad6-c803-43c6-a3c3-79ab87964258)



# Disable CFG BDO



im too lazy to type follow vid




https://github.com/Tungrad/BDO/assets/126987283/a4ba0270-5ce4-4137-bd53-bb5476c4baaf



# Can help fix stutters give it a shot

https://www.youtube.com/watch?v=CAxuGjdahd0&t=157s

link for file dl if you want find it [here](https://web.archive.org/web/20220927205631/https://wj32.org/wp/software/empty-standby-list/)

# Keker pc high ram usage use this 

https://www.sordum.org/9197/reduce-memory-v1-6/

settings i use 

![image](https://github.com/Tungrad/BDO/assets/126987283/e2d0aacb-53c0-4282-a3ad-1e06bbe6c5fa)



# EXTRAAAAAA COPE 


Now call me crazy but this may fix stuttering issues or general BDO issues, if you have DONE everything and still experiencing issues then Go into BDO and click the Reset ALL button this will reset eveything so you will need to setup your UI and BDO settings all over again i guess this would be a last resort but this has made my own bdo more stable and smoother somehow idk dont ask me why. **YOUR MILEAGE MAY VARY** 


# Regedit tweaks
this is the reg file i always apply on my windows up to you if you want to also you can open the file and check it yourself and only apply certain ones up to you


Download it [here](https://www.dropbox.com/scl/fi/wranqdshjct7phn4ib9oh/XDDD.reg?rlkey=fb4munkn22jihtasfat3i8f6z&st=hcp4h5u2&dl=0)

You can also run this one also if you so wish [reg](https://www.dropbox.com/scl/fi/inufb4tsw4co4lmmp3j5a/HOHOHO.reg?rlkey=nwxtbpvi47rha0lri1v0ha8ne&st=ocix4uuw&dl=0)


### CTT Tool
I would recommend this for most people and be done, there are some other windows debloat tools but idk i just have my own script to uninstall the bs 
Run powershell as admin and paste the command below, Click Y to install chocolatey and then a windows will appear 

 ```powershell
 iwr -useb https://christitus.com/win | iex
 ```
 Head over to the Tweaks tab and these are what i have ticked feel free to copy. Click run tweaks when done selecting
 ![image](https://github.com/Tungrad/BDO/assets/126987283/7dad788d-55a4-4a2a-a306-f1408291d9d3)~

and in the update tab i select the middle option
![image](https://github.com/Tungrad/BDO/assets/126987283/b310efc5-997b-4c9c-a306-be055d2d760a)




# BDO setup
setting up a bat file for affinities on BDO

How to setup bat file and pin it to taskbar, right click your desktop -``new`` - ``text document``-
![image](https://github.com/Tungrad/BDO/assets/126987283/86f16f60-b2e2-47c3-86a4-bf34fa71d844)

Rename the file to BDO.bat then right click and edit it in the file put in this  ![image](https://github.com/Tungrad/BDO/assets/126987283/696040e4-5e48-42a3-bd0b-e54379ca6cb3)

```powershell
 cd /d "C:\Pearlabyss\BlackDesert"
 Start /affinity Yournumber BlackDesertLauncher.exe
 ```

Change the path on the first line to you bdo install if its different to mine, you will then need to go to the [canadian](https://docs.google.com/document/d/1cyLaDiPL_B6nOZw_qPE_wOGuoeRT-qddTjevTFoFBkg/edit#heading=h.v9tozbpj4fx) mf guide, go to the CPU performance tab in his guide and get the number prefix for the Yournumber that you will need to edit in the bat file you just made.

I have 5554 in mine just for example

If you a new bozo follow the entire guide if not then you then only focus on the CPU performance section. overall it's a good guide.

Once you have the number needed for your CPU in the bat file done cut and paste the bat file into your BDO install directory mine is this “C:\Pearlabyss\BlackDesert”
Once you have pasted it right click it ``properties`` - ``Advanced`` - ``run as admin``once done right click the batfile once again and create shortcut then once you have done that move the shortcut to your desktop right click it and then click properties 
Then put this “cmd.exe /C” without the quote marks into the target tab
![image](https://github.com/Tungrad/BDO/assets/126987283/19621c10-2622-4d15-8780-a0343a8b0b13)

Click apply then you will notice the icon off the file looks different now, you can have some fun and change the icon of it to make it cooler. also right click properties of the bat file advanced and tick run as admin, you should then be able to pin the file to your taskbar now and open your game.
keep in mind if you wanna set your own icon to make it cooler make sure the image dimensions are 64x64 pixels and ico format


I like to put a max FPS cap on bdo to prevent hitting 6k fps in loading screens copy if you so wish also test different options under low latency mode for your setup
![image](https://github.com/Tungrad/BDO/assets/126987283/c8ccee59-e485-4df8-b212-d02a067cac42)

As always test before and after when making tweaks to see any performance gain or if it has a negative impact.


# Msi Tool
Download the [MSI](http://www.mediafire.com/file/ewpy1p0rr132thk/MSI_util_v3.zip/file) Tool open it as admin , find your gpu and if your gpu is not already ticked tick it, if its unticked and does not have a negative irq value just skip this.

![image](https://github.com/Tungrad/BDO/assets/126987283/e126c0fe-a6de-4ac4-b3d4-391aa0071d8a)

# Chrome

if you use chrome or any other chromium based browser disable this

![image](https://github.com/Tungrad/BDO/assets/126987283/33a0ad6c-e15d-4c1c-a6ca-fef12afed43e)

if you're on fixfox or w/e else is there just disable  hardware acceleration

# Discord
Disable hardware acceleration in discord also 

![image](https://github.com/Tungrad/BDO/assets/126987283/3b4b89d8-557d-4763-a5d1-e85df20077d1)


# Scan for corrupted files DISM n SFC 

Open CMD as admin and run the following the commands, wait for each command to finish before pasting the next

 ```bat
   DISM /Online /Cleanup-Image /CheckHealth
```
 ```bat
   DISM /Online /Cleanup-Image /ScanHealth
```
 ```bat
   DISM /Online /Cleanup-Image /RestoreHealth
```
 ```bat
   sfc /scannow
```

restart your pc once done with everything. 


# Getting ads on twitch ? stop being a keker buy nitro or use this 
https://github.com/pixeltris/TwitchAdSolutions


#  Ocing
To get a bit more performance from your system you can look into overclocking, do it at your own risk tho

### AMD
Look into PBO if you're on the AMD platform general PBO guide [here](https://www.youtube.com/watch?v=dfkrp25dpQ0&t=20s)

### Intel
if you're on intel you can look into this [guide](https://www.youtube.com/watch?v=6nIIG7QYcKE)

## DRR4/5 
OCing To get a bit more performance from your system you can look into overclocking, do it at your own risk tho
for the general person i would just totally skip this and just make sure **XMP / DOCP/ EXPO is enable in your BIOS!**

### DDR5
if you have ddr5 memory i would follow this [guide](https://www.youtube.com/watch?v=dlYxmRcdLVw) generally these speeds and timing will work on most hynix ddr5 kits and probably samsung also 

### DDR4
If you are on DDR4 its requires a bit more effort here is an extensive [Guide](https://github.com/integralfx/MemTestHelper/blob/oc-guide/DDR4%20OC%20Guide.md)

but yh for the avg person i would skip this personally

## More in depth guides
if you really really really want to try optimise your system further you can look into these guides
[Basic guide](https://github.com/luke-beep/guide-to-optimizing-windows/tree/main) [Advanced Guide](https://github.com/amitxv/PC-Tuning/tree/main)

[1st video](https://www.youtube.com/watch?v=WGDRL87tg5s) [2nd video](https://youtu.be/sbXzM60ad8I?t=12)


# END

Hopefully this guide was helpful and improved your performance 

![image](https://github.com/Tungrad/BDO/assets/126987283/60325967-e5aa-4f01-9f09-8132a3c4c119)


