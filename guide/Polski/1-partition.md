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

### Przewodnik dotyczący partycjonowania
> There are two methods to partition your device. Please select the method you would like to use below. 

#### Method 1: Manual partitioning 

<details>
  <summary><strong>Click here for method 1</strong></summary> 

#### Odmontuj dane
> Ignore any possible errors and continue
```cmd
adb shell umount /dev/block/by-name/userdata
``` 

#### Resizing the partition table
```cmd
adb shell sgdisk --resize-table 64 /dev/block/sda
```

#### Przygotowanie do partycjonowania
```cmd
adb shell parted /dev/block/sda
``` 

#### Wyświetlanie aktualnej tablicy partycji
> Parted wyświetli listę partycji, **userdata** powinenen być ostatnią partycją na liście.
```cmd
print
``` 

#### Usuwanie userdata
> Zamień **$** na numer partycji **userdata**, który powinien wynosić **32**
```cmd
rm $
``` 

#### Ponowne utworzenie userdata
> Zamień **11.7GB** na poprzednią wartość początkową **userdata**, którą właśnie usunęliśmy (prawdopodobnie jest to 1611MB)
>
> Zastąp **70GB** wartością końcową, jaką chcesz mieć dla **userdata**. In this example your available usable space in Android will be 70GB-11.7Gb = **58.3GB**
```cmd
mkpart userdata ext4 11.7G 70GB
``` 

#### Tworzenie partycji ESP 
> Zamień **70GB** na końcową wartość **userdata**
>
> Zastąp **70.3GB** wartością, której użyłeś wcześniej, dodając do niej **0.3GB**
```cmd
mkpart esp fat32 70GB 70.3GB
``` 

#### Tworzenie partycji Windows
> Zastąp **70.3GB** wartością końcową **esp**
```cmd
mkpart win ntfs 70.3GB -0MB
``` 

#### Tworzenie bootowalnego ESP
> Użyj `print`, aby zobaczyć wszystkie partycje. Zamień "$" na numer partycji ESP, który powinien wynosić **33**
```cmd
set $ esp on
``` 

#### Wyjdź z parted
```cmd
quit
``` 

### Formatowanie danych
- Sformatuj wszystkie dane w TWRP, w przeciwnym razie Android nie uruchomi się.
- (Idź do Wyczyść > Formatuj dane > wpisz yes) 

#### Sprawdź, czy Android nadal się uruchamia
- Po prostu uruchom ponownie telefon i sprawdź, czy Android nadal działa 

### Formatting Windows and ESP drives
> Reboot into the modded recovery, then run the below two commands
```cmd
adb shell mkfs.ntfs -f /dev/block/by-name/win -L WINVAYU
``` 

```cmd
adb shell mkfs.fat -F32 -s1 /dev/block/by-name/esp -n ESPVAYU
``` 

</details> 

#### Method 2: Automatic partitioning 

<details>
  <summary><strong>Click here for method 2</strong></summary>

### Uruchom skrypt partycjonowania
> Zastąp **$** ilością miejsca, jaką ma mieć system Windows (nie dodawaj GB, po prostu wpisz liczbę)
> 
> Jeśli poprosi Cię o ponowne uruchomienie, zrób to
```cmd
adb shell partition $
```

#### Sprawdź, czy Android nadal się uruchamia
- Po prostu uruchom ponownie telefon i sprawdź, czy Android nadal działa

</details>

## [Następny krok: Rootowanie telefonu](2-root.md)




















