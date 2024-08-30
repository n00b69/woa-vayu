<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Windows na POCO X3 Pro

## Tworzenie partycji

### Wymagania
- Odblokowany bootloader

- [ADB i Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [Zmodyfikowane recovery](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)

### Uwagi
> [!Warning]  
> 
> NIE URUCHAMIAJ PONOWNIE TELEFONU! Jeśli uważasz, że popełniłeś błąd, poproś o pomoc na [Telegramie](https://t.me/woahelperchat.
> 
> Nie uruchamiaj wszystkich poleceń na raz, wykonuj je po kolei!

### Otwieranie CMD jako administrator
> Pobierz **platform-tools** i wypakuj gdzieś folder, a następnie otwórz CMD jako **administrator**.
>
> Zaleca się pozostawienie tego okna otwartego i korzystanie z niego przez cały przewodnik.
> 
> Zastąp `ścieżka\do\platform-tools` rzeczywistą ścieżką do folderu platform-tools, na przykład **C:\platform-tools**.
```cmd
cd ścieżka\do\platform-tools
```

#### Instalacja OFOX
> Otwórz okno CMD w folderze platform-tools, a następnie (gdy telefon jest w trybie fastboot) wpisz
```cmd
fastboot flash recovery ścieżka\do\moddedtwrp.img reboot recovery
```

#### Tworzenie kopii zapasowych obrazu rozruchu
> Spowoduje to utworzenie kopii zapasowej obecnego obrazu rozruchu w bieżącej ścieżce
```cmd
adb pull /dev/block/by-name/boot boot.img
```

### Uruchom skrypt partycjonowania
> Zastąp **$** ilością miejsca, jaką ma mieć system Windows (nie dodawaj GB, po prostu wpisz liczbę)
> 
> Jeśli poprosi Cię o ponowne uruchomienie, zrób to
```cmd
adb shell partition $
```

#### Sprawdź, czy Android nadal się uruchamia
- Po prostu uruchom ponownie telefon i sprawdź, czy Android nadal działa

## [Następny krok: Rootowanie telefonu](2-root.md)




















