# Housing Prices Prediction Challenge

## Data Mining - Doctorado UDP 2025

![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://raw.githubusercontent.com/Doctorado-UDP/data-mining-2025/refs/heads/main/prediction_challenge/badges/active.svg) ![License](https://raw.githubusercontent.com/Doctorado-UDP/data-mining-2025/refs/heads/main/prediction_challenge/badges/mit.svg)

## Instrucciones

En la carpeta [prediction_challenge/data](https://github.com/Doctorado-UDP/data-mining-2025/tree/main/prediction_challenge/data) se encuentran **cinco conjuntos de datos** correspondientes a particiones de una base de datos que abarca las 15 ciudades más grandes de Alemania (i.e., Berlin, Hamburg, Munich, Cologne, Frankfurt, Stuttgart, Düsseldorf, Leipzig, Dortmund, Essen, Bremen, Dresden, Hannover, Nuremberg y Duisburg). Todas tienen al menos 500K habitantes. La base de datos presenta, para cada ciudad, una muestra amplia balanceada por año del número de anuncios. El número de observaciones varía entre 1K por ciudad y año en la muestra de casas en venta y hasta 50K por año en Berlin y Leipzig y en el caso de los departamentos en renta. Se utilizarán los **anuncios de casas en venta** (*n* = 390.296) para predecir la variable **price_sqm** (i.e., Price per sqm in EUR: Calculated price per square meter by price and size of house/size of apartment). El conjunto de datos se dividió en una proporción de 70/15/15 para crear **training set**, **validation set** y **test set**. 

Cada uno de estos conjuntos se dividió en dos para contener, de forma separada, los predictores y la variable dependiente. El **conjunto reservado**, no disponible en GitHub, que se utilizará para calcular las métricas del leaderboard, contiene los valores reales (*ground-truth*) de la variable dependiente del **test set**.

> [!CAUTION]
> Para no superar los límites de LFS, el conjunto de predictores del training set se dividió en tres conjuntos.

**Los participantes deberán:**

1. Utilizar [X_train_part1.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part_1.csv), [X_train_part2.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part_2.csv), [X_train_part3.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part_3.csv) e [y_train.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/y_train.csv) para entrenar sus modelos y [X_val.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_val.csv) e [y_val.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/y_val.csv) para validarlos.
2. Obtener las etiquetas predichas utilizando [X_test.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_test.csv) y subirlas a la carpeta [prediction_challenge/submissions](https://github.com/Doctorado-UDP/data-mining-2025/tree/main/prediction_challenge/submissions)
3. Pueden utilizar como script base el [código de ejemplo](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/baseline_model.ipynb) y preparar modelos afinados.
4. El siguiente [código](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/submissions_eval.ipynb) será utilizado, por el profesor, para calcular el [**leaderboard**](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/leaderboard.csv).
5. El leaderboard se calculará diariamente, excepto los domingos, hasta que cierre el challenge.

**Formato de envío (también disponible en el código de ejemplo):**

Es importante que los participantes completen la metadata en el código para el envío y verifiquen el formato del archivo con predicciones (**submission_Nombre_Modelo_N-envío.csv**).

* participant = "Baseline" - Nombre del participante, solo el primer nombre.
* model_name = "RF100" - Nombre del modelo: Naive Bayes (NB), Support Vector Machine (SVM), Random Forest (RFX) donde X es el número de árboles, XGBoost, u otro.
* submission_number = "1" - El número de envío, mantener las comillas, por favor.

> [!IMPORTANT]
> **Durante el challenge NO se subirán los códigos de cada envío, sin embargo, luego se revisarán los scripts de los mejores modelos.**

**Cuestiones logísticas:**

1. Se puede realizar máximo **un envío por día**.
2. Cada modelo tiene un límite de **cinco predictores**.
3. Los participantes pueden crear índices, recodificar y transformar predictores utilizando los datos de entrenamiento y probar distintos hiperparámetros y modelos. 
4. Los participantes **pueden** crear nuevas variables a partir de información que no exista en el conjunto de datos de entrenamiento.
5. El challenge termina el **viernes 21 de noviembre de 2024 a las 23.59 horas** de Santiago de Chile.

> [!CAUTION]
> **El año pasado estaba prohibido crear nuevas variables con información externa del conjunto de datos de entrenamiento, sin embargo, este año es posible siempre y cuando esa información se incorpore en el paso de predicción final.**

## Leaderboard actualizado

Participant | Date | Submission | Model | Accuracy | Precision | Recall | F1-Score
--- | :-: | :-: | :-: | :-: | :-: | :-: | :-: 
Baseline | 2025-11-06 | 1 | RF100 | 0.287 | 0.283 | 0.287 | 0.267

## Fórmula para la calificación

$$y = \alpha + (X - 0.001) \times 6.258$$ 

Donde $y$ es la nota de 1.0 a 7.0; $\alpha$ = 1.0; $X$ es **el mejor F1-Score obtenido** durante el challenge.

De esta forma, F1-Score = 0.800 $\sim$ 6.0; 0.900 \$\sim$ 6.6; y la nota máxima se alcanzaría con 0.960.

> [!IMPORTANT]
> **Esta fórmula es la misma utilizada el año pasado, sin embargo, es provisional ya que la capacidad de predicción del modelo base es menor. Por tanto, puede ajustarse pronto para beneficiar a los participantes.**

## Codebook

Schaffner, S., &  Thiel, P. (2024). FDZ Data description: Real-Estate Data for Germany Campus Files (RWI-GEO-RED Panel and RWI-GEO-RED Cross v5) - Advertisements on the Internet Platform ImmobilienScout24 for teaching purposes. Codebook.

- **obid**. Housing unit identifier. Each property is uniquely identified by an artificial ID number. IDs are propertyspecific and do not change over time even if the object is temporarily withdrawn from the pool of advised real estates and offered again at a later time. Some IDs may be re-used over time when agents re-use previous advertisements.
- **plz**. Postcode. It gives the postal code of the city the housing unit is located in.
- **mieteinnahmenpromonat**. Rental income per month in EUR. For housing units offered for sale, this indicates the rent income if the housing unit is rented out. This is on a monthly basis and in EUR rounded to two decimal digits.
- **heizkosten**. Heating costs. This indicates the monthly heating costs in EUR and is rounded to two decimal digits.
- **baujahr**. Year that housing unit was built. Year in which the housing unit was built. Observations that lie in the future are not necessarily faulty entries, potentially indicating that an housing unit is still under construction.
- **letzte_modernisierung**. Year of last modernization of housing unit. Indicator for the year of the last modernisation.
- **wohnflaeche**. Living area. Living space in square meters. The precision of entries varies between natural numbers and numbers with two decimal places. If
- **grundstuecksflaeche**. Plot area. This variable indicates the plot area of the housing unit in square meters. Numbers are rounded to two decimal digits.
- **nutzflaeche**. Usable floor space. This indicates the usable floor space in square meters. Numbers are rounded to two decimal digits.
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
