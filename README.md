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
if you want to try optimise the most performance possible you can look into pre making a debloat driver that you will install later using this [Guide](https://github.com/luke-beep/guide-to-optimizing-windows/blob/main/docs/DRIVER-TWEAKS.md#debloat-nvidia-drivers). 

## Windows installation 
I like to unplug my ethernet cable when installing windows if you're on wifi and not using a cable you will not need to worry about this. 

Once in windows install your drivers that you pre-download and restart when promted to, after this i plug in my ethernet cable back in or if you are on wifi connect to your network

Once in windows Install the Ninite file or atleast your browser of choice and download and run [O&O ShutUp](https://www.oo-software.com/en/shutup10) and apply [recommended](https://imgur.com/a/9mhHbh8) settings accept the restore point then go ahead and close out of the program and restart your pc.

# Windows post install - bits n pieces stolen from [amitxv guide](https://github.com/amitxv/PC-Tuning/blob/main/docs/post-install.md)

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

- Open CMD and enter the command below

    - Remove OneDrive if you will not be using it.

        ```bat
        for %a in ("SysWOW64" "System32") do (if exist "%windir%\%~a\OneDriveSetup.exe" ("%windir%\%~a\OneDriveSetup.exe" /uninstall))
        ```
- Windows 10+ Only:

    - Windows 10:

        - Uninstall bloatware in ``Apps -> Apps and Features`` by pressing ``Win+I`` uninstall programs you will not be using

        - In the ``Optional features`` section, uninstall everything apart from ``Microsoft Paint``, ``Notepad`` and ``WordPad`` if applicable (these do not exist in earlier Windows 10 versions)

    - Windows 11:

        - Uninstall bloatware in ``Apps -> Installed apps`` by pressing ``Win+I`` uninstall programs you will not be using

        - In the ``Apps -> Optional features`` section, uninstall everything apart from ``WMIC``, ``Windows PowerShell ISE``, ``Notepad (system)`` and ``WordPad``

- Open your start menu with windows key and unpin and uninstall iteams left over in here you will typically see tiktok, clip chimp etx if you didnt go down the tiny11 route.
-  Restart your PC once to apply the changes above


## Configure Memory Management Settings (Windows 8+)

- Open PowerShell as admin and enter the command below

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
The sound control window should pop up now, Follow [This](https://imgur.com/a/IpVCXBG) to configure your sound settings 

## Device manager Settings
Find your mouse right click properties and uncheck both in power management [following](https://imgur.com/a/9n9VWPw)

Do the same for your [Network adapters](https://imgur.com/a/TE8LmxV)
while in the network adapter settings go to the advanced tab and set the following to disabled (Energy efficient ethernet, Green Ethernet,power saving mode)

## Nvidia inspector 
Download [inspector](https://www.guru3d.com/files-details/nvidia-inspector-download.html)
This is my [Base profile](https://cdn.discordapp.com/attachments/610614436939694141/1116940618204184637/Overall_profile.nip)
and these are 3 BDO profile you can swap between [BDOV1](https://cdn.discordapp.com/attachments/610614436939694141/1116940617042362378/Black_DesertV1.nip). [BDOV2](https://cdn.discordapp.com/attachments/610614436939694141/1116940617428250705/Black_DesertV2.nip). [BDOV3](https://cdn.discordapp.com/attachments/610614436939694141/1116940617772179456/Black_DesertV3.nip).

If you playing BDO play around with this setting Off, On, Ultra with the other bdo profiles i linked before and see what feels the best.![image](https://github.com/Tungrad/BDO/assets/126987283/f51a5a43-8c12-47fa-950d-20f06d434ce4) 

## Disable  coreisolation
Search for Coreisolation in windows search 
![image](https://github.com/Tungrad/BDO/assets/126987283/f8326b29-2912-4469-8786-1c66ff1168e3)

Disable it 
![image](https://github.com/Tungrad/BDO/assets/126987283/672b99ed-e2b7-440f-9e61-860650f3f7f7)

## Powerplan 

I typically like to you the Bitsum powerplan 
[Power plan.zip](https://github.com/Tungrad/BDO/files/11712663/Power.plan.zip)

Unzip folder to your C drive, the path should look like this C:\Plan run the bat file as admin then open your powerplan settings it was added successfully  



# Which optimise tool to use.
There are about 3 Tools that i've seen and would recommend to try out. 

Avoid using all 3 in conjuction with each otherand turning on all settings more likely to cause issues than improve performance if you do this.
For the general person I would say go the CTT route and be done, if you're more into minx maxing performance and having a older system I would say to use CTT with hone or just use optimizer on its own.

### CTT Tool
I would recommend this for most people but if you want more GAMER oriented tool only use the the security section of the tool as shown below. 
Run powershell as admin and paste the command below, Click Y to install chocolatey and then a windows will appear 

 ```powershell
 iwr -useb https://christitus.com/win | iex
 ```
 Head over to the Tweaks tab and these are what i have ticked feel free to copy. Click run tweaks when done selecting
![image](https://github.com/Tungrad/BDO/assets/126987283/559ac5e8-7036-46ca-be37-0c248444148b)

Then head over to the updates tab and select the middle option "security"
![image](https://github.com/Tungrad/BDO/assets/126987283/235cf578-3d91-4ed2-a4af-d0e122380b0b)


### Optimizer
[Optimizer](https://github.com/hellzerg/optimizer) is solid tool if you feeling to go a bit more harder into the "optimisation" for your PC this is a widely used tool
These are the settings I would run for the program.

General tab settings
![image](https://github.com/Tungrad/BDO/assets/126987283/4b807195-9d84-4c2a-9a2d-2f73f5318b79)

Windows 10/11 settings
![image](https://github.com/Tungrad/BDO/assets/126987283/f6803075-ff43-4bd1-8593-06dfa110420e)


### Hone cntrl

[Hone](https://github.com/auraside/HoneCtrl) Another tool that's pretty popular amoung the MC crowd and valorant 
For Hone i would run these general safe settings which can be seen [here](https://github.com/luke-beep/guide-to-optimizing-windows/blob/main/docs/HONE.md)

If you want to go full ham with with hone settings you can copy everythig this guy has turn on in this [video](https://youtu.be/hl2SIMnWW5A?t=69) generally i dont think you should be but its up to you what you want to do

# BDO setup
setting up a batfile for affinities on BDO

How to setup bat file and pin it to taskbar, right click your desktop -``new`` - ``text document``-
![image](https://github.com/Tungrad/BDO/assets/126987283/86f16f60-b2e2-47c3-86a4-bf34fa71d844)

Rename the file to BDO.bat then right click and edit it in the file put in this  ![image](https://github.com/Tungrad/BDO/assets/126987283/696040e4-5e48-42a3-bd0b-e54379ca6cb3)

```powershell
 cd /d "C:\Pearlabyss\BlackDesert"
 Start /affinity Yournumber BlackDesertLauncher.exe
 ```

Change the path on the first line to you bdo install if its different to mine, you will then need to go to the [canadian](https://docs.google.com/document/d/1cyLaDiPL_B6nOZw_qPE_wOGuoeRT-qddTjevTFoFBkg/edit#heading=h.v9tozbpj4fx) mf guide, go to the CPU performance tab in his guide and get the number prefix for the Yournumber that you will need to edit in the batfile you just made.

If you a new bozo follow the entire guide if not then you then only focus on the CPU performance section. overall it's a good guide.

Once you have the number needed for your CPU in the bat file done cut and paste the bat file into your BDO install directory mine is this “C:\Pearlabyss\BlackDesert”
Once you have pasted it right click it ``properties`` - ``Advanced`` - ``run as admin``once done right click the batfile once again and create shortcut then once you have done that move the shortcut to your desktop right click it and then click properties 
Then put this “cmd.exe /C” without the quote marks into the target tab
![image](https://github.com/Tungrad/BDO/assets/126987283/19621c10-2622-4d15-8780-a0343a8b0b13)

Click apply then you will notice the icon off the file looks different now, you can have some fun and change the icon of it to make it cooler. also right click properties of the bat file advanced and tick run as admin, you should then be able to pin the file to your taskbar now and open your game.

You can use this [regfile](https://cdn.discordapp.com/attachments/827179224213094421/1105669846693331016/eac.reg) to put EAC to run on low prio your choice if you want to copy this step.

I like to put a max FPS cap on bdo to prevent hitting 6k fps in loading screens copy if you so wish
![image](https://github.com/Tungrad/BDO/assets/126987283/c8ccee59-e485-4df8-b212-d02a067cac42)

## Msi Tool
Download the [MSI](http://www.mediafire.com/file/ewpy1p0rr132thk/MSI_util_v3.zip/file) Tool open it as admin , find your gpu and if your gpu is not already ticked tick it, if its unticked and does not have a negative irq value just skip this.

![image](https://github.com/Tungrad/BDO/assets/126987283/e126c0fe-a6de-4ac4-b3d4-391aa0071d8a)

## Chrome

if you use chrome or any other chromium based browser disable this

![image](https://github.com/Tungrad/BDO/assets/126987283/33a0ad6c-e15d-4c1c-a6ca-fef12afed43e)

if you're on fixfox or w/e else is there just disable  hardware acceleration

##  Ocing
To get a bit more performance from your system you can look into overclocking, do it at your own risk tho

### AMD
Look into PBO if you're on the AMD platform general PBO guide [here](https://www.youtube.com/watch?v=dfkrp25dpQ0&t=20s)

### Intel
if you're on intel you can look into this [guide](https://www.youtube.com/watch?v=6nIIG7QYcKE)#

## DRR4/5 OCing To get a bit more performance from your system you can look into overclocking, do it at your own risk tho
for the general person i would just totally skip this and just make sure **XMP / DOCP/ EXPO is enable in your BIOS!*

### DDR5
if you have ddr5 memory i would follow this [guide](https://www.youtube.com/watch?v=dlYxmRcdLVw) generally these speeds and timing will work on most hynix ddr5 kits and probably samsung also 

### DDR4
If you are on DDR4 its requires a bit more effort here is an extensive [Guide](https://github.com/integralfx/MemTestHelper/blob/oc-guide/DDR4%20OC%20Guide.md)

but yh for the avg person i would skip this personally

## GETTING THAT 1 EXTRA FPS
if you really really really want to try optimise your system further you can look into these two videos

[1st video](https://www.youtube.com/watch?v=WGDRL87tg5s) [2nd video](https://youtu.be/sbXzM60ad8I?t=12)
