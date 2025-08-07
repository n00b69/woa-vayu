[English](/guide/reinstall.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Windows'u Yeniden Yükleme

### Ön Koşullar
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Modifiye edilmiş TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery) (zaten yüklü olmalıdır)

### TWRP'ye Başlatma
> MIUI recovery'yi değiştirdiyse, fastboot'a önyükleme yapın ve çalıştırın
```cmd
fastboot flash recovery path\to\twrp.img reboot recovery
```

#### Windows bölümünü biçimlendirme
```cmd
adb shell format
```

## [Sonraki adım: Windows'u Yeniden Yükleme](/guide/tr-TR/3-install_tr-TR.md)
