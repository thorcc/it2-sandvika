# Uke 1 – Terminalen og Python

## 1 Terminalen

### 1.0 Anbefalt terminal

- Mac: [iTerm2](https://iterm2.com/)
- Windows: [Windows terminal](https://apps.microsoft.com/detail/9n0dx20hk701?hl=en-US&gl=US)

### 1.1 Pakkebehandlere (package managers)

En **pakkebehandler** er et verktøy i terminalen som gjør det enkelt å installere programmer.  
I stedet for å laste ned fra en nettside og trykke "Neste, Neste, Fullfør", kan vi skrive én kommando.  

#### Installere pakkebehandlere
- **Mac:** [Homebrew](https://brew.sh/)  
- **Windows:** [Winget](https://learn.microsoft.com/en-us/windows/package-manager/winget) (allerede installert på Windows 10/11 – du trenger ikke gjøre noe).  

#### Eksempler på bruk
- **Mac (brew):**  
  - `brew search spotify` → søk etter program  
  - `brew install spotify` → installer program  
- **Windows (winget):**  
  - `winget search spotify` → søk etter program og finn ID  
  - `winget install Spotify.spotify` → installer program med ID  

Disse kan brukes til **utviklingsverktøy også**, f.eks. `brew install git` eller `winget install git`.  

---

### 1.2 Fancy terminal

Standard-terminalen fungerer helt fint, men det finnes verktøy som gjør den både penere og mer nyttig:  
- **Mac:** [`oh-my-zsh`](https://ohmyz.sh/)  
- **Windows:** [`oh-my-posh`](https://ohmyposh.dev/docs/installation/windows)  

Fordeler: temaer, bedre oversikt, og nyttige snarveier.  

---

### 1.3 Nyttige terminal-kommandoer

| Kommando       | Hva den gjør                 |
| -------------- | ---------------------------- |
| `cd MAPPENAVN` | Gå inn i en mappe            |
| `pwd`          | Vis hvilken mappe du er i nå |
| `ls`           | Vis alle filer i mappen      |
| `mkdir NAVN`   | Lag en ny mappe              |
| `rm FILNAVN`   | Slett en fil                 |
| `clear`        | Tøm skjermen i terminalen    |
| `code .`       | Åpne denne mappen i VS Code  |

---

## 2 Python


### 2.1 Installere Python

Ikke bruk **brew** eller **winget** til å installere Python – de versjonene kan skape problemer.  

- Last ned fra [python.org/downloads](https://www.python.org/downloads/)  
- Installer på vanlig måte.  

Etterpå:  
- **Mac:** dobbeltklikk `Install Certificates` i Python-mappen.  
- **Windows:** husk å huke av for *"Add to PATH"* under installasjonen.  

💡 Test installasjonen:  
- Mac: `python3 --version`  
- Windows: `python --version`  

---

### 2.2 Virtuelle miljøer (venv)

Når vi jobber med prosjekter, trenger vi ofte ekstra Python-pakker.  
For å unngå kaos (og feil versjoner), lager vi et **virtuelt miljø**. Da blir pakkene installert bare i prosjektmappen, ikke på hele PC-en.  

---

#### Opprette et virtuelt miljø
1. Gå inn i prosjektmappen med `cd` (eller åpne mappen i VS Code).  
2. Kjør:  
   - Mac: `python3 -m venv venv`  
   - Windows: `python -m venv venv`  

Her betyr:  
- `-m venv` → bruk Pythons innebygde verktøy for virtuelle miljøer  
- `venv` → navnet på mappen (du kan kalle den noe annet, men `venv` er standard)  

---

#### Starte et virtuelt miljø
- **Mac:** `source venv/bin/activate`  
- **Windows:** `venv\Scripts\Activate.ps1`  

 Når miljøet er aktivt, ser du `(venv)` foran linja i terminalen.  
Du kan skru det av med `deactivate`.  

---

#### Installere pakker
- `pip install PAKKENAVN`  

Eksempel:  
- `pip install requests`  

---

#### Requirements-filen
En **requirements.txt** er en liste over alle pakkene prosjektet trenger.  

- Lag filen: `pip freeze > requirements.txt`  
- Installer alt fra filen: `pip install -r requirements.txt`  

Dette er spesielt nyttig når du deler kode – da kan andre installere alt med én kommando.  
