<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Troubleshooting Issues
> Below you will find a list of common problems and their solutions

## Cannot mount Windows in Android
If mounting Windows produces an empty folder, you either don't have Windows installed, or your rom does not have mount support.

##### Done!


## Cannot write to Windows in Android
> This is caused by shutting down Windows instead of restarting it.
- To solve this, boot to Windows and then press "restart", then as the screen shuts off boot to TWRP and from there load up Android.
- Or, disable hibernation in Windows using [this](https://github.com/n00b69/woa-beryllium/releases/tag/1.0) script 
> Alternatively, if you have already set up the Switch to Android app, simply use this to switch to Android.

##### Done!


## Charging in Windows does not work
> [!WARNING]
> Do not use a powered USB hub with host mode enabled, this can potentially break your device. If you use a powered USB hub, please use the [disable USB host mode guide](/guide/English/Additional-materials-en.md#Disabling-USB-host-mode)

Charging in Windows only works on specific cables. Cables that have been known to work are the original Poco X3 Pro cable (identified by the additional orange/red pin in the USB-A port), and the Nimaso 100W USB-C to USB-C fast charging cable.

##### Done!


## Device can boot into Android but not bootloader
> This is caused by having partitions with a name longer  than 16 characters, such as **Basic data partition**, which has 20 characters
- Reboot to the modded recovery and in the built-in terminal run
```cmd
parted /dev/block/sda
```
- Run ```print``` to list all partitions
- Look for partitions that are more than 16 characters long, for example "Basic Data Partition" and note their volume number
- Rename this partition with ```name $ test```, replacing **$** with the partition number, and replacing **test** with the name you want the partition to have
- Run ```quit```
- Reboot to bootloader in the reboot menu to check if fastboot works again

##### Done!




















