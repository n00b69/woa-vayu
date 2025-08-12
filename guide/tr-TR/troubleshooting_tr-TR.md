[English](/guide/troubleshooting.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Sorun Giderme
> Aşağıda, yaygın sorunların ve çözümlerinin bir listesini bulabilirsiniz.

## Android'de Windows'u Bağlayamama
Windows'u bağlamaya çalıştığınızda boş bir klasör görünüyorsa, ya Windows yüklü değildir ya da ROM'unuz bağlama desteğine sahip değildir.

##### Tamamlandı!

## Android'de Windows'a Yazamama
> Bu sorun, Windows'u yeniden başlatmak yerine kapatmanızdan kaynaklanır.
- Bunu çözmek için Windows'a önyükleme yapın, ardından "yeniden başlat" seçeneğine basın. Ekran kapandığında TWRP'ye önyükleme yapın ve oradan Android'e geçin.
- Alternatif olarak, Windows'ta hazırda bekletme modunu devre dışı bırakmak için [bu betiği](https://github.com/n00b69/woa-beryllium/releases/tag/1.0) kullanabilirsiniz.
> Eğer zaten Switch to Android uygulamasını kurduysanız, Android'e geçmek için bunu kullanabilirsiniz.

##### Tamamlandı!

## Windows'ta Şarj Olmama
> [!WARNING]
> Ana bilgisayar modu etkinleştirilmiş bir güçlendirilmiş USB hub kullanmayın, bu cihazınızı bozabilir. Eğer güçlendirilmiş bir USB hub kullanıyorsanız, lütfen [USB ana bilgisayar modunu devre dışı bırakma rehberini](/guide/English/Additional-materials-en.md#Disabling-USB-host-mode) kullanın.

Windows'ta şarj yalnızca belirli kablolarla çalışır. Çalıştığı bilinen kablolar, orijinal Poco X3 Pro kablosu (USB-A portunda ek turuncu/kırmızı pim ile tanımlanır) ve Nimaso 100W USB-C'den USB-C'ye hızlı şarj kablosudur.

##### Tamamlandı!

## Cihaz Android'e Önyükleme Yapabiliyor Ancak Önyükleyiciye (Bootloader) Giremiyor
> Bu sorun, **Basic data partition** gibi 16 karakterden uzun isimlere sahip bölümlerden kaynaklanır (örneğin, bu bölüm 20 karakterdir).
- Modifiye edilmiş kurtarma moduna yeniden başlatın ve yerleşik terminalde şu komutu çalıştırın:
```cmd
parted /dev/block/sda
```
- Tüm bölümleri listelemek için ```print``` komutunu çalıştırın.
- 16 karakterden uzun olan bölümleri arayın, örneğin "Basic Data Partition" ve bu bölümün hacim numarasını not edin.
- Bölümü yeniden adlandırmak için ```name $ test``` komutunu çalıştırın; burada **$** yerine bölüm numarasını, **test** yerine ise bölüme vermek istediğiniz adı yazın.
- ```quit``` komutunu çalıştırın.
- Yeniden başlatma menüsünden önyükleyiciye geçerek fastboot'un tekrar çalışıp çalışmadığını kontrol edin.

##### Tamamlandı!
