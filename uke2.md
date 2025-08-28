# Uke 2 - API, JSON og Flask

## GET-requests i Python

```python
import requests

repsons = requests.get("https://google.com")

print(f"Status kode: {respons.status_code}")
print(f"Respons-tekst: {respons.text}")
```

## Hente JSON-data

```python
import requests

respons = requests.get("https://api.chucknorris.io/jokes/random")
print(f"Status kode: {respons.status_code}")
data = respons.json()
print(data)
```


## API: [data.stortinget.no](https://data.stortinget.no)

- Regjering: [https://data.stortinget.no/eksport/regjering?format=json](https://data.stortinget.no/eksport/regjering?format=json)
- Dagens representanter: [https://data.stortinget.no/eksport/dagensrepresentanter?format=json](https://data.stortinget.no/eksport/dagensrepresentanter?format=json)
- Bilder: [https://data.stortinget.no/eksport/personbilde?personid=JGS&storrelse=middels](https://data.stortinget.no/eksport/personbilde?personid=JGS&storrelse=middels)

## Oppgaver

1. Lag et Python-program som henter listen med representanter fra Stortingets API og printer listen i terminalen.
2. Utvid programmet slik at det går gjennom listen med politikere, og printer info om hver politiker på en strukturert måte, eks: FORNAVN ETTERNAVN (PARTI)
3. Bruk Flask, og lag en nettside som viser en oversikt over alle politikerene
4. Legg til knapper eller lenker for sortering på partier
