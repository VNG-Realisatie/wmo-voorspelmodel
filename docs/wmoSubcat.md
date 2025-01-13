---

layout: page-with-side-nav

title: Wmo Voorspelmodel Documentatie

---

# Documentatie voor Functies

## Bestand: wmoSubcat.R

### Functie: Download_Wmo_Excel

```
Downloadt een Excel-bestand van een opgegeven URL.

Deze functie controleert of een Excel-bestand al lokaal aanwezig is.
Als het bestand niet aanwezig is, wordt het gedownload van de opgegeven URL.

@param url De URL van het Excel-bestand.
@param file_path Het lokale pad waar het Excel-bestand moet worden opgeslagen.
@return Geen expliciete returnwaarde. Het resultaat is een lokaal bestand.
@examples
Download_Wmo_Excel("https://example.com/wmo.xlsx", "./data/wmo.xlsx")
@export
```
### Functie: Laad_Wmo_Data

```
Laadt en combineert data uit meerdere bladen van een Excel-bestand.

Deze functie leest data uit specifieke bladen van een Excel-bestand
en combineert deze in een enkele DataFrame. Voor elk blad wordt het jaartal
toegevoegd aan de dataset.

@param file_path Het pad naar het Excel-bestand.
@param sheets Een lijst met bladen die moeten worden geladen.
@param jaren Een vector van jaren om de data op te filteren.
@return Een DataFrame met gecombineerde data van de opgegeven bladen.
@examples
data <- Laad_Wmo_Data("./data/wmo.xlsx", c("Tabel 1", "Tabel 2", "Tabel 3"), 2017:2019)
@export
```
### Functie: Voeg_WmoSubcategorieen_toe

```
Voegt Wmo-subcategorieën toe aan een dataset.

Deze functie laadt data met Wmo-subcategorieën uit een Excel-bestand
en voegt deze toe aan een bestaande dataset op gemeenteniveau. Het proces
omvat het downloaden van het Excel-bestand, het combineren van data uit
meerdere bladen, en het koppelen op basis van gwb_code en jaartal.

@return Een DataFrame met de toegevoegde Wmo-subcategorieën.
@examples
wmo_data <- Voeg_WmoSubcategorieen_toe()
@export
```
