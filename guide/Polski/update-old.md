<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Windows na POCO X3 Pro

## Aktualizowanie sterowników

### Wymagania
- [Zmodyfikowane recovery](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)

- [Sterowniki](https://github.com/n00b69/woa-vayu/releases/tag/Drivers)

- [Obraz UEFI](https://github.com/n00b69/woa-vayu/releases/tag/UEFI)

### Uruchom recovery
> Jeśli Twój recovery został zastąpiony recovery domyślnym, sflashuj go ponownie za pomocą
```cmd
fastboot flash recovery ścieżka\do\moddedtwrp.img reboot recovery
```

#### Włączanie trybu pamięci masowej
> Jeżeli zostałeś poproszony, aby wykonać polecenie jeszcze raz, zrób to
```cmd
adb shell msc
```

### Diskpart
```cmd
diskpart
```

#### Wybór partycji Windows
> Użyj `list Volume`, aby go znaleźć, zamień `$` na rzeczywistą liczbę **WINVAYU**
```diskpart
select volume $
```

#### Dodaj literę do systemu Windows
```cmd
assign letter x
```

#### Wyjdź z Diskpart
```cmd
exit
```

### Instalowanie sterowników
> [!Note]
> Ten proces zajmie +- 20 minut. Nie martw się, to normalne.

- Wypakuj archiwum ze sterownikami, a następnie otwórz plik `OfflineUpdater.cmd` (jeśli pojawi się błąd, otwórz `OfflineUpdaterFix.cmd`)
 
> Jeśli poprosi Cię o podanie litery, wpisz literę dysku **WINVAYU** (która powinna być X), a następnie naciśnij enter.

### Uruchom ponownie system Windows
> Pamiętaj, aby zmienić także obraz UEFI w systemie Android, w przeciwnym razie podczas późniejszego uruchamiania systemu Windows może pojawić się „niebieski ekran śmierci” (BSoD).
```cmd
adb reboot
```

## Skończone!















