<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Partitioning your device

### Prerequisites
- Unlocked bootloader

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Modified TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)

- [Latest Vayu firmware](https://xmfirmwareupdater.com/firmware/vayu/)

### Notes
> [!WARNING]  
> All your data will be erased! Back up now if needed.
> 
> Do not run the same command twice.
> 
> DO NOT REBOOT YOUR PHONE if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/woahelperchat).
> 
> Do not run all commands at once, execute them in order!

> [!IMPORTANT]
> Make sure you use the MODDED Recovery throughout this whole tutorial as we provide tools to help aid this installation process and make it as easy as possible for you.
> 
> If you don't use it and you face any errors, consider it your fault and consider yourself alone if you try asking for support as you have deferred from the main guide.

### Opening CMD as an admin
> Download **platform-tools** and extract the folder somewhere, then open CMD as an **administrator**.
>
> It is recommended to keep this window open and use it throughout the entire guide.
> 
> Replace `path\to\platform-tools` with the actual path to the platform-tools folder, for example **C:\platform-tools**.
```cmd
cd path\to\platform-tools
```

#### Flash the modded recovery
> Replace `path\to\moddedtwrp.img` with the actual path to the modded recovery image
```cmd
fastboot flash recovery path\to\moddedtwrp.img reboot recovery
```

#### Backing up your boot image
> This will back up your boot image in the current directory
```cmd
adb pull /dev/block/by-name/boot boot.img
```

### Flashing latest firmware
> [!Important]
> If you are using older Android versions, it is mandatory to flash the latest firmware (this does not affect your current ROM), or Windows will not boot.
>
> If you are on recent Android versions, it is still recommended to do so.
- Download the **vayu firmware.zip** and put it somewhere on your phone.
- Select the **Install** button in TWRP, locate the firmware file, then install it.
- There is no need to reboot yet, stay in TWRP for the next few steps.

### Partitioning your device
> There are two methods to partition your device. Please select the method you would like to use below. 

#### Method 1: Manual partitioning 

<details>
  <summary><strong>Click here for method 1</strong></summary> 

#### Resizing the partition table
```cmd
adb shell sgdisk --resize-table 64 /dev/block/sda
```

#### Opening a shell
```cmd
adb shell
```

### Preparing for partitioning
> [!Note]
> If at any moment in parted you see an error prompting you to type "Yes/No" or "Ignore/Cancel", type `Yes` or `Ignore` depending on the situation to ignore the errors and continue.
>
> If you see any **udevadm** errors, you can ignore these as well.
```cmd
parted /dev/block/sda
```

#### Printing the current partition table
> Parted will print the list of partitions, userdata should be the last partition in the list
```cmd
print
``` 

#### Removing userdata
> Replace **$** with the number of the **userdata** partition, which should be **32**
```cmd
rm $
``` 

#### Recreating userdata
> Replace **11.7GB** with the former start value of **userdata** which we just deleted
>
> Replace **70GB** with the end value you want **userdata** to have. In this example your available usable space in Android will be 70GB-11.7GB = **58.3GB**
```cmd
mkpart userdata ext4 11.7GB 70GB
``` 

#### Creating ESP partition
> Replace **70GB** with the end value of **userdata**
>
> Replace **70.3GB** with the value you used before, adding **0.3GB** to it
```cmd
mkpart esp fat32 70GB 70.3GB
``` 

#### Creating Windows partition
> Replace **70.3GB** with the end value of **esp**
```cmd
mkpart win ntfs 70.3GB -0MB
``` 

#### Making ESP bootable
> Use `print` to see all partitions. Replace "$" with your ESP partition number, which should be **33**
```cmd
set $ esp on
``` 

#### Exit parted
```cmd
quit
``` 

### Formatting data
- Format all data in TWRP, or Android will not boot.
- ( Go to Wipe > Format data > type yes ) 

#### Check if Android still starts
- Just restart the phone, and see if Android still works 

### Formatting Windows and ESP drives
> Reboot into the modded recovery, then run the below command
```cmd
adb shell format
```

### Fixing the GPT
> If you do not do this, Windows may break your device
```cmd
adb shell fixgpt
```

</details>

#### Method 2: Automatic partitioning 

<details>
  <summary><strong>Click here for method 2</strong></summary> 

### Run the partitioning script
> After running the script, enter the size (in GB) that you want Windows to be
>
> Do not write **GB**, just the number (for example **50**)
```cmd
adb shell partition
``` 

### Check if Android still starts
- Just restart the phone, and see if Android still works 

</details>

## [Next step: Rooting your phone](/guide/2-root.md)















