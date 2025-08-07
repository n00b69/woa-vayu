[English](/guide/3-install.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Windows Yükleme

### Ön Koşullar
- [Modifiye Edilmiş TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery) (zaten yüklü olmalı)

- [ARM için Windows Görüntüsü](https://arkt-7.github.io/woawin/)

- [Sürücüler](https://github.com/n00b69/woa-vayu/releases/tag/Drivers)

- [UEFI Görüntüsü](https://github.com/n00b69/woa-vayu/releases/tag/UEFI)

### TWRP'ye Önyükleme
> Eğer recovery stok recovery ile değiştirildiyse, aşağıdaki komutu kullanarak tekrar flash edin:
```cmd
fastboot flash recovery path\to\moddedtwrp.img reboot recovery
```

#### MSC Betiğini Çalıştırma
> Tekrar çalıştırmanızı isterse, yapın.
```cmd
adb shell msc
```

### Diskpart
> [!WARNING]  
> DISKPART İÇİNDE HİÇBİR BÖLÜMÜ SİLMEYİN, OLUŞTURMAYIN YA DA DEĞİŞTİRMEYİN! BU, UFS'NİZİN TÜMÜNÜ SİLEBİLİR VEYA FASTBOOT'A ÖNYÜKLEME YAPMANIZI ENGELLEYEBİLİR! BU DURUMDA CİHAZINIZ GERİ DÖNÜLEMEZ ŞEKİLDE BOZULABİLİR (BRICK OLABİLİR)! (Xiaomi'ye götürmek veya [EDL](/guide/tr-TR/edl_tr-TR.md) ile flash etmek dışında çözüm yoktur ve her ikisi de muhtemelen ücretlidir)

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

#### Telefonun ESP Birimini Seçme
> `list volume` komutunu kullanarak bulun, `$` yerine **ESPVAYU**'nun gerçek numarasını yazın.
```diskpart
select volume $
```

#### Y Harfini Atama
```diskpart
assign letter y
```

#### Diskpart'tan Çıkma
```diskpart
exit
```

### Windows'u Yükleme
> `path\to\install.esd` kısmını, install.esd dosyasının gerçek yoluyla değiştirin (dosya install.wim veya 22631.2861.XXXXXXX.esd olarak da adlandırılmış olabilir).
```cmd
dism /apply-image /ImageFile:path\to\install.esd /index:6 /ApplyDir:X:\
```

> Eğer `Error 87` alırsanız, görüntünüzün indeksini şu komutla kontrol edin: `dism /get-imageinfo /ImageFile:path\to\install.esd`, ardından `index:6` kısmını görüntünüzdeki **Windows 11 Pro**'nun gerçek indeks numarasıyla değiştirin.

### Boot.img Dosyasını Windows'a Kopyalama
- **platform-tools** klasöründen **rooted_boot.img** dosyasını Windows Gezgini'nde **WINVAYU** diskine sürükleyip bırakın, ardından adını **boot.img** olarak değiştirin.

### Sürücüleri Yükleme
- Sürücü arşivini açın, ardından `OfflineUpdater.cmd` dosyasını çalıştırın (bir hata çıkarsa, bunun yerine `OfflineUpdaterFix.cmd` dosyasını çalıştırın).

> Eğer bir harf girmenizi isterse, **WINVAYU**'nun sürücü harfini (bu genellikle **X** olmalıdır) girin ve enter tuşuna basın.

#### Windows Önyükleyici Dosyalarını Oluşturma
> Eğer "Failure when attempting to copy boot files" gibi bir hata çıkarsa, tekrar `diskpart` açın ve **ESPVAYU**'ya yeni bir harf atayın, ardından aşağıdaki komutta `Y` harfini yeni atadığınız harfle değiştirin.
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### ESP için Sürücü Harfini Kaldırma
> Bu işlem çalışmazsa, yoksayın ve bir sonraki komuta geçin. Bu hayali sürücü, bilgisayarınızı bir sonraki yeniden başlatmanızda kaybolacaktır.
```cmd
mountvol y: /d
```

### Fastboot'a Yeniden Başlatma
```cmd
adb reboot bootloader
```

#### UEFI'ye Önyükleme
> `path\to\vayu-uefi.img` kısmını, UEFI görüntüsünün gerçek yoluyla değiştirin.
```cmd
fastboot boot path\to\vayu-uefi.img
```

### Android'e Yeniden Başlatma
Cihazınız yaklaşık 10 dakika bekledikten sonra kendi kendine yeniden başlamalı ve Android'e önyükleme yapmalısınız. Son adım için devam edin.

## [Son Adım: Çift Önyükleme Ayar Yapma](/guide/tr-TR/4-dualboot_tr-TR.md)
