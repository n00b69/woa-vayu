<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Driver updating

### Prerequisites
- A brain

- [Drivers](https://github.com/n00b69/woa-vayu/releases/tag/Drivers)

- [Modified TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery) (should already be installed)

### Boot into TWRP
> If your recovery has been replaced by the stock recovery, flash it again using
```cmd
fastboot flash recovery path\to\moddedtwrp.img reboot recovery
```

#### Execute the msc script
> If it asks you to run it once again, do so
```cmd
adb shell msc
```

### Diskpart
```cmd
diskpart
```

#### Select the Windows volume of the phone
> Use `list volume` to find it, replace "$" with the actual number of **WINVAYU**
```diskpart
select volume $
```

#### Assign the letter X
```diskpart
assign letter x
```

#### Exit diskpart
```diskpart
exit
```

### Installing drivers
> Unpack the driver archive, then open the `OfflineUpdater.cmd` file (if an error shows up, run `OfflineUpdaterFix.cmd` instead)

> If it asks you to enter a letter, enter the drive letter of **WINVAYU** (which should be **X**), then press enter

### Reboot your device
> Reboot your device to boot back into Windows. If this boots you to Android, reflash the UEFI image through fastboot or by using the WOA Helper app

## Finished!













