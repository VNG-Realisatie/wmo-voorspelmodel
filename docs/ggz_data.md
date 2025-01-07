# Documentatie voor Functies

## Bestand: ggz_data.R

### Functie: zoek_ggz_bestand

```
Zoekt het meest recente GGZ-bestand in een opgegeven map.

Deze functie zoekt in de geconfigureerde map naar het meest recente GGZ-bestand
op basis van een specifiek naamgevingspatroon. Als er geen bestanden worden gevonden,
wordt een foutmelding gegeven.

@return De padnaam van het meest recente GGZ-bestand.
@examples
bestand <- zoek_ggz_bestand()
@export
```
### Functie: voeg_GGZ_data_toe

```
Voegt GGZ-data toe aan een dataset en extrapoleert ontbrekende jaren.

Deze functie leest GGZ-data in vanuit het meest recente bestand in een
geconfigureerde map. Vervolgens worden de gegevens getransformeerd naar een 
long-formaat en ontbrekende jaren geëxtrapoleerd met lineaire regressie. De 
verwerkte gegevens worden teruggegeven als een DataFrame.

@return Een DataFrame met GGZ-data, inclusief extrapolatie voor ontbrekende jaren.
@examples
ggz_data <- voeg_GGZ_data_toe()
@export
```
