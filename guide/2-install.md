<img align="right" src="https://github.com/woa-vayu/src_vayu_windows/blob/main/2Poco X3 Pro Windows.png" width="350" alt="Windows 11 Running On A Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Installing Windows

### Prerequisites
- A brain

- [Windows on ARM image](https://worproject.com/esd)

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
> [!WARNING]
> DO NOT ERASE, CREATE OR OTHERWISE MODIFY ANY PARTITION WHILE IN DISKPART!!!! THIS CAN ERASE ALL OF YOUR UFS OR PREVENT YOU FROM BOOTING TO FASTBOOT!!!! THIS MEANS THAT YOUR DEVICE WILL BE PERMANENTLY BRICKED WITH NO SOLUTION! (except for taking the device to Xiaomi or flashing it with EDL, both of which will likely cost money)

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

#### Select the ESP volume of the phone
> Use `list volume` to find it, replace "$" with the actual number of **ESPVAYU**
```diskpart
select volume <number>
```

#### Assign the letter Y
```diskpart
assign letter y
```

#### Exit diskpart
```diskpart
exit
```

### Installing Windows
> Replace `<path\to\install.esd>` with the actual path of install.esd (it may also be named install.wim)

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
```

> If you get `Error 87`, check the index of your image with `dism /get-imageinfo /ImageFile:<path\to\install.esd>`, then replace `index:6` with the actual index number of Windows 11 Pro in your image

### Installing drivers
Unpack the Drivers archive you've downloaded earlier and run the `OfflineUpdater_<paneltype>.cmd` script
> When it asks you for the drive letter, enter X:

#### Create Windows bootloader files
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

### Unassign disk letters
> So that they don't stay there after disconnecting the device
```cmd
diskpart
```

#### Select the Windows volume of the phone
> Use `list volume` to find it, replace "$" with the actual number of **WINVAYU**
```diskpart
select volume $
```

#### Unassign the letter X
```diskpart
remove letter x
```

#### Select the ESP volume of the phone
> Use `list volume` to find it, replace "$" with the actual number of **ESPVAYU**
```diskpart
select volume $
```

#### Unassign the letter Y
```diskpart
remove letter y
```

#### Exit diskpart
```diskpart
exit
```

### Reboot your device
> Set up your phone, then proceed to the last step

## [Last step: Setting up dualboot](/guide/dualboot.md)













