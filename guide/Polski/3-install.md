<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Windows na POCO X3 Pro

## Instalacja Windowsa

### Wymagania
- [Zmodyfikowane recovery](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)

- [Windows na ARM](https://worproject.com/esd)
  
- [Sterowniki](https://github.com/n00b69/woa-vayu/releases/tag/Drivers)

- [Obraz UEFI](https://github.com/n00b69/woa-vayu/releases/tag/UEFI)

### Uruchomienie recovery
> Jeśli recovery zostało zastąpione recovery domyślnym, sflashuj go ponownie za pomocą
```cmd
fastboot flash recovery ścieżka\do\moddedtwrp.img reboot recovery
```

#### Włączanie trybu pamięci masowej
> Jeżeli zostałeś poproszony, aby wykonać polecenie jeszcze raz, zrób to
```cmd
adb shell msc
```

### Diskpart
> [!WARNING]
> NIE USUWAJ ŻADNYCH PARTYCJI W DISKPART!!!! TO USUNIE CAŁĄ ZAWARTOŚĆ PAMIĘCI!!!! OZNACZA TO, ŻE TWOJE URZĄDZENIE ZOSTANIE TRWALE USZKODZONE BEZ ROZWIĄZANIA! (z wyjątkiem wysłania go do Xiaomi lub flashowania go za pomocą EDL)
```cmd
diskpart
```

#### Wybieranie partycji Windows
> Wpisz `list Volume`, aby ją znaleźć, zamień `$` na rzeczywistą liczbę **WINVAYU**
```diskpart
select volume $
```

#### Dodanie litery do systemu Windows
```cmd
assign letter x
```

#### Wybieranie partycji ESP
> Użyj `list Volume`, aby go znaleźć, zamień `$` na rzeczywistą liczbę **ESPVAYU**
```diskpart
select volume $
```

#### Dodanie literę do ESP
```cmd
assign letter y
```

#### Wyjście z Diskpart
```cmd
exit
```

### Instalowanie Windowsa
> Zamień `ścieżka\do\install.esd` na rzeczywistą ścieżkę do pliku install.esd (może on również nosić nazwę install.wim lub 22631.2861.XXXXXXX.esd)
```cmd
dism /apply-image /ImageFile:ścieżka\do\install.esd /index:6 /ApplyDir:X:\
```

> Jeśli pojawi się komunikat `Błąd 87`, sprawdź indeks obrazu za pomocą polecenia `dism /get-imageinfo /ImageFile:ścieżka\do\install.esd`, a następnie zastąp `index:6` rzeczywistym numerem indeksu systemu **Windows 11 Pro** w Twoim obrazie

### Kopiowanie obrazu rozruchu do Windowsa
- Zaznacz i upuść **rooted_boot.img** z poprzedniego kroku do **WINVAYU** w eksploratorze plików, a następnie zmień mu nazwę na **boot.img**.

### Instalowanie sterowników
- Wypakuj archiwum ze sterownikami, a następnie otwórz plik `OfflineUpdater.cmd` (jeśli pojawi się błąd, otwórz `OfflineUpdaterFix.cmd`)
 
> Jeśli poprosi Cię o podanie litery, wpisz literę dysku **WINVAYU** (powinna to być litera **X**), a następnie naciśnij enter.

#### Tworzenie plików bootloadera systemu Windows
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### Remove the drive letter for ESP
> If this does not work, ignore it and skip to the next command. This phantom drive will disappear the next time you reboot your PC.
```cmd
mountvol y: /d
```

### Uruchamianie ponownie do Androida
Telefon powinien uruchomić się ponownie sam po +- 10 minutach czekania, po których uruchomi się Android, aby wykonać ostatni krok.

## [Ostatni krok: Konfiguracja dualboot](4-dualboot.md)

















