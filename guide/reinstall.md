<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Reinstalling Windows

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Modified TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery) (should already be installed)

### Boot into TWRP
> If MIUI has replaced your recovery, boot to fastboot and run
```cmd
fastboot flash recovery path\to\twrp.img reboot recovery
```

#### Formatting the Windows partition
```cmd
adb shell format
```

## [Next step: Reinstalling Windows](/guide/2-install.md)




















  
