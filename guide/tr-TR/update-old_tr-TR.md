[English](/guide/update-old.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Sürücüleri Güncelleme

### Ön Koşullar
- [Modifiye Edilmiş TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery) (zaten yüklü olmalı)

- [Sürücüler](https://github.com/n00b69/woa-vayu/releases/tag/Drivers)

- [UEFI Görüntüsü](https://github.com/n00b69/woa-vayu/releases/tag/UEFI)

### TWRP'ye Önyükleme
> Eğer recovery görüntünüz stok recovery ile değiştirildiyse, aşağıdaki komutu kullanarak tekrar flash edin:
```cmd
fastboot flash recovery path\to\moddedtwrp.img reboot recovery
```

#### MSC Betiğini Çalıştırma
> Tekrar çalıştırmanızı isterse, yapın.
```cmd
adb shell msc
```

### Diskpart
```cmd
diskpart
```

#### Telefonun Windows Birimini Seçme
> `list volume` komutunu kullanarak bulun, `$` yerine **WINVAYU**'nun gerçek numarasını yazın.
```diskpart
select volume $
```

#### X Harfini Atama
```diskpart
assign letter x
```

#### Diskpart'tan Çıkma
```diskpart
exit
```

### Sürücüleri Yükleme
> [!Note]
> Bu işlem yaklaşık 20 dakika sürecektir. Endişelenmeyin, bu normaldir.

- Sürücü arşivini açın, ardından `OfflineUpdater.cmd` dosyasını çalıştırın (bir hata çıkarsa, bunun yerine `OfflineUpdaterFix.cmd` dosyasını çalıştırın).

> Eğer bir harf girmenizi isterse, **WINVAYU**'nun sürücü harfini (bu genellikle **X** olmalıdır) girin ve enter tuşuna basın.

### Cihazınızı Yeniden Başlatma
> Android'de UEFI görüntüsünü de değiştirdiğinizden emin olun, aksi takdirde Windows'a önyükleme yaparken "mavi ekran hatası" (BSoD) ile karşılaşabilirsiniz.
```cmd
adb reboot
```

## Tamamlandı!
