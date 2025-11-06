# Prediction Challenge

## Data Mining - Doctorado UDP 2025

![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://raw.githubusercontent.com/Doctorado-UDP/data-mining-2025/refs/heads/main/prediction_challenge/badges/active.svg) ![License](https://raw.githubusercontent.com/Doctorado-UDP/data-mining-2025/refs/heads/main/prediction_challenge/badges/mit.svg)

## Instrucciones

## Leaderboard actualizado

Participant | Date | Submission | Model | Accuracy | Precision | Recall | F1-Score
--- | :-: | :-: | :-: | :-: | :-: | :-: | :-: 
Baseline | 2025-11-06 | 1 | RF100 |  |  | | 

## Fórmula para la calificación

$$y = \alpha + (X - 0.001) \times 6.258$$ 

Donde $y$ es la nota de 1.0 a 7.0; $\alpha$ = 1.0; $X$ es **el mejor F1-Score obtenido** durante el challenge.

De esta forma, F1-Score = 0.800 $\sim$ 6.0; 0.900 \$\sim$ 6.6; y la nota máxima se alcanzaría con 0.960.

> [!IMPORTANT]
> **Esta forma es la misma utilizada el año pasado, sin embargo, es provisional ya que la capacidad de predicción del modelo base es menor. Por tanto, puede ajustarse pronto para beneficiar a los participantes.**

## Codebook

Schaffner, S., &  Thiel, P. (2024). FDZ Data description: Real-Estate Data for Germany Campus Files (RWI-GEO-RED Panel and RWI-GEO-RED Cross v5) - Advertisements on the Internet Platform ImmobilienScout24 for teaching purposes. Codebook.

- **obid**. Housing unit identifier. Each property is uniquely identified by an artificial ID number. IDs are propertyspecific and do not change over time even if the object is temporarily withdrawn from the pool of advised real estates and offered again at a later time. Some IDs may be re-used over time when agents re-use previous advertisements.
- **plz**. Postcode. It gives the postal code of the city the housing unit is located in.
- **mieteinnahmenpromonat**. Rental income per month in EUR. For housing units offered for sale, this indicates the rent income if the housing unit is rented out. This is on a monthly basis and in EUR rounded to two decimal digits.
- **heizkosten**. Heating costs. This indicates the monthly heating costs in EUR and is rounded to two decimal digits.
- **baujahr**. Year that housing unit was built. Year in which the housing unit was built. Observations that lie in the future are not necessarily faulty entries, potentially indicating that an housing unit is still under construction.
- letzte_modernisierung
- wohnflaeche
- grundstuecksflaeche
- nutzflaeche
- zimmeranzahl
- nebenraeume
- schlafzimmer
- badezimmer
- parkplatzpreis
- ev_kennwert
- laufzeittage
- hits
- click_schnellkontakte
- click_customer
- click_weitersagen
- click_url
- liste_show
- liste_match
- immobilientyp
- denkmalobjekt
- einbaukueche
- einliegerwohnung
- ev_wwenthalten
- ferienhaus
- foerderung
- gaestewc
- garten
- kaufvermietet
- keller
- parkplatz
- rollstuhlgerecht
- bauphase
- ausstattung
- energieeffizienzklasse
- energieausweistyp
- haustier_erlaubt
- heizungsart
- kategorie_Haus
- objektzustand
- ergg_1km
- blid
- gid2019
- kid2019
- bef1
- bef2
- bef10
- bef9
- bef8
- bef7
- bef6
- bef5
- bef4
- bef3
- anbieter
- duplicateid
- spell
- hits_gen
- click_schnellkontakte_gen
- click_weitersagen_gen
- click_url_gen
- liste_show_gen
- liste_match_gen
- adat
- edat
- price_sqm
