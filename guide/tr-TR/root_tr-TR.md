[English](/guide/root.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Root Rehberi

### Ön Koşullar
- [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)
- [ADB ve Fastboot](https://developer.android.com/studio/releases/platform-tools)
- [Modifiye Edilmiş TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)

### TWRP'ye Önyükleme
> Eğer recover görüntünüz stok recovery ile değiştirildiyse, aşağıdaki komutu kullanarak tekrar flash edin:
```cmd
fastboot flash recovery path\to\moddedtwrp.img reboot recovery
```

#### Önyükleme (Boot) Görüntüsünü Yedekleme
> Bazen Magisk'i flash etmek bootloop'a neden olabilir. Bunu düzeltmek için bir boot.img yedeğini geri yüklemeniz gerekecektir.

TWRP yedekleme özelliğini kullanarak boot bölümünün bir yedeğini alın.

### Magisk'i Flash Etme
- **magisk.apk** dosyasını flash edin (dosyayı magisk.zip olarak yeniden adlandırmanız gerekebilir) ve telefonunuzu yeniden başlatın.
- Telefon açıldığında, **Magisk** uygulamasını bulun ve açın.
- Verilen talimatları izleyin. Eğer birden fazla yöntem sunulursa, **doğrudan yükleme** yöntemini seçin.

Telefonunuz şimdi yeniden başlayacak ve başarıyla root edilmiş olacak.

> [!IMPORTANT]
> Telefonunuzu root ettikten sonra, Android'de ve Windows'ta (WOA Helper uygulamasını kullanarak) yeni bir boot.img yedeği oluşturun ve daha önce yaptığınız tüm boot.img yedeklerini kaldırın. Bunu yapmazsanız, Android'e geçiş yapmak telefonunuzun root'unu kaldıracaktır.
> 
> ROM'unuzu güncelledikten veya değiştirdikten (ve yeniden root ettikten) sonra, bu sayfadaki tüm adımları tekrarlamanız gerekecektir.

## Tamamlandı!
