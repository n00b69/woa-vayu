[English](/guide/uninstall.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Kaldırma

### Neden Bu Gerekli?
Windows'u kaldırmak istiyorsanız, insan hatasını önlemek ve yalnızca kaldırma için ayrı bir rehber yazmak yerine bu yöntem kullanılır.

Eğer önyükleyici kilidini tekrar kilitlemek istiyorsanız, bölüm tablonuzun stok (orijinal) olması gerekir.

### Ön Koşullar
- [ADB ve Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Modifiye Edilmiş TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery) (yeni yöntem)

- [gpt_both0.bin](https://github.com/n00b69/woa-vayu/releases/download/Files/gpt_both0.bin) (eski yöntem)

## Yeni Yöntem

### Android'e Geçiş
> Aksi takdirde, Windows'u kaldırdıktan sonra cihazınız Android'e önyükleme yapmaz.
- Masaüstünüzdeki **Switch to Android** veya **Android** kısayolunu çalıştırın veya fastboot/kurtarma modunda bir **boot.img** yedeğini flash edin.

### Modifiye Edilmiş Recovery Görüntüsünü Flash Etme ve Önyükleme
> `path\to\moddedtwrp.img` kısmını, modifiye edilmiş recovery görüntüsünün gerçek yoluyla değiştirin.
```cmd
fastboot flash recovery path\to\moddedtwrp.img reboot recovery
```

### Geri Yükleme Scriptini Çalıştırma
```cmd
adb shell restore
```

##### Tamamlandı!

## Eski Yöntem
> Yeni yöntem işe yaramazsa kullanılır.

### Android'e Geçiş
> Aksi takdirde, Windows'u kaldırdıktan sonra cihazınız Android'e önyükleme yapmaz.
- Masaüstünüzdeki **Switch to Android** veya **Android** kısayolunu çalıştırın veya fastboot/kurtarma modunda bir **boot.img** yedeğini flash edin.

### Fastboot Moduna Önyükleme
> Telefon kapalıyken ses kısma + güç tuşuna basılı tutun veya cihaz açıkken aşağıdaki komutu çalıştırın:
```cmd
adb reboot bootloader
```

### GPT'yi Geri Yükleme
> ```path
```cmd
fastboot flash partition:0 path\to\gpt_both0.bin
```

#### Userdata'yı Silme
> Önyükleme döngüsünü (bootloop) önlemek ve dosya sistemi boyutunu geri yüklemek için:
```cmd
fastboot -w
```

##### Tamamlandı!
