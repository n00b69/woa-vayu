<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Windows na POCO X3 Pro

## Konfiguracja dualboot

### Wymagania
- [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)

- [Obraz UEFI](https://github.com/n00b69/woa-vayu/releases/tag/UEFI)

- [WOA Helper](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA)

## Przewodnik Dualboot
W tym przewodniku założono, że jesteś zrootowany, jeśli tak nie jest, postępuj zgodnie z [tym przewodnikiem](root.md)

### Konfiguracja – Android
- Pobierz i zainstaluj aplikację **WOA Helper**, a następnie otwórz ją i przyznaj uprawnienia root.
- Pobierz **obraz UEFI** i umieść go w folderze o nazwie `UEFI` w pamięci wewnętrznej.
- Otwórz aplikację WOA Helper i użyj **STA CREATOR** w **WOA TOOLBOX**.
> [!Important]
> Jeśli `/sdcard/Windows` jest pusty, Twój ROM nie obsługuje montowania i będziesz musiał wykonać kopię zapasową boot.img w aplikacji, a następnie skopiować ją ręcznie do systemu Windows po uruchomieniu (na przykład przesyłając go gdzieś a następnie pobranie go podczas uruchamiania systemu Windows). To samo dotyczy plików StA, które są również generowane w pamięci wewnętrznej.
>
> Zrób to samo, jeśli folder jest tylko do odczytu.
- Naciśnij przycisk **SZYBKI START DO WINDOWS**.

### Konfiguracja — Windows
> [!Tip]
> Jeśli to będzie pierwszy raz, gdy uruchamiasz Windowsa i chcesz pominąć logowanie do konta Microsoft, wciśnij przycisk **Nie mam Internetu** w etapie WiFi, a gdy zapytany, wciśnij **Kontynuuj z ograniczoną konfiguracją**.
- Navigate to `C:\sta` and create a shortcut of **sta.exe** to your desktop, if one isn't already present

#### Uruchamianie systemu Android
- Uruchom nowy skrót na pulpicie (możesz także przypiąć go do menu startowego/paska zadań, aby ułatwić dostęp)

#### Uruchamianie systemu Windows
- Naciśnij **SZYBKI START DO WINDOWS** w aplikacji lub użyj nowo utworzonego przełącznika w panelu szybkich ustawień
  
## Skończone!
















