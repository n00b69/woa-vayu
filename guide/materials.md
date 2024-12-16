<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

# Useful apps and instructions for Windows

## List of supported apps/games
This is by no means a comprehensive list, it simply lists apps/games that have been tested by the community
[The link can be found here](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

You can also find a list of dedicated ARM software [at this link](https://armrepo.ver.lt/)

#### Finished!


## Hide D drive (modem partition)
> [!NOTE]
> This is recommended because this drive should not be modified, while some applications may try to write to it.

#### Automated method
- Download [ModemHide.vbs](https://github.com/Misha803/My-Scripts/releases/tag/ModemHide) onto your polaris 
- Run it
- Approve any UAC dialogs 
- Click `Yes` in the dialog box

#### Manual method
- Open a command prompt window and run ```diskpart```
- Run ```list volume``` to see all available volumes
- Select the disk that has letter D with ```select volume $```, replacing "$" with the volume number
- Remove the letter with ```remove letter d```
- Exit diskpart with ```exit```

##### Finished!


## Disabling USB host mode
> [!Warning]
> Unpowered USB devices will stop working

> [!Important]
> The following steps must be done on your phone in Windows, not on your computer. 

Run [USB Host Mode Control](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control) to enable/disable USB host mode and  confirm that you want to disable/enable USB host mode 

#### Finished!


## Install Microsoft Office / Microsoft 365
- Download this [ISO file](https://mega.nz/file/dnhQ3Q6b#X0o_B9eEPRa_IaPojQ-z1sLdqMgXkEQXqxfm2P0jL0I) to the tablet
- Right-click on the iso file and select Mount to open it in explorer
- Double-click on ```Office Tool Plus.exe``` to start the installation wizard
- Approve any UAC dialogs 
- In the window that appears, click `Yes` to start installation 
- Wait for the installation to complete

#### Finished!


## Activate Windows / Office
Follow the instructions by Massgravel [here](https://github.com/massgravel/Microsoft-Activation-Scripts)

#### Finished!


### Making the keyboard float
> [!WARNING]  
> Make sure these steps are done on the POCO X3 Pro running Windows!

- Open CMD as an admin and run ```reg delete HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Scaling /v MonitorSize```
- Press 'y' then enter
- Reboot your phone

##### Finished!









### Provisioning the modem
> [!WARNING]  
> You will need to do this every time before you boot Windows if you want LTE!

> [!NOTE]
> You don't have to do this if you're using WoA Helper

#### Provisioning the modem mostly automatically (faster/easier method)

#### Prerequisites
- Magisk or TWRP installed
- [Modem provisioning zip](https://github.com/woa-vayu/Port-Windows-11-POCO-X3-Pro/releases/tag/modemprov)

##### Flash the modem provisioning zip

> This is very self explanatory, open Magisk (or TWRP), install zip that does the hard work for you

- Open Magisk (or boot TWRP)
- Go to the Modules section ("Install" button in TWRP)
- Flash the zip
- Boot into Windows

##### Finished!








#### Provisioning the modem manually (longer/harder method)

#### Prerequisites

- [Modified TWRP](../../../releases/Recoveries)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

##### Flash and boot modded recovery

> This is self explanatory, it flashes the recovery then reboots into the recovery

```fastboot flash recovery path\to\twrp.img reboot recovery```

##### Mounting partitions

> Also self explanatory, this will mount the windows partitions

- Go to the mount menu
- Mount the partition win

##### Start ADB Shell

> Starts a shell on your computer used to communicate with your phone over ADB

```adb shell```

##### Finding the modem folder

> Take note of the random data in that folder name (after qcremotefs8150)

> This looks for the Qualcomm remotefs driver folder

```ls /win/Windows/System32/DriverStore/FileRepository/ | grep qcremotefs8150```

##### Dump modem data

> Just like before, replace the random data with the one that you noted down before

> Make sure you do BOTH commands

> This dumps your modem data into the remote fs folder, ultimately fixing the modem

```dd if=/dev/block/by-name/modemst1 of=/win/Windows/System32/DriverStore/FileRepository/qcremotefs8150_[insert random data here]/bootmodem_fs1```

```dd if=/dev/block/by-name/modemst2 of=/win/Windows/System32/DriverStore/FileRepository/qcremotefs8150_[insert random data here]/bootmodem_fs2```

##### Finished!









### Disabling USB Host mode

> [!WARNING]
>  Any non powered hub will STOP working!
>
> Make sure these steps are done on the POCO X3 Pro running Windows!

> This edits the registry key to tell the USB Controller not to put the device into host mode

- In the command prompt put ```reg add "HKLM\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters" /v RoleSwitchMode /t REG_DWORD /d 3```
- Reboot your phone

##### Finished!




















