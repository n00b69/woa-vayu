<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Uninstallation

### Why is this needed?
If you want to uninstall Windows, this is used instead of deleting partitions manually to avoid human error + writing a whole dedicated guide to just uninstalling.

If you want to relock your bootloader you'll need your partition table to be stock.

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Modded TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery) (new method)

- [gpt_both0.bin](https://github.com/n00b69/woa-vayu/releases/download/Files/gpt_both0.bin) (old method)

## New method

### Flash and boot modified recovery
```cmd
fastboot flash recovery path\to\moddedtwrp.img 
fastboot reboot recovery
```

#### Execute the restore script
```cmd
adb shell restore
```

##### Finished!

## Old method 
> In case the new one didn't work

### Restore GPT
> Replace ```path\to\gpt_both0.bin``` with the path to the gpt_both0.bin file.
```cmd
fastboot flash partition:0 path\to\gpt_both0.bin
```

#### Erase userdata to avoid bootloop and restore FS size
```cmd
fastboot -w
```

##### Finished!









