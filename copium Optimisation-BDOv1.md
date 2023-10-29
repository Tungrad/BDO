
# Updating in bits n pieces its more so 99% done but im lazy af

# General windows / BDO setup -  

General PC setup and tweaks for the avg BDO gamer, along with BDO setup i personally do, will cover a basic general setup and will go more in depth down the rabbit hole of trying to optimise  your PC. 

Taken info from many resources and put them together in this guide for the avg bdo gamer / casual trying to improve their experience.

this is about 95% of what i do there are some other tweaks but its way to trihard for the avg person and i cba explaining how to do them if you wanna know what else i do ask me in discord ig

# Choosing your OS!
Win10 vs Win11
Pick whichever OS you like better if you're on relatively new CPU i would say go win11 just slighty better performance on win11 when asking people who have new cpus, but they are basically more or less the same performance so use w/e you like.

General [guide](https://youtube.com/shorts/VfOAjO3BfRc?feature=share) on creating a windows boot usb 

If you go down the windows 11 path would say try out [tiny11](https://youtu.be/qiF30VGfGhA?t=172) cuts out most of the reinstalled apps which you will not have to remove later on your own (edge is completely removed in tiny11) 

Github link for the [tiny11 builder](https://github.com/ntdevlabs/tiny11builder)

## Pre install
If you're going to install a fresh OS i would recommend to pre-download your basic needed drivers (chipset,Lan,GPU) and put them on a folder names "Drivers" for example on a usb or 2nd drive. I would suggest going onto this site - https://ninite.com/ 
and create a installer of the programs you use, there are tools  later in this guide that have a similar feature but i like to create on of these now incase just kind of a failsafe.
if you go down the tiny11 path you will not have a browser installed and if you dont know how to use winget, dont skip predownloading drivers and at least download the installer of browser of your choice.
if you want to try optimise the most performance possible you can look into pre making a debloat driver that you will install later using this [Guide](https://github.com/luke-beep/guide-to-optimizing-windows/blob/main/docs/DRIVER-TWEAKS.md#debloat-nvidia-drivers). 

## Windows installation 
I like to unplug my ethernet cable when installing windows if you're on wifi and not using a cable you will not need to worry about this. 

Once in windows install your drivers that you pre-download and restart when promted to, after this i plug in my ethernet cable back in or if you are on wifi connect to your network

After this run/install the Ninite file or atleast your browser of choice and download and run [O&O ShutUp](https://www.oo-software.com/en/shutup10) and apply [recommended](https://imgur.com/a/9mhHbh8) settings accept the restore point then go ahead and close out of the program and restart your pc.

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

- Windows 10+ Only:

    - Windows 10:

        - Uninstall bloatware in ``Apps -> Apps and Features`` by pressing ``Win+I`` uninstall programs you will not be using

        - In the ``Optional features`` section, uninstall everything apart from ``Microsoft Paint``, ``Notepad`` and ``WordPad`` if applicable (these do not exist in earlier Windows 10 versions)

    - Windows 11:

        - Uninstall bloatware in ``Apps -> Installed apps`` by pressing ``Win+I`` uninstall programs you will not be using

        - In the ``Apps -> Optional features`` section, uninstall everything apart from ``WMIC``, ``Windows PowerShell ISE``, ``Notepad (system)`` and ``WordPad``
     
- Automated     
If you prefer to have this done automatically then you can copy and paste the following into PowerShell it will pretty much remove everyting apart from calculator, notepad and terminal so keep that in mind if you use any of the default windows apps, you can go into the store and download them again.

 ```powershell
dism /online /norestart /disable-feature /featurename:Printing-PrintToPDFServices-Features
dism /online /norestart /disable-feature /featurename:Printing-XPSServices-Features
dism /online /norestart /disable-feature /featurename:WorkFolders-Client
dism /online /norestart /disable-feature /featurename:Printing-Foundation-Features
dism /online /norestart /disable-feature /featurename:Printing-Foundation-InternetPrinting-Client
dism /online /norestart /disable-feature /featurename:MSRDC-Infrastructure
dism /online /norestart /disable-feature /featurename:SmbDirect
dism /online /norestart /disable-feature /featurename:MediaPlayback
dism /online /norestart /disable-feature /featurename:WCF-TCP-PortSharing45
dism /online /norestart /disable-feature /featurename:WCF-Services45
dism /online /norestart /disable-feature /featurename:WindowsMediaPlayer
dism /online /norestart /disable-feature /FeatureName:MicrosoftWindowsPowerShellV2Root

 ```

 ```powershell
dism /online /norestart /Remove-Capability /CapabilityName:App.StepsRecorder~~~~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:App.Support.QuickAssist~~~~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:Browser.InternetExplorer~~~~0.0.11.0
dism /online /norestart /Remove-Capability /CapabilityName:Hello.Face.20134~~~~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:Language.Handwriting~~~en-US~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:Language.Speech~~~en-US~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:Language.TextToSpeech~~~en-US~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:MathRecognizer~~~~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:Media.WindowsMediaPlayer~~~~0.0.12.0
dism /online /norestart /Remove-Capability /CapabilityName:Microsoft.Windows.WordPad~~~~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:OneCoreUAP.OneSync~~~~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:OpenSSH.Client~~~~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:Print.Management.Console~~~~0.0.1.0
dism /online /norestart /Remove-Capability /CapabilityName:Microsoft.Wallpapers.Extended~~~~0.0.1.0

 ```

 ```powershell
powershell "Get-AppXPackage | Where NonRemovable -Match false | Where IsFramework -Match false | Where Name -NotMatch '.*Windows(Store|Notepad|Calculator|Terminal|Paint)|NVIDIAControlPanel.*' | Remove-AppXPackage"
powershell "sleep 5"
powershell "Get-AppXProvisionedPackage -online | Where DisplayName -NotMatch '.*Windows(Store|Notepad|Calculator|Terminal)|NVIDIAControlPanel.*' | ForEach-Object { try { Write-Host $_.DisplayName ; Remove-AppxProvisionedPackage -Online -PackageName $_.PackageName  } catch { Write-Host $_ } }"


 ```

- Open your start menu with windows key and unpin and uninstall items left over in here you will typically see tiktok, clip chimp etx if you didnt go down the tiny11 route.
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
- Energy-Efficient Ethernet - Disabled
- Gigabit Lite - Disabled
- Green Ethernet - Disabled
- Interrupt Moderation - Disabled
- Jumbo Frame - Disabled
- Ns Offload - Disabled
- Power Saving Mode - Disabled
- Shutdown Wake-On-Lan - Disabled
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

## Powerplan 

I typically like to suggest the Bitsum powerplan, if you have your own powerplan or like to edit the pre-existing powerplans like balanced to your liking then do so
[Power plan.zip](https://github.com/Tungrad/BDO/files/11712663/Power.plan.zip)

Unzip folder to your C drive, the path should look like this C:\Plan run the bat file as admin to check it was added successfully open your powerplan settings it should look like this 

![image](https://github.com/Tungrad/BDO/assets/126987283/5d47a12e-2f8c-472c-9c1e-6176ddcb1508)

Or you can try out this alternative one
[2nd Power plan](https://github.com/Tungrad/BDO/blob/main/Power.bat) click downloand on the top right and run it as admin and it should automatically add and set it to active plan


# Group policy edit cope

If you have windows pro version you can click ``windows key + r`` and type ``gpedit.msc`` like so to open the application

![image](https://github.com/Tungrad/BDO/assets/126987283/c5053516-cc36-4cbb-b71e-cc4d1b4da9a6)

if you are not on a pro version you an use [This](https://github.com/Fleex255/PolicyPlus) to do the same thing basically 

one you have one of the 2 programs open first you are going to go to ``Administative templats`` -> ``Network`` -> ``QoS Packet Scheduler`` on here you will see these 3 options 


open set timer resolution and copy what i have again dont forget to click apply and okay

![image](https://github.com/Tungrad/BDO/assets/126987283/f62ec2c2-e8c8-47ef-a2cd-34ff0b27427e)


Now we move over to more extra **COPE** 

Now we go back to the program you was just using, now head to  ``Windows settings`` and then click on ``Policy-based QoS`` - right click and create new policy

![image](https://github.com/Tungrad/BDO/assets/126987283/2bf4a9ea-e158-4c1e-91ae-118cae936fea)

now copy the DSCP value you can name it what ever you want i just name it BlackDesert and then click next
![image](https://github.com/Tungrad/BDO/assets/126987283/7a4244f7-780c-47a6-91c1-4aabb394826e)

copy what i have here 
![image](https://github.com/Tungrad/BDO/assets/126987283/f64b9393-5a2c-4ecd-9c8d-2e885e623546)

Click Next on the next page till you see this page and copy what i have in the first drop down bax TCP and UDP

![image](https://github.com/Tungrad/BDO/assets/126987283/f290621a-bd1d-4164-b1af-f770d83fb65b)

and then just click finish and you're done with this 


## MSI AFTERBURNER
Download [msi afterburner](https://download.msi.com/uti_exe/vga/MSIAfterburnerSetup.zip?__token__=exp=1686574187~acl=/*~hmac=76ef0d51e24860e0101c2c76cba86e3ffab24219ab8a6fbd4bedd5ba98c73163)

enable the fan curve and adjust it to your preference 
![image](https://github.com/Tungrad/BDO/assets/126987283/bb02743b-209f-4c5b-83a9-6346b2c01d5e)

for the BDO gamers my performance has improved quite a bit from overclocking my memoryclock a bit so play around with adding a bit more to the mem clock and see if you see positive results 



## W32 Priority Seperation

open regedit and  go to this reg directory at the top - ``Computer\HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Control\PriorityControl`` if you would like to read up on this here is the original source post [guide/post](https://forums.blurbusters.com/viewtopic.php?t=8535)

change the value to the ranges listed below, you do not need to restart for this to take effect, so for example defualt value is 2 change it to 26 apply it and play your games / stream whichever you do with your pc and see which feels best. 

The 2 best performing ones for me are `` 16 `` or `` 26 `` just to give you an idea.

In the cope regfile i have it set to 26 which is typically the best most of the time so keep that in mind if u run the regfile if u wanna fuck around with this

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


# Disable CFG BDO



im too lazy to type follow vid




https://github.com/Tungrad/BDO/assets/126987283/a4ba0270-5ce4-4137-bd53-bb5476c4baaf



# Can help fix stutters give it a shot

https://www.youtube.com/watch?v=CAxuGjdahd0&t=157s


# Extra cope

Find the location of the bdo exe typically found in here C:\Pearlabyss\BlackDesert\bin64 , Right click on the exe and click properties and then go to the compatibility tab tick disable full screen opti and run as admin

![image](https://github.com/Tungrad/BDO/assets/126987283/301200b4-7c7f-47c8-9ff8-95b40dc725a2)


then click change high dpi settings and copy shown

![image](https://github.com/Tungrad/BDO/assets/126987283/05a5a16b-6c9f-4478-9ff0-381bd610d586)

Now do this for the bdo launcher that's typically located in C:\Pearlabyss\BlackDesert , Right click on the exe and click properties and then go to the compatibility tab tick disable full screen opti and run as admin

![image](https://github.com/Tungrad/BDO/assets/126987283/100e8f31-98cb-4938-8dac-cfedc6f2c9ab)

then click change high dpi settings and copy shown

![image](https://github.com/Tungrad/BDO/assets/126987283/05a5a16b-6c9f-4478-9ff0-381bd610d586)

# EXTRAAAAAA COPE 


Now call me crazy but this may fix stuttering issues or general BDO issues, if you have DONE everything and still experiencing issues then Go into BDO and click the Reset ALL button this will reset eveything so you will need to setup your UI and BDO settings all over again i guess this would be a last resort but this has made my own bdo more stable and smoother somehow idk dont ask me why. **YOUR MILEAGE MAY VARY** 


# Regedit tweaks
file with some regedit tweaks taken from all the copium guides from the past maybe it helps maybe it doesnt always test before and after.

[General cope tweaks](https://cdn.discordapp.com/attachments/200251993766363136/1166924789986889788/COPEV2.reg?ex=654c4266&is=6539cd66&hm=aab04702a81e89caa866d66fcf8eeadccf13eb515a6500d05587c80bbfa8b764&)

[EAC Regedit](https://cdn.discordapp.com/attachments/200251993766363136/1163453296720220251/eac.reg?ex=653fa151&is=652d2c51&hm=f5bcf61c8119cdeac71da07b5ae69d9dc721b3413b4ffe303dcd978a06dc5e19&)

## Cope Tweak 
may or may not improve your performance as always test it for urself and make restore points
  ```bat
   bcdedit /set disabledynamictick yes
```
if it fucks up your pc or gaming performance use a restore point or disable it with this 
  ```bat
   bcdedit /set disabledynamictick no
```

# Which optimise tool to use.
BOTH CTT and Optimizer are good individually or can be used in conjunction with each other, but in no way necessary they just help automate/ speed run doing certain tweaks manually 

**MAKE SURE TO MAKE A RESTORE POINT BEFORE USING AND CHECKING PERFORMANCE IN GAME TO SEE IF ITS A POSITIVE GAIN OR NEGATIVE**

Avoid using all both in conjunction with each other and turning on all the settings you are more likely to cause more issues than improving performance if you do this.

For the general person I would say go the CTT route and be done, but feel free to try each on its own I would say optmizer is a solid tool to use on its own also, dont forget to test before making any tweak changes

### CTT Tool
I would recommend this for most people and be done, but you can use the next tool with this if you so wish, just keep in mind not to do the same tweak on both programs as its a bit redundant to do so.
Run powershell as admin and paste the command below, Click Y to install chocolatey and then a windows will appear 

 ```powershell
 iwr -useb https://christitus.com/win | iex
 ```
 Head over to the Tweaks tab and these are what i have ticked feel free to copy. Click run tweaks when done selecting
![image](https://github.com/Tungrad/BDO/assets/126987283/559ac5e8-7036-46ca-be37-0c248444148b)

Then head over to the updates tab and select the middle option "security"
![image](https://github.com/Tungrad/BDO/assets/126987283/235cf578-3d91-4ed2-a4af-d0e122380b0b)


### Optimizer
[Optimizer](https://github.com/hellzerg/optimizer) Overall great tool has some more tweaks that may or may not increase your performance so test before and after turning on certain tweaks and make sure to have relevant restore points to do so.

Keep in mind to test before and after enabling performance tweaks, so you can know if they are hindering your performance or not.

General tab settings
![image](https://github.com/Tungrad/BDO/assets/126987283/4b807195-9d84-4c2a-9a2d-2f73f5318b79)

Windows 10/11 settings
![image](https://github.com/Tungrad/BDO/assets/126987283/f6803075-ff43-4bd1-8593-06dfa110420e)


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

If you a new bozo follow the entire guide if not then you then only focus on the CPU performance section. overall it's a good guide.

Once you have the number needed for your CPU in the bat file done cut and paste the bat file into your BDO install directory mine is this “C:\Pearlabyss\BlackDesert”
Once you have pasted it right click it ``properties`` - ``Advanced`` - ``run as admin``once done right click the batfile once again and create shortcut then once you have done that move the shortcut to your desktop right click it and then click properties 
Then put this “cmd.exe /C” without the quote marks into the target tab
![image](https://github.com/Tungrad/BDO/assets/126987283/19621c10-2622-4d15-8780-a0343a8b0b13)

Click apply then you will notice the icon off the file looks different now, you can have some fun and change the icon of it to make it cooler. also right click properties of the bat file advanced and tick run as admin, you should then be able to pin the file to your taskbar now and open your game.

You can use this [regfile](https://cdn.discordapp.com/attachments/827179224213094421/1105669846693331016/eac.reg) to put EAC to run on low prio your choice if you want to copy this step, just be sure to test this if it improves performance or hinders it.

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


