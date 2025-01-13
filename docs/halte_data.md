---

layout: page-with-side-nav

title: Wmo Voorspelmodel Documentatie

---

# Documentatie voor Functies

## Bestand: halte_data.R

### Functie: haal_halte_data_op

```
Haal halte data op

Deze functie haalt haltegegevens op van een externe CSV-bestand, filtert op haltes die geen locatie_type 1 hebben,
en zet de gegevens om naar een sf-object met de juiste coördinaten en CRS.

@param halte_id Een unieke ID van de halte waarvan de data opgehaald wordt.
@return Een sf-object met halte data.
```
### Functie: haal_grensindeling_op

```
Haal grensindeling op voor een specifiek jaar

Deze functie haalt de grensindeling op voor een gegeven jaar van de CBS WFS-service.
Het downloadt zowel gemeentelijke als wijkgegevens, controleert op fouten, en voegt de resultaten samen.

@param jaar Het jaar waarvoor de grensindeling opgehaald moet worden.
@return Een sf-object met de geometrieën en wijkcodes van de opgehaalde gebieden.
@throws RuntimeError als de gegevens niet kunnen worden opgehaald.
```
### Functie: halte_data_bewerken

```
Bewerken van haltegegevens en berekening van statistieken

Deze functie voegt haltegegevens toe aan de opgehaalde grensindelingen door te berekenen hoeveel haltes zich binnen elk gebied bevinden.
Statistieken zoals de vierkantswortel, logaritme en halte-dichtheden per vierkante meter worden ook berekend. 

@param grenzen Een `sf` object met de grensindelingen.
@param halte_data Een `sf` object met haltegegevens.
@param jaar Het jaar waarvoor de gegevens worden bewerkt.
@return Een data.frame met grensindelingen en bijbehorende halte-statistieken per m².
```
### Functie: ophalen_halte_data

```
Ophalen en bewerken van haltegegevens over meerdere jaren

Deze functie haalt haltegegevens op voor meerdere jaren, zoals gedefinieerd in de configuratie, en bewerkt deze samen met grensindelingen.
De resultaten worden samengevoegd in één dataset per jaar, inclusief statistieken over haltes per vierkante meter.

@return Een data.frame met gecombineerde haltegegevens en grensindelingen over meerdere jaren.
```
