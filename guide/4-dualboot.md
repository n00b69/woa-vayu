<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Dualboot guide

### Prerequisites
- [UEFI image](https://github.com/n00b69/woa-vayu/releases/tag/UEFI)

- [WOA Helper app](https://github.com/n00b69/woa-helper/releases/tag/APK)

## Dualboot guide
This guide assumes you are rooted, if you aren't, please follow [this guide](root.md) first.

### Setup - Android
- Download and install the **WOA Helper** app, then open it and grant it root access.
- Download the **UEFI image** and place it inside the folder named `UEFI` in your internal storage.
- Open the WOA Helper app and press the **QUICKBOOT TO WINDOWS** button.

### Setup - Windows
> [!Tip]
> If this is your first time booting Windows and you wish to skip the Microsoft Account login, press the **I don't have internet** button in the WiFi page, then when prompted, press the **Continue with limited setup** button.
>
> If there is no such button, press the **SIM card** button at the top of the screen (the one that says **Connected**), and press **Disconnect**.

#### Booting to Android
- Run the new shortcut on your desktop (you can also pin it to your start menu / taskbar for ease of access)

#### Booting to Windows
- Press **QUICKBOOT TO WINDOWS** inside the app, or use the newly created toggle in your quick settings panel

> [!Important]
> If you ever update or change your Android ROM, make sure to create a new **boot.img** backup (after rooting your phone!) and place it inside the **C:\ folder** in Windows, overwriting the old file.
>
> You can use the **BACK UP BOOT IMAGE** feature in the WOA Helper app to do so.

## Finished!
