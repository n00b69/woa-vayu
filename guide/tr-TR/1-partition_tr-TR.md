[English](/guide/1-partition.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Cihazınızı Bölümleme

### Ön Koşullar
- Bootloader kilidinin açık olması

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Modifiye Edilmiş TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)

- [En Güncel Vayu Firmware'i](https://xmfirmwareupdater.com/firmware/vayu/)

### Notlar
> [!WARNING]  
> Tüm verileriniz silinecek! Gerekirse şimdi yedekleme yapın.
> 
> Aynı komutu iki kez çalıştırmayın.
> 
> Hata yaptığınızı düşünüyorsanız TELEFONUNUZU YENİDEN BAŞLATMAYIN, [Telegram sohbet grubunda](https://t.me/WaLoVayu) yardım isteyin.
> 
> Tüm komutları bir kerede çalıştırmayın, sırayla uygulayın!

> [!IMPORTANT]
> Bu rehber boyunca MODİFİYE EDİLMİŞ TWRP Recovery kullanmanız zorunludur, çünkü bu kurulum sürecini kolaylaştırmak için sunduğumuz araçları destekler.
>
> Eğer modifiye edilmiş recovery kullanmazsanız ve bir hata ile karşılaşırsanız, bu sizin hatanız olarak kabul edilir ve ana rehberden sapmış olmanız nedeniyle destek alamayabilirsiniz.

### CMD'yi Yönetici Olarak Açma
> **platform-tools** dosyasını indirin ve bir yere çıkarın, ardından CMD'yi **yönetici** olarak açın.
>
> Bu pencereyi rehber boyunca açık tutmanız önerilir.
> 
> `path\to\platform-tools` yerine platform-tools klasörünün gerçek yolunu yazın, örneğin **C:\platform-tools**.
```cmd
cd path\to\platform-tools
```

#### Modifiye edilmiş recovery'i flash etme
> `path\to\moddedtwrp.img` yerine modifiye edilmiş recovery dosyasının gerçek yolunu yazın.
```cmd
fastboot flash recovery path\to\moddedtwrp.img reboot recovery
```

#### Önyükleme (boot) görüntüsünü yedekleme
> Bu işlem, önyükleme görüntünüzü mevcut dizine yedekler.
```cmd
adb pull /dev/block/by-name/boot boot.img
```

### En güncel firmware'i flash etme
> [!Important]
> Eski Android sürümlerini kullanıyorsanız, en güncel firmware'i flash etmek zorunludur (bu, mevcut ROM'unuzu etkilemez), aksi takdirde Windows açılmaz.
>
> Güncel Android sürümlerindeyseniz, bunu yapmak yine de önerilir.
- **vayu firmware.zip** dosyasını indirin ve telefonunuzda bir yere kaydedin.
- TWRP'de **Yükle(Install)** butonuna tıklayın, firmware dosyasını bulun ve yükleyin.
- Henüz yeniden başlatmaya gerek yok, sonraki adımlar için TWRP'de kalın.

### Cihazınızı Bölümleme
> Cihazınızı bölümlemek için iki yöntem bulunmaktadır. Lütfen aşağıdan kullanmak istediğiniz yöntemi seçin.

#### Yöntem 1: Manuel Bölümleme 

<details>
  <summary><strong>Yöntem 1 için buraya tıklayın</strong></summary> 

#### Bölüm tablosunu(partition) yeniden boyutlandırma
```cmd
adb shell sgdisk --resize-table 64 /dev/block/sda
```

#### Shell açma
```cmd
adb shell
```

### Bölümleme için hazırlık
$${\color{lightblue}🟦 Not}$$
> Parted'de herhangi bir noktada "Yes/No" veya "Ignore/Cancel" gibi bir hata mesajı görürseniz, duruma göre `Yes` veya `Ignore` yazarak hataları yok sayın ve devam edin.
>
> **udevadm** hataları görürseniz, bunları da yok sayabilirsiniz.
```cmd
parted /dev/block/sda
```

#### Mevcut bölüm tablosunu yazdırma
> Parted, bölümlerin listesini yazdıracaktır; **userdata** bölümü listenin sonunda olmalıdır.
```cmd
print
``` 

#### Userdata bölümünü kaldırma
> **$** yerine **userdata** bölümünün numarasını yazın, bu genellikle **32** olmalıdır.
```cmd
rm $
``` 

#### Userdata bölümünü yeniden oluşturma
> **11.7GB** yerine az önce sildiğimiz **userdata** bölümünün eski başlangıç değerini yazın.
>
> **70GB** yerine **userdata** bölümünün sahip olmasını istediğiniz bitiş değerini yazın. Bu örnekte Android'de kullanılabilir alanınız 70GB - 11.7GB = **58.3GB** olacaktır.
```cmd
mkpart userdata ext4 11.7GB 70GB
``` 

#### ESP bölümü oluşturma
> **70GB** yerine **userdata** bölümünün bitiş değerini yazın.
>
> **70.3GB** yerine önceki kullandığınız değere **0.3GB** eklenmiş halini yazın.
```cmd
mkpart esp fat32 70GB 70.3GB
``` 

#### Windows bölümü oluşturma
> **70.3GB** yerine **esp** bölümünün bitiş değerini yazın.
```cmd
mkpart win ntfs 70.3GB -0MB
``` 

#### ESP bölümünü önyüklenebilir yapma
> Tüm bölümleri görmek için `print` komutunu kullanın. **$** yerine ESP bölüm numaranızı yazın, bu genellikle **33** olmalıdır.
```cmd
set $ esp on
``` 

#### Parted'den çıkma
```cmd
quit
``` 

### Verileri formatlama
- Android'un açılabilmesi için TWRP'de tüm verileri formatlayın.
- ( Wipe (Sil) > Format Data (Verileri Formatla) > "yes" yazın)

#### Android'in çalışıp çalışmadığını kontrol etme
- Telefonu yeniden başlatın ve Android'in çalışıp çalışmadığını kontrol edin.

### Windows ve ESP sürücülerini formatlama
> Modifiye edilmiş recovery ile yeniden başlatın, ardından aşağıdaki komutu çalıştırın.
```cmd
adb shell format
```

### GPT'yi düzeltme
> Bunu yapmazsanız, Windows cihazınızı bozabilir.
```cmd
adb shell fixgpt
```

</details>

#### Yöntem 2: Otomatik Bölümleme 

<details>
  <summary><strong>Yöntem 2 için buraya tıklayın</strong></summary> 

### Bölümleme betiğini çalıştırma
> Betiği çalıştırdıktan sonra, Windows için istediğiniz boyutu (GB cinsinden) girin.
>
> **GB** yazmayın, sadece sayıyı girin (örneğin **50**).
```cmd
adb shell partition
``` 

### Android'in çalışıp çalışmadığını kontrol etme
- Telefonu yeniden başlatın ve Android'in çalışıp çalışmadığını kontrol edin.

</details>

## [Sonraki adım: Telefonunuzu root etme](/guide/tr-TR/2-root_tr-TR.md)
