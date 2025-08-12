[English](/guide/nopc.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Windows'u PC Olmadan Yükleme

### Ön Koşullar
- Root edilmiş bir POCO X3 Pro
- [Termux](https://play.google.com/store/apps/details?id=com.termux) (yalnızca özel bir kurtarma yüklü değilse)
- [Modifiye Edilmiş TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)
- [En Güncel Vayu Firmware'i](https://xmfirmwareupdater.com/firmware/vayu/)
- [Vayu WinInstaller](https://github.com/Kumar-Jy/WinInstaller/releases/tag/Vayu_WinInstaller)
- [ARM için Windows Görüntüsü](https://arkt-7.github.io/woawin/)
- [WOA Helper Uygulaması](https://github.com/n00b69/woa-helper/releases/tag/APK)

### Notlar
> [!WARNING]  
> Tüm verileriniz silinecek! Gerekirse şimdi yedekleme yapın.
>  
> Hata yaptığınızı düşünüyorsanız telefonunuzu YENİDEN BAŞLATMAYIN, [Telegram sohbet grubunda](https://t.me/wininstaller) yardım isteyin.

### Cihazınızı Root Etme
> Cihazınız zaten root edilmişse, bir sonraki adıma geçin; aksi takdirde [bu talimatları](/guide/tr-TR/root_tr-TR.md) kullanarak root edin (bunu yapmak için bir PC'ye ihtiyacınız olacak).

### Modifiye Edilmiş TWRP'yi Flash Etme
> Özel(Custom) bir recovey yüklüyse, bunun yerine modifiye edilmiş TWRP'yi oradan yükleyebilirsiniz.
- Modifiye edilmiş TWRP'yi indirin, adını **TWRP.img** olarak değiştirin ve **dahili depolamanızın** `Download(İndirilenler)` klasöründe bırakın.
- **Termux**'u indirin, açın ve root erişimi verin.
- Termux'ta aşağıdaki komutu çalıştırarak TWRP'yi flash edin:
```cmd
su -c dd if=/sdcard/Download/TWRP.img of=/dev/block/by-name/recovery
```
- Termux'ta aşağıdaki komutu çalıştırarak TWRP'ye yeniden başlatın:
```cmd
su -c reboot recovery
```

#### TWRP Terminalini Açma
- TWRP'ye önyükleme yaptıktan sonra, sizden parola istenirse verilerin şifresini çözmek için parolanızı girin.
- Ekranın sağ alt köşesindeki **Advanced (Gelişmiş)** butonuna basın, ardından **Terminal**'e tıklayın.

### Bölümleme (partitioning) Scriptini Çalıştırma
> **$** yerine Windows için istediğiniz depolama miktarını yazın ('GB' eklemeyin, sadece sayıyı yazın).  
>
> Bir kez daha çalıştırmanızı isterse, bunu yapın
```cmd
partition $
```

### Android'in Çalışıp Çalışmadığını Kontrol Etme
- Telefonu yeniden başlatın ve Android'in çalışıp çalışmadığını kontrol edin.

### Gerekli Dosyaları Hazırlama
- Windows görüntüsünü indirin ve **dahili depolamanızın** `Download` klasöründe kaldığından emin olun, SD kartta değil.
- **WinInstaller**'ı indirin ve dahili depolamanızda bırakın.
- **vayu firmware.zip** dosyasını indirin ve dahili depolamanızda bırakın.
- [WOA Helper uygulamasını](https://github.com/n00b69/woa-helper/releases/tag/APK) indirin ve yükleyin, ardından açın ve root erişimi verin. Uygulama içinde henüz başka bir şey yapmayın.
- Modifiye edilmiş TWRP'ye yeniden başlatın. MIUI kurtarma ile değiştirildiyse tekrar flash edin.

### WinInstaller'ı Flash Etme
- TWRP'de **Yükle**'yi seçin, ardından **vayu firmware.zip** dosyasını bulun ve flash edin.
- Firmware flash edildikten sonra yeniden başlatmayın. Bunun yerine, **WinInstaller.zip** dosyasını da flash edin.
- Tüm işlemler tamamlanana ve cihazınız Windows'a önyükleme yapana kadar bekleyin. Bu işlem yaklaşık 15-20 dakika sürecektir.

> [!Tip]  
> Microsoft Hesabı girişini atlamak istiyorsanız, WiFi sayfasında **İnternetim yok** butonuna basın, ardından istendiğinde **Sınırlı kurulumla devam et** butonuna basın.  
> Böyle bir buton yoksa, ekranın üst kısmındaki **SIM kart** butonuna (**Bağlandı** yazan) basın ve **Bağlantıyı kes**'e tıklayın.

#### Android'e Önyükleme Yapma
- Masaüstünüzdeki **Android** kısayolunu çalıştırın (kolay erişim için başlangıç menünüze / görev çubuğunuza sabitleyebilirsiniz).

#### Windows'a Önyükleme Yapma
- WOA Helper uygulamasında **WINDOWS'A HIZLI ÖNYÜKLEME**'ye basın veya hızlı ayarlar panelinizde yeni oluşturulan geçişi kullanın.

## Tamamlandı!
