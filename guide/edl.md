<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Running Windows on the POCO X3 Pro

## Restoring the device in EDL mode
> This is done as a last resort when your device either only boots to EDL mode by itself, or if you are unable to restore it with other means

### Prerequisites
- A crypto wallet with $3 USDT

- [A Telegram account](https://telegram.org)

- [MiFlash HXRU Auth Tool](https://hxrutool.com)

- [Stock fastboot rom](http://xmfirmwareupdater.com/miui/vayu/)

### Setting up HXRU Tool
- Create a HRXU account [here](https://dashboard.hxrutool.com/Register)
- Download **MiFlash HXRU Auth Tool** on the homepage
- Inside **MiFlash_HXRU.rar** you will find a folder with a file inside called **PASS123.rar**, open it with password `123`
- Inside this protected archive is a folder containing **MiFlash_HXRU.zip**. Extract its contents somewhere

### Buy credits
> Contact [@hxruofficial](https://t.me/hxruofficial) on Telegram to buy credits.
> 
> You will need **5** credits to flash your device using this tool, which will cost around **$3**

### Booting into EDL mode
> [!Note]
> If you're already in EDL mode, skip this step and continue with "Flashing your device"
- If your bootloader is unlocked and if you have access to fastboot mode, run ```fastboot oem edl``` to boot to EDL mode.

> If your bootloader is locked, or Android doesn't boot and you cannot access fastboot mode in any way, you will need to either remove the back of your device to short the EDL testpoints, or you will have to use an EDL cable
>
> (Not all EDL cables work and you may risk wasting money on one that won't, but this is probably still better than having to open your device).
- Look for a cable that has **V2** in its name, for example **Hydra V2 EDL Cable** or **V2 EDL Pro Cable**. Make sure it is for USB-C devices.
- Insert the cable into your device, then hold the button on the cable which may look like [this](https://t.me/nabuwoa/204867).
- It should boot you into EDL mode now.

### Installing EDL drivers
> If the device in **Device Manager** is called **QUSB_BULK_CID** or has a ⚠️ yellow warning triangle / question mark, and is located in any other category (for example **Other devices**), you need to install EDL drivers first.
- To install EDL drivers, extract the contents of [QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip) somewhere, right click on **QUSB_BULK_CID**, click on **Update driver** and **Browse my computer for drivers**, then find and select the **QUD** folder.

### Flashing your device
- Open **XiaoMiFlash.exe** and grant it administrator access.
- Download the stock fastboot rom for your device (which should have a .tgz extension) and open it. Inside there should be a .tar file. Extract the contents of this .tar file into any folder).
- Click the **select** button in **XiaoMiFlash** and select this folder.
- Press **flash**.
- If you get a `write time out` error, hold the **power** + **volume down** button for +- 30 seconds to reboot EDL. After this press the **flash** button again.
- After a few seconds a login popup should show up. Enter your HRXU account details here and press **Request Auth Flashing**.
- After it says **flash done**, reboot your device by holding **power** +- 14 seconds.

## Finished!















