<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Installing Windows without a PC
> [!Warning]
> THIS PAGE IS NOT YET FINISHED! DO NOT USE IT!
> Seriously, do not use it until this warning is removed from this page.

### Prerequisites
- A rooted POCO X3 Pro

- [Vayu WinInstaller]

- [Windows on ARM image](https://worproject.com/esd)

- [Drivers](https://github.com/n00b69/woa-vayu/releases/tag/Drivers)

- [Modified TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)

- [UEFI image](https://github.com/n00b69/woa-vayu/releases/tag/UEFI)

- [WOA Helper app](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA)

### Notes
> [!WARNING]  
> All your data will be erased! Back up now if needed.
> 
> DO NOT REBOOT YOUR PHONE if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/woahelperchat).
> 
> Do not run all commands at once, execute them in order!

### Flash the modified TWRP
> While in fastboot mode, replace `path\to\moddedtwrp.img` with the actual path of the image.
>
> If you don't have a PC, which is probable since you're following this guide instead of the PC method, you can use the **Termux** app on another (rooted) phone to do this.
```cmd
fastboot flash recovery path\to\moddedtwrp.img reboot recovery
```

#### Opening TWRP terminal
- Once booted into TWRP, decrypt data by entering your password if it asks you to.
- Press the **Advanced** button on the bottom right of the screen, then press **Terminal**

### Run the partitioning script
> Replace **$** with the amount of storage you want Windows to have (do not add GB, just write the number)
> 
> If it asks you to run it once again, do so
```cmd
partition $
```

#### Rooting your phone
- If your phone isn't already rooted, you can flash Magisk at this point using rhe instructions in [the root guide](root.md), else continue to the next step.

### Check if Android still starts
- Just restart the phone, and see if Android still works

### Preparing necessary files
- Download the [drivers](https://github.com/n00b69/woa-vayu/releases/tag/Drivers) and rename the zip to **Driver.zip**. Make sure it remains in the `Downloads` folder.
- Download the [Windows image](https://worproject.com/esd) and rename it to **install.esd**. Make sure it remains in the `Downloads` folder.
- Download and install the [WOA Helper app](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA), then open it and grant it root access. Do not do anything else inside the app yet.
- Now reboot to the modified TWRP. Flash it again if it has been replaced by MIUI recovery.

### Flashing WinInstaller
- In TWRP, select **Install** and then locate **WinInstaller.zip** and flash it.
- Wait untill all processes complete and Windows setup appears. (It will take 10 to 15 minutes and eventually reboot 2 or 3 times).
> [!Tip]
> If you wish to skip the Microsoft Account login, press the **I don't have internet** button in the WiFi page, then when prompted, press the **Continue with limited setup** button.

#### Booting to Android
- Run the **Android** shortcut on your desktop (you can also pin it to your start menu / taskbar for ease of access)

#### Booting to Windows
- Press **QUICKBOOT TO WINDOWS** inside the WOA Helper app, or use the newly created toggle in your quick settings panel

## Finished!


























