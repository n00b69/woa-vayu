<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Windows na POCO X3 Pro

## Dezinstalacja

### Dlaczego jest to potrzebne?
Jeśli chcesz odinstalować system Windows, używa się tego zamiast ręcznego usuwania partycji, aby uniknąć błędów ludzkich + napisania całego dedykowanego przewodnika na temat samego odinstalowywania.

Jeśli chcesz ponownie zablokować bootloader, musisz mieć domyślną tablicę partycji.

### Wymagania
- [ADB i Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [gpt_both0.bin](https://github.com/n00b69/woa-vayu/releases/download/Files/gpt_both0.bin)

### Instrukcje odinstalowania
> [!Important]
> Istnieje bardzo małe prawdopodobieństwo, że ten przewodnik nie zadziała, jeśli tablica partycji jest całkowicie popieprzona. Jeśli później nie będziesz mógł uruchomić systemu odzyskiwania/Androida, będziesz musiał ponownie sflashować urządzenie za pomocą EDL.

Poradnik dotyczący korzystania z EDL znajdziesz [tutaj](edl.md).

#### Uruchom komputer w trybie fastboot
> Przytrzymaj przycisk zmniejszania głośności + przycisk zasilania, gdy telefon jest wyłączony, lub uruchom następujące polecenie podczas uruchamiania
```cmd
adb reboot bootloader
```

#### Przywróć GPT
> Zastąp ```ścieżka\do\gpt_both0.bin``` ścieżką do pliku gpt_both0.bin
```cmd
fastboot flash partition:0 ścieżka\do\gpt_both0.bin
```

#### Usuń dane użytkownika, aby uniknąć pętli rozruchowej i przywrócić rozmiar FS
```cmd
fastboot -w
```
> [!Note]
> Jeśli wymazanie danych użytkownika nie powiedzie się, uruchom ponownie komputer w celu odzyskania i zamiast tego wyczyść wszystkie dane

## Skończone!













