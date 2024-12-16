<img align="right" src="https://github.com/n00b69/woa-vayu/blob/main/vayu.png" width="350" alt="Windows 11 running on a Poco X3 Pro">

# Windows na POCO X3 Pro

## Dodatkowe materiały
> Poniżej znajdziesz listę usprawnień i materiałów dla systemu Windows na urządzeniu ARM

### Lista obsługiwanych aplikacji/gier
Nie jest to w żadnym wypadku pełna lista, zawiera po prostu listę aplikacji/gier przetestowanych przez społeczność
[Link można znaleźć tutaj](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

Listę dedykowanego oprogramowania ARM znajdziesz także [pod tym linkiem](https://armrepo.ver.lt/)

#### Skończone!

### Ukryj dysk D (partycję modemu)
> [!WARNING]
> Jest to zalecane, ponieważ ten dysk nie powinien być modyfikowany, gdyż niektóre aplikacje mogą próbować na nim zapisywać dane

- Otwórz okno wiersza poleceń i uruchom ```diskpart```
- Uruchom ```lista woluminów```, aby zobaczyć wszystkie dostępne woluminy
- Wybierz dysk oznaczony literą D za pomocą ```wybierz wolumin $```, zastępując „$” numerem woluminu
- Usuń literę za pomocą ```usuń literę d```
- Wyjdź z dysku za pomocą ```exit```

#### Skończone!

### Przełączanie trybu hosta USB
> [!warning]
> Wyłącz tryb hosta USB, jeśli używasz koncentratora USB Poweref, ponieważ może to nieodwracalnie uszkodzić urządzenie. Jeśli nie korzystasz z zasilanego koncentratora USB, włącz tryb hosta USB, w przeciwnym razie nie będziesz mógł używać żadnych urządzeń USB.

Uruchom [Kontrola hosta USB](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control), aby włączyć/wyłączyć tryb hosta USB, potwierdź, że chcesz wyłączyć/ włącz tryb hosta USB, a następnie potwierdź ponowne uruchomienie

#### Skończone!

### Zainstaluj pakiet Microsoft Office/Microsoft 365
- Pobierz ten [plik ISO](https://mega.nz/file/hjAiSL4T#G7kOKpsUFpyL2UW9RQmY2e96urcQW5xZKdc7ciaNOy8) na telefon
- Kliknij prawym przyciskiem myszy plik ISO i wybierz Zamontuj, aby otworzyć go w Eksploratorze
- Kliknij dwukrotnie ```Office Tool Plus.exe```, aby uruchomić kreatora instalacji
- W wyświetlonym oknie kliknij „Tak”.
- Poczekaj na zakończenie instalacji

#### Skończone!

### Aktywuj system Windows/Office
Postępuj zgodnie z instrukcjami Massgravel [tutaj] (https://github.com/massgravel/Microsoft-Activation-Scripts)

#### Skończone!




















