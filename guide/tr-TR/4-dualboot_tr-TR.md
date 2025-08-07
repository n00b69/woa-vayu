[English](/guide/4-dualboot.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Çift Önyükleme (Dualboot) Rehberi

### Ön Koşullar
- [UEFI Görüntüsü](https://github.com/n00b69/woa-vayu/releases/tag/UEFI)

- [WOA Helper Uygulaması](https://github.com/n00b69/woa-helper/releases/tag/APK)

## Çift Önyükleme (Dualboot) Rehberi
Bu rehber, cihazınızın root edilmiş olduğunu varsayar. Eğer root edilmediyse, lütfen önce [bu rehberi](/guide/tr-TR/root_tr-TR.md) takip edin.

### Kurulum - Android
- **WOA Helper** uygulamasını indirin, kurun ve ardından açarak root erişimi verin.
- **UEFI görüntüsünü** indirin ve dahili depolama alanınızda `UEFI` adında bir klasörün içine yerleştirin.
- WOA Helper uygulamasını açın ve **WINDOWS QUICKBOOT ET** butonuna basın.

### Kurulum - Windows
> [!Tip]
> Eğer Windows'a ilk kez önyükleme yapıyorsanız ve Microsoft Hesabı girişini atlamak istiyorsanız, WiFi sayfasında **İnternetim yok** butonuna basın, ardından istendiğinde **Sınırlı kurulumla devam et** butonuna tıklayın.
>
> Eğer böyle bir buton yoksa, ekranın üst kısmındaki **SIM kart** butonuna (**Bağlandı** yazan) tıklayın ve **Bağlantıyı kes** seçeneğini seçin.

#### Android'e Önyükleme
- Masaüstünüzdeki yeni kısayolu çalıştırın (kolay erişim için bunu başlangıç menünüze / görev çubuğunuza sabitleyebilirsiniz).

#### Windows'a Önyükleme
- Uygulama içindeki **WINDOWS QUICKBOOT ET** butonuna basın veya hızlı ayarlar panelinizde yeni oluşturulan geçişi kullanın.

> [!Important]
> Android ROM'unuzu günceller veya değiştirirseniz, telefonunuzu root ettikten sonra yeni bir **boot.img** yedeği oluşturduğunuzdan emin olun ve bu yedeği Windows'taki **C:\ klasörüne** yerleştirerek eski dosyayı üzerine yazın.
>
> Bunu yapmak için WOA Helper uygulamasındaki **BOOT IMAJINI YEDEKLE** özelliğini kullanabilirsiniz.

## Tamamlandı!
