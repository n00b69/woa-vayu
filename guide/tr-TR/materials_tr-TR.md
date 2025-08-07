[English](/guide/materials.md) | **Türkçe**

<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Poco X3 Pro üzerinde çalışan Windows 11">

# POCO X3 Pro Üzerinde Windows Çalıştırma

## Ek Materyaller
> Aşağıda, ARM cihazınızda Windows için çeşitli ince ayarlar ve materyallerin bir listesini bulabilirsiniz.

### Desteklenen Uygulamalar/Oyunlar Listesi
> Bu listeler kapsamlı değildir, ancak topluluk tarafından test edilmiş uygulama ve oyunları içerir.

- [Renegade Google Sheets Listesi](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

- [ARM Deposu (yerel ARM yazılımları)](https://armrepo.ver.lt/)

- [Haberler ve desteklenen uygulamalar](https://windowsonarm.org/)

#### Tamamlandı!

### USB Host Modunu Açma/Kapama
> [!Warning]
> Güçlendirilmiş bir USB hub kullanıyorsanız, cihazınıza geri dönüşü olmayan bir zarar verebileceği için USB host modunu devre dışı bırakın. Güçlendirilmiş bir USB hub kullanmıyorsanız, USB cihazlarını kullanabilmek için USB host modunu etkinleştirin.

- USB host modunu etkinleştirmek/devre dışı bırakmak için [USB Host Control](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control) uygulamasını çalıştırın ve USB host modunu devre dışı bırakmak/etkinleştirmek istediğinizi onaylayın.
- Eğer USB host modu şu anda etkinse ve USB çalışmıyorsa, önce kapatın, ardından tekrar açın.

#### Tamamlandı!

### Microsoft Office Yükleme
- [Gravesoft'un Office yükleyici sayfasına](https://gravesoft.dev/office_c2r_links) gidin.
- İhtiyacınıza uygun yükleyiciyi indirin. `Online x64` seçeneğini seçtiğinizden emin olun.
- `setup.exe` dosyasını açın ve içinde verilen talimatları takip edin.

#### Tamamlandı!


### Windows / Office Etkinleştirme
- Massgravel'in [buradaki](https://github.com/massgravel/Microsoft-Activation-Scripts) talimatlarını takip edin.

#### Tamamlandı!



### Klavyeyi Yüzer Hale Getirme
> [!WARNING]  
> Bu adımların, Windows'u çalıştıran cihazda yapıldığından emin olun, bilgisayarınızda değil!

- CMD'yi yönetici olarak açın ve şu komutu çalıştırın:
```cmd
reg delete HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Scaling /v MonitorSize
```
- `y` tuşuna basın ve ardından enter tuşuna basın.
- Cihazınızı yeniden başlatın.

##### Tamamlandı!
