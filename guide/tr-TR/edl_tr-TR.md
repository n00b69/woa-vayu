[English](/guide/edl.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Cihazı EDL Modunda Geri Yükleme
> Bu işlem, cihazınız yalnızca EDL moduna kendi kendine önyükleme yapıyorsa veya başka yollarla geri yüklenemiyorsa son çare olarak yapılır.

### Ön Koşullar
- 3 USDT içeren bir kripto cüzdanı
- [Bir Telegram hesabı](https://telegram.org)
- [MiFlash HXRU Auth Tool](https://hxrutool.com)
- [Stok fastboot ROM](http://xmfirmwareupdater.com/miui/vayu/)

### HXRU Aracını Kurma
- [Buradan](https://dashboard.hxrutool.com/Register) bir HRXU hesabı oluşturun.
- Ana sayfadan **MiFlash HXRU Auth Tool**'u indirin.
- **MiFlash_HXRU.rar** dosyası içinde, **PASS123.rar** adında bir dosya bulunan bir klasör bulacaksınız; bu dosyayı `123` şifresiyle açın.
- Bu korumalı arşivin içinde **MiFlash_HXRU.zip** dosyası bulunan bir klasör var. İçeriğini bir yere çıkarın.

### Kredi Satın Alma
> Telegram üzerinden [@hxruofficial](https://t.me/hxruofficial) ile iletişime geçerek kredi satın alın.
> 
> Bu aracı kullanarak cihazınızı flash etmek için **5** krediye ihtiyacınız olacak, bu yaklaşık **3 dolar** tutar.

### EDL Moduna Önyükleme
> [!Note]
> Eğer zaten EDL modundaysanız, bu adımı atlayın ve "Cihazınızı Flash Etme" ile devam edin.
- Eğer önyükleyici kilidiniz açıksa ve fastboot moduna erişiminiz varsa, EDL moduna geçmek için şu komutu çalıştırın:
```cmd
fastboot oem edl
```

> Eğer önyükleyici kilitliyse veya Android açılmıyorsa ve fastboot moduna hiçbir şekilde erişemiyorsanız, cihazınızın arka kapağını açarak EDL test noktalarını kısa devre yapmanız ya da bir EDL kablosu kullanmanız gerekecek.
>
> (Tüm EDL kabloları çalışmaz ve çalışmayan bir kablo alarak paranızı riske atabilirsiniz, ancak bu muhtemelen cihazınızı açmaktan daha iyi bir seçenektir).
- Adında **V2** olan bir kablo arayın, örneğin **Hydra V2 EDL Cable** veya **V2 EDL Pro Cable**. Kablonun USB-C cihazlar için olduğundan emin olun.
- Kabloyu cihazınıza takın, ardından kablo üzerindeki butona basılı tutun; bu buton [şu şekilde](https://t.me/nabuwoa/204867) görünebilir.
- Bu işlem sizi EDL moduna önyüklemelidir.

### EDL Sürücülerini Yükleme
> Eğer **Aygıt Yöneticisi**'nde cihaz **QUSB_BULK_CID** olarak görünüyorsa veya yanında ⚠️ sarı uyarı üçgeni / soru işareti varsa ve başka bir kategoride (örneğin **Diğer cihazlar**) yer alıyorsa, önce EDL sürücülerini yüklemeniz gerekir.
- EDL sürücülerini yüklemek için, [QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip) dosyasının içeriğini bir yere çıkarın, **QUSB_BULK_CID** üzerine sağ tıklayın, **Sürücüyü güncelle**'ye tıklayın ve **Bilgisayarımdaki sürücüleri tara** seçeneğini seçin, ardından **QUD** klasörünü bulun ve seçin.

### Cihazınızı Flash Etme
- **XiaoMiFlash.exe**'yi açın ve yönetici erişimi verin.
- Cihazınız için stok fastboot ROM'unu indirin (bu bir .tgz uzantısına sahip olmalıdır) ve açın. İçinde bir .tar dosyası olmalı. Bu .tar dosyasının içeriğini herhangi bir klasöre çıkarın.
- **XiaoMiFlash**'te **seç** butonuna tıklayın ve bu klasörü seçin.
- **Flash** butonuna basın.
- Eğer `write time out` hatası alırsanız, **güç** + **ses kısma** tuşuna yaklaşık 30 saniye basılı tutarak EDL moduna yeniden başlatın. Ardından tekrar **flash** butonuna basın.
- Birkaç saniye sonra bir oturum açma penceresi görünmelidir. Buraya HRXU hesap bilgilerinizi girin ve **Request Auth Flashing**'e basın.
- **Flash done** mesajını gördükten sonra, cihazınızı yeniden başlatmak için **güç** tuşuna yaklaşık 14 saniye basılı tutun.

## Tamamlandı!
