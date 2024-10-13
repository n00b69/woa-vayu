<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Installing Windows without a PC

### Prerequisites
- A rooted POCO X3 Pro

- [Vayu WinInstaller](https://github.com/Kumar-Jy/WinInstaller/releases/tag/Vayu_WinInstaller)

- [Windows on ARM image](https://arkt-7.github.io/woawin/)

- [Modified TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)

- [WOA Helper app](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA)

### Notes
> [!WARNING]  
> All your data will be erased! Back up now if needed.
> 
> DO NOT REBOOT YOUR PHONE if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/woahelperchat).

### Flash the modified TWRP
> While in fastboot mode, replace `path\to\moddedtwrp.img` with the actual path of the image.
>
> If you don't have a PC, you can flash the modified TWRP through any non-stock recovery.
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
- If your phone isn't already rooted, you can flash Magisk at this point using the instructions in [the root guide](root.md), else continue to the next step.

### Check if Android still starts
- Just restart the phone, and see if Android still works

### Preparing necessary files
- Download the Windows image and make sure it remains in the `Downloads` folder **of your internal storage**, NOT SD card. Make sure it has an **.esd** extension, because other extensions are not supported.
- Download and install the [WOA Helper app](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA), then open it and grant it root access. Do not do anything else inside the app yet.
- Reboot to the modified TWRP. Flash it again if it has been replaced by MIUI recovery.

### Flashing WinInstaller
- In TWRP, select **Install** and then locate **WinInstaller.zip** and flash it.
- Wait untill all processes complete and your device boots into Windows. This will take around 15-20 minutes.

> [!Tip]
> If you wish to skip the Microsoft Account login, press the **I don't have internet** button in the WiFi page, then when prompted, press the **Continue with limited setup** button.
>
> If there is no such button, press the **SIM card** button at the top of the screen (the one that says **Connected**), and press **Disconnect**.

#### Booting to Android
- Run the **Android** shortcut on your desktop (you can also pin it to your start menu / taskbar for ease of access).

#### Booting to Windows
- Press **QUICKBOOT TO WINDOWS** inside the WOA Helper app, or use the newly created toggle in your quick settings panel.

## Finished!


























