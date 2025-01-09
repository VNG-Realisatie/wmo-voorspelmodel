---
layout: test-side-nav
title: Wmo Voorspelmodel Documentatie
---
# Documentatie voor Functies

## Bestand: cbs_data.R

### Functie: haal_cbs_data_op

```
Haalt data op van lokale cache of rechtstreeks van CBS.

Deze functie controleert of er gegevens beschikbaar zijn in de lokale cache.
Als de cache ingeschakeld is en gegevens beschikbaar zijn, worden deze samengevoegd.
Als de cache leeg is, haalt de functie data rechtstreeks op van het CBS.

@return Een DataFrame met gecombineerde data of data opgehaald van het CBS.
@examples
data <- haal_cbs_data_op()
@export
```
### Functie: sla_data_lokaal_op

```
Slaat een DataFrame lokaal op als CSV-bestand.

Deze functie slaat een gegeven DataFrame op als CSV-bestand op een specifieke locatie
op het bestandssysteem. De locatie wordt bepaald door een pad in de configuratie.
Als de directory nog niet bestaat, wordt deze aangemaakt. Bij fouten tijdens het opslaan
wordt een foutmelding getoond.

@param df DataFrame die opgeslagen moet worden.
@param bestands_naam De naam van het bestand waaronder de data opgeslagen moet worden.
@return Geen expliciete return waarde, output is een zij-effect: een bestand op disk.
@examples
sla_data_lokaal_op(mijnDataFrame, "mijnData.csv")
@export
```
### Functie: haal_data_van_cbs_online

```
Haalt gegevens op van CBS en slaat deze lokaal op indien geconfigureerd.

Deze functie haalt data op van het CBS voor elk jaar in een opgegeven reeks.
De gebruiker moet een specifieke 'cbs_tabel' naam opgeven. Als deze tabelnaam niet
wordt opgegeven of leeg is, stopt de functie met een foutmelding. Voor elk jaar
wordt gecontroleerd of de data beschikbaar is. Zo niet, stopt de functie met een
foutmelding. De data voor alle jaren wordt gecombineerd en eventueel lokaal
opgeslagen als dit zo is geconfigureerd.

@param cbs_tabel De naam van de CBS-tabel waaruit gegevens opgehaald moeten worden.
@return Een DataFrame met gecombineerde data van alle opgevraagde jaren.
@examples
haal_data_van_cbs_online("kwb")
@export
```
