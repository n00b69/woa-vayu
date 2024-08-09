<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Windows na POCO X3 Pro

## Rootowanie telefonu

### Wymagania
- [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)

- [ADB i Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Skopiowanie obecnego obrazu rozruchu do Androida
- Podłącz telefon do komputera (z włączonym debugowaniem USB)
- W oknie na telefonie zezwól na dostęp do plików z poziomu komputera. Jeśli okno nie wyskoczy, przejdź do panelu powiadomień i kliknij na powiadomienie odnośnie USB, a następnie zmień rodzaj połączenia na **przesyłanie plików**.
- Skopiuj plik **boot.img** z folderu **platform-tools** do pamięci wewnętrznej telefonu.

#### Łatanie obrazu rozruchu
- Pobierz i zainstaluj **Magisk**, następnie go otwórz.
- Kliknij **Instaluj** > **wybierz i załataj plik** i wybierz **boot.img**, który przed chwilą skopiowałeś.
- Gdy łatanie się zakończy, znajdź **magisk_patched-27000_XXXX.img** w folderze **Downloads** i skopiuj go do folderu **platform-tools** na komputerze.

### Uruchomienie ponownie do trybu fastboot
```cmd
adb reboot bootloader
```

#### Wgrywanie zrootowanego obrazu rozruchu
> zmień `ścieżka\do\magisk_patched.img` na faktyczną scieżkę do obrazu.
```cmd
fastboot flash boot ścieżka\do\magisk_patched.img
```

### Uruchom ponownie do Androida
```cmd
fastboot reboot
```

#### Zakończenie instalacji
- Otwórz aplikację **Magisk** ponownie.
- Postępuj zgodnie z instrukcjami na ekranie. Telefon powinien się uruchomić ponownie po kilku sekundach.

### Kopiowanie zrootowanego obrazu rozruchu
> Gdy już twój telefon się włączy

- A superuser request for Shell might appear on your phone's screen. If it does, grant it access.
```cmd
adb shell "su -c cp dev/block/by-name/boot /sdcard/root.img" & adb pull /sdcard/root.img
```

## [Następny krok: Instalacja Windowsa](3-install.md)













































