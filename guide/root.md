<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Root guide

### Prerequisites
- [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Modified TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)

### Boot into TWRP
> If your recovery has been replaced by the stock recovery, flash it again using
```cmd
fastboot flash recovery path\to\moddedtwrp.img reboot recovery
```

#### Backing up your boot image
> Sometimes flashing Magisk can cause a bootloop. To fix this, you'll need to restore a boot.img backup.

Use the TWRP backup feature to make a backup of the boot partition.

### Flashing Magisk
- Flash the **magisk.apk** (you may have to rename it to magisk.zip) and reboot your phone. 
- Once booted, locate the **Magisk** app and open it.
- Follow any instructions provided. Select the **direct install** method if you are provided with several methods.

Your phone will now reboot, and you have succesfully rooted it.

> [!IMPORTANT]
> After you've rooted your phone, create a new boot.img backup in Android and in Windows (using the WOA Helper app) and remove any remaining boot.img backups you have made previously. If you don't do this, switching to Android will unroot your phone.
> 
> After updating or changing your rom (and rerooting) you will have to repeat all the steps on this page.

## Finished!
