<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Uruchamianie Windows na POCO X3 Pro

## Wymagania wstępne
- Zrootowany POCO X3 Pro

- [Vayu WinInstaller]

- [Obraz Windows on ARM](https://worproject.com/esd)

- [Sterowniki](https://github.com/n00b69/woa-vayu/releases/tag/Drivers)

- [Modyfikowany TWRP](https://github.com/n00b69/woa-vayu/releases/tag/Recovery)

- [Aplikacja WOA Helper](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA)

### Uwagi
> [!Warning]
> Wszystkie dane zostaną skasowane! Zapewnij sobie kopie zapasowe, jeśli potrzebne.
> 
> NIE RESTARTUJ TELEFONU, jeśli myślisz, że popełnilesz błąd. Skorzystaj z pomocy w [czacie Telegram](https://t.me/woahelperchat).
> 
> Nie uruchamiaj tych poleceń jednocześnie, wykonywaj je po kolei!

### Pobieranie i wypakowywanie sterownika
- Zastąp `scp` i `adb` odpowiednimi poleceniami dla Twojego systemu operacyjnego.
- Skopiuj plik `drivers.zip` do katalogu `adb`/`scp` na Twoim telefonie.
- Wypakuj plik `drivers.zip` w katalogu `adb`/`scp`.
```cmd
adb push drivers.zip /data/adb
adb shell su -c "unzip -o /data/adb/drivers.zip -d /data/adb"
```

### Uruchomienie skryptu do partycjonowania
- Wklej to polecenie w terminalu TWRP i podaj ilość pamięci, którą chcesz przypisać do Windows (liczba w GB).
```cmd
partition $
```

#### Sprawdzenie, czy Android nadal uruchamia się
- Ponownie uruchom telefon i sprawdź, czy Android działa poprawnie.

### Przygotowywanie plików wymaganych
- Pobierz [sterowniki](https://github.com/n00b69/woa-vayu/releases/tag/Drivers) i [obraz Windows on ARM](https://worproject.com/esd).
- Zainstaluj [aplikację WOA Helper](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA) i udziel jej uprawnień root.

### Uruchomienie WinInstaller
- W TWRP, wejdź do **Zainstaluj** i znajdź **WinInstaller.zip**, a następnie zainstaluj go.
- Poczekaj, aż zostaną ukończone wszystkie operacje i uruchomi się instalator Windows.
> [!Tip]
> Jeśli chcesz pominąć logowanie do konta Microsoft, kliknij **Nie mam internetu** na stronie Wi-Fi, a potem **Kontynuuj z ograniczonym ustawieniem**.

#### Uruchamianie systemu Android
- Uruchom skrypt **android** na pulpicie Windowsa.

#### Uruchamianie Windows
- W aplikacji WOA Helper kliknij **QUICKBOOT TO WINDOWS**, lub użyj stworzonego w pasku szybkich ustawień przełącznika.

## Gotowe!

























