[English](/guide/dualboot.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Android ve Windows Arasında Sorunsuz Çift Önyükleme

### Ön Koşullar
- [UEFI Görüntüsü](https://github.com/n00b69/woa-vayu/releases/tag/UEFI)

- [WOA Helper Uygulaması](https://github.com/n00b69/woa-helper/releases/tag/APK)

## Çift Önyükleme Uygulamasını Kurma
> Bu rehber, cihazınızın root edilmiş olduğunu varsayar. Eğer root edilmediyse, lütfen önce [bu rehberi](/guide/tr-TR/root_tr-TR.md) takip edin.

### Kurulum - Android
- **WOA Helper** uygulamasını indirin, kurun ve ardından açarak root erişimi verin.
- **UEFI görüntüsünü** indirin ve dahili depolama alanınızda `UEFI` adında bir klasörün içine yerleştirin.
- WOA Helper uygulamasını açın ve **WOA ARAÇKUTUSU** içindeki **STA OLUSTURUCU** özelliğini kullanın.
> [!Important]
> Eğer `/sdcard/Windows` klasörü boşsa, ROM'unuz bağlama desteğine sahip değildir ve uygulama içinde bir **boot.img** yedeği oluşturmanız, ardından Windows'a önyükleme yaptığınızda bu yedeği manuel olarak Windows'a kopyalamanız gerekecektir (örneğin, bir yere yükleyip Windows'ta indirerek). Aynı durum, dahili depolama alanında oluşturulan StA dosyaları için de geçerlidir.
>
> Klasör salt okunur durumdaysa da aynı işlemi yapın.
- **WINDOWSA QUICKBOOT ET** butonuna basın.

### Kurulum - Windows
> [!Tip]
> Eğer Windows'a ilk kez önyükleme yapıyorsanız ve Microsoft Hesabı girişini atlamak istiyorsanız, WiFi sayfasında **İnternetim yok** butonuna basın, ardından istendiğinde **Sınırlı kurulumla devam et** butonuna tıklayın.
>
> Eğer böyle bir buton yoksa, ekranın üst kısmındaki **SIM kart** butonuna (**Bağlandı** yazan) tıklayın ve **Bağlantıyı kes** seçeneğini seçin.
- `C:\sta` klasörüne gidin ve eğer yoksa **sta.exe** dosyasından masaüstünüze bir kısayol oluşturun.

#### Android'e Önyükleme
- Masaüstünüzdeki yeni kısayolu çalıştırın (kolay erişim için bunu başlangıç menünüze / görev çubuğunuza sabitleyebilirsiniz).

#### Windows'a Önyükleme
- Uygulama içindeki **WINDOWSA QUICKBOOT ET** butonuna basın veya hızlı ayarlar panelinizde yeni oluşturulan geçişi kullanın.

> [!Important]
> Android ROM'unuzu günceller veya değiştirirseniz, telefonunuzu root ettikten sonra yeni bir **boot.img** yedeği oluşturduğunuzdan emin olun ve bu yedeği Windows'taki **C:\ klasörüne** yerleştirerek eski dosyayı üzerine yazın.
>
> Bunu yapmak için WOA Helper uygulamasındaki **BOOT IMAJI YEDEKLE** özelliğini kullanabilirsiniz.

## Tamamlandı!
