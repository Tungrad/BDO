# General windows / BDO setup
General PC setup and tweaks for the avg BDO gamer, along with BDO setup i personally do, will cover a basic general setup and will go more indeth down the rabbit hole of trying to optismise your PC. 

Taken info from many resources and put them together in this guide for the avg bdo gamer / casual trying to improve their experience.

# Choosing your OS!
Win10 vs Win11
Pick whichever OS you like better if you're on reletivly new CPU i would say go win11.

General [guide](https://youtube.com/shorts/VfOAjO3BfRc?feature=share) on creating a windows boot usb 

If you go down the windows 11 path would say try out [tiny11](https://youtu.be/qiF30VGfGhA?t=172) cuts out most of the reinstalled apps which you will not have to remove later on your own (edge is completely removed in tiny11) 

Github link for the [tiny11 builder](https://github.com/ntdevlabs/tiny11builder)

## Pre install
If you're going to install a fresh OS i would reccomend to predownload your basic needed drivers (chipset,Lan,GPU) and put them on a folder names "Drivers" for example on a usb or 2nd drive. I would suggest going onto this site - https://ninite.com/ 
and create a installer of the programs you use, there are tools  later in this guide that have a similar feature but i like to create on of these now incase just kind of a failsafe.
if you go down the tiny11 path you will not have a browser installed and if you dont know how to use winget i dont skip predownloading drivers and at least download the installer of browser of your choice.

## Windows installation 
I like to unplug my ethernet cable when installing windows if you're on wifi and not using a cable you will not need to worry about this. 

Once in windows install your drivers that you pre-download and restart when promted to. After this i plug in my ethernet cable back in of on wifi connect to your network

Once in windows Install the Ninite file or atleast your browser of choice and download and run [O&O ShutUp](https://www.oo-software.com/en/shutup10) and apply [recommended](https://imgur.com/a/9mhHbh8) settings accept the restore point then go ahead and close out of the program and restart your pc.

# Windows post install - bits n pieces stolen from [amint guide](https://github.com/amitxv/PC-Tuning/blob/main/docs/post-install.md)


## Install Visual C++ Redistributable Runtimes

Download and install the [Visual C++ redistributable runtimes](https://github.com/abbodi1406/vcredist).

## Install .NET 4.8 Runtimes

Download and install the [.NET 4.8 runtimes](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net48). NET 4.8 already ships with Windows 10 1909+.

## Install DirectX Runtimes

Download and install the [DirectX runtimes](https://www.microsoft.com/en-gb/download/details.aspx?id=8109).


## Configure Memory Management Settings (Windows 8+)

- Open PowerShell and enter the command below

    ```powershell
    Get-MMAgent
    ```

- If anything is set to True, use the command below as an example to disable a given setting, paste them individually some might return an error

    ```powershell
    Disable-MMAgent -MemoryCompression
    Disable-MMAgent -ApplicationLaunchPrefetching
    Disable-MMAgent -ApplicationPreLaunch
    Disable-MMAgent -OperationAPI
    Disable-MMAgent -PageCombining
    ```


## Configure Audio Settings
- Press Win + R to open the Run Command dialog box.
 ```powershell
 mmsys.cpl
 ```
The sound contro window should pop up now, Follow [This](https://imgur.com/a/IpVCXBG) to configure your sound settings 

## Device manager Settings
Find your mouse right click properties and uncheck both in power management [following](https://imgur.com/a/9n9VWPw)

Do the same for your [Network adapters](https://imgur.com/a/TE8LmxV)
while in the network adapter settings go to the advanced tab and set the following to disabled (Energy efficient ethernet, Green Ethernet,power saving mode)

## Nvidia inspector 
Download [inspector](https://www.guru3d.com/files-details/nvidia-inspector-download.html)
This is my [Base profile](https://cdn.discordapp.com/attachments/610614436939694141/1116940618204184637/Overall_profile.nip)
and these are 3 BDO profile you can swap between [BDOV1](https://cdn.discordapp.com/attachments/610614436939694141/1116940617042362378/Black_DesertV1.nip). [BDOV2](https://cdn.discordapp.com/attachments/610614436939694141/1116940617428250705/Black_DesertV2.nip). [BDOV3](https://cdn.discordapp.com/attachments/610614436939694141/1116940617772179456/Black_DesertV3.nip).

# Which optimise tool to use.
There are about 3 Tools that i've seen and would recommend to try out. 

Avoid using all in conjuction with each otherand turning on all settings more likely to cause issues than improve performance if you do this.
