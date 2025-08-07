[English](/guide/2-root.md) | **Türkçe** 

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Cihazınızı Root Etme

### Ön Koşullar
- [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)

### Önyükleme (Boot) Görüntüsünü Android'e Kopyalama
- Telefonunuzu bilgisayarınıza bağlayın (USB hata ayıklama özelliği etkin olmalı).
- Telefonunuzda, bilgisayarınızın telefon verilerinize erişmesine izin vermek için çıkan uyarıya tıklayın. Eğer uyarı çıkmazsa, bildirim paneline gidin, USB bildirimine tıklayın ve bağlantı türünü **dosya aktarımı** olarak değiştirin.
- **platform-tools** klasöründen **boot.img** dosyasını telefonunuzun dahili depolama alanına kopyalayın.

#### Önyükleme (Boot) Görüntüsünü Yamalama
- **Magisk** uygulamasını indirin, kurun ve ardından açın.
- **Yükle** > **Bir dosyayı yama** seçeneğine tıklayın ve az önce kopyaladığınız **boot.img** dosyasını seçin.
- Yamalama işlemi tamamlandığında, **Downloads(İndirilenler)** klasörünüzde oluşan **magisk_patched-27000_XXXX.img** dosyasını bulun ve bilgisayarınızdaki **platform-tools** klasörüne kopyalayın.

### Fastboot Moduna Yeniden Başlatma
```cmd
adb reboot bootloader
```

#### Root Edilmiş Önyükleme Görüntüsünü Flash Etme
> `path\to\magisk_patched.img` kısmını, dosyanın gerçek konumuyla değiştirin.
```cmd
fastboot flash boot path\to\magisk_patched.img
```

### Android'e Yeniden Başlatma
```cmd
fastboot reboot
```

#### Kurulumu Tamamlama
- **Magisk** uygulamasını tekrar açın.
- Ekranda çıkan talimatları takip edin; cihazınız birkaç saniye içinde yeniden başlayacaktır.

### Root Edilmiş Önyükleme Görüntüsünü Kopyalama
> Cihazınız Android'e yeniden başladıktan sonra:
```cmd
adb shell "su -c cp /dev/block/by-name/boot /sdcard/rooted_boot.img" & adb pull /sdcard/rooted_boot.img
```
- Telefon ekranında Shell için bir süper kullanıcı (superuser) isteği belirebilir. Eğer belirirse, erişim izni verin.
- Komut başarısız olursa, **Magisk** uygulamasını açın, `Superuser` sekmesine gidin, **Shell**'i bulun ve erişim izni verin.

## [Sonraki Adım: Windows Yükleme](/guide/tr-TR/3-install_tr-TR.md)
