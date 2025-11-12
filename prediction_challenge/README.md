# Housing Prices Prediction Challenge

## Data Mining - Doctorado UDP 2025

![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://raw.githubusercontent.com/Doctorado-UDP/data-mining-2025/refs/heads/main/prediction_challenge/badges/active.svg) ![License](https://raw.githubusercontent.com/Doctorado-UDP/data-mining-2025/refs/heads/main/prediction_challenge/badges/mit.svg)

## Instrucciones

En la carpeta [prediction_challenge/data](https://github.com/Doctorado-UDP/data-mining-2025/tree/main/prediction_challenge/data) se encuentran **cinco conjuntos de datos** correspondientes a particiones de una base de datos que abarca las 15 ciudades más grandes de Alemania (i.e., Berlin, Hamburg, Munich, Cologne, Frankfurt, Stuttgart, Düsseldorf, Leipzig, Dortmund, Essen, Bremen, Dresden, Hannover, Nuremberg y Duisburg). Todas tienen al menos 500K habitantes. La base de datos presenta, para cada ciudad, una muestra amplia balanceada por año del número de anuncios. El número de observaciones varía entre 1K por ciudad y año en la muestra de casas en venta y hasta 50K por año en Berlin y Leipzig y en el caso de los departamentos en renta. Se utilizarán los **anuncios de casas en venta** (*n* = 390.296) para predecir la variable **price_sqm** (Price per sqm in EUR: Calculated price per square meter by price and size of house/size of apartment). El conjunto de datos se dividió en una proporción de 70/15/15 para crear **training set**, **validation set** y **test set**. 

Cada uno de estos conjuntos se dividió en dos para contener, de forma separada, los predictores y la variable dependiente. El **conjunto reservado**, no disponible en GitHub, que se utilizará para calcular las métricas del leaderboard, contiene los valores reales (*ground-truth*) de la variable dependiente del **test set**.

> [!CAUTION]
> Para no superar los límites de LFS, el conjunto de predictores del training set se dividió en tres conjuntos.
> La variable **kaufpreis** (Purchasing price in EUR) fue eliminada de los conjuntos.

**Los participantes deberán:**

1. Utilizar [X_train_part1.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part1.csv), [X_train_part2.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part2.csv), [X_train_part3.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part3.csv) e [y_train.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/y_train.csv) para entrenar sus modelos y [X_val.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_val.csv) e [y_val.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/y_val.csv) para validarlos.
2. Obtener las etiquetas predichas utilizando [X_test.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_test.csv) y subirlas a la carpeta [prediction_challenge/submissions](https://github.com/Doctorado-UDP/data-mining-2025/tree/main/prediction_challenge/submissions)
3. Pueden utilizar como script base el [código de ejemplo](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/baseline_model.ipynb) y preparar modelos afinados.
4. El siguiente [código](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/submissions_eval.ipynb) será utilizado, por el profesor, para calcular el [**leaderboard**](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/leaderboard.csv).
5. El leaderboard se calculará diariamente, excepto los domingos (aunque quizás algunos sí), hasta que se cierre el challenge.

**Formato de envío (también disponible en el código de ejemplo):**

Es importante que los participantes completen la metadata en el código para el envío y verifiquen el formato del archivo con predicciones (**submission_Nombre_Modelo_N-envío.csv**).

* participant = "Baseline" - Nombre del participante, solo el primer nombre.
* model_name = "RF100" - Nombre del modelo: Naive Bayes (NB), Support Vector Machine (SVM), Random Forest (RFX) donde X es el número de árboles, XGBoost, u otro.
* submission_number = "1" - El número de envío, mantener las comillas, por favor.

> [!IMPORTANT]
> **Durante el challenge NO se subirán los códigos de cada envío, sin embargo, luego se revisarán los scripts de los mejores modelos.**

**Cuestiones logísticas:**

1. Se puede realizar máximo **un envío por día** (los adicionales quedarán standby en [prediction_challenge/submissions](https://github.com/Doctorado-UDP/data-mining-2025/tree/main/prediction_challenge/submissions_standby)).
2. Cada modelo tiene un límite de **cinco predictores**.
3. Los participantes pueden crear índices, recodificar y transformar predictores utilizando los datos de entrenamiento y probar distintos hiperparámetros y modelos. 
4. Los participantes **pueden** crear nuevas variables a partir de información que no exista en el conjunto de datos de entrenamiento.
5. El challenge termina el **viernes 21 de noviembre de 2024 a las 23.59 horas** de Santiago de Chile.

> [!CAUTION]
> **El año pasado estaba prohibido crear nuevas variables con información externa del conjunto de datos de entrenamiento, sin embargo, este año es posible siempre y cuando esa información se incorpore en el paso de predicción final.**

## Leaderboard actualizado

Participant | Date | Submission | Model | Accuracy | Precision | Recall | F1-Score
--- | :-: | :-: | :-: | :-: | :-: | :-: | :-: 
Luis | 2025-11-09 | 3 | RF100 | 0.744 | 0.742 | 0.744 | 0.743
Luis | 2025-11-06 | 1 | RF100 | 0.416 | 0.417 | 0.416 | 0.416
Dayana | 2025-11-11 | 2 | RF100 | 0.416 | 0.417 | 0.416 | 0.416
Dayana | 2025-11-12 | 3 | RF100 | 0.349 | 0.348 | 0.349 | 0.348
Baseline | 2025-11-06 | 1 | RF100 | 0.287 | 0.283 | 0.287 | 0.267
Dayana | 2025-11-07 | 1 | RF100 | 0.287 | 0.283 | 0.287 | 0.267
Victor | 2025-11-06 | 1 | RF100 | 0.287 | 0.283 | 0.287 | 0.267
Luis | 2025-11-08 | 2 | RF100 | 0.202 | 0.202 | 0.202 | 0.202

## Nueva fórmula para la calificación

$$y = \alpha + (X - 0.001) \times k$$ 

Donde $y$ es la nota de 1.0 a 7.0; $\alpha$ = 1.0; $X$ es **el mejor F1-Score obtenido** durante el challenge; *k* = 7.320.

De esta forma, F1-Score = 0.700 $\sim$ 6.1; 0.800 \$\sim$ 6.8; y la nota máxima se alcanzaría con 0.821.

> [!IMPORTANT]
> **El valor de *k* el año pasado fue 6.258, sin embargo, este año la capacidad de predicción del modelo base es menor. Por tanto, se ajustó a un valor más sensible a la dificultad del challenge y así no penalizar injustamente la calificación.**

## Consistencia en el preprocesamiento y evitar data leakage

Los participantes deberían aplicar los pasos de recodificación y transformaciones no solo a [X_train_part1.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part1.csv), [X_train_part2.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part2.csv), [X_train_part3.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part3.csv), también a [X_val.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_val.csv) y [X_test.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_test.csv). Esto asegura la consistencia para la validación y los cálculos finales de las métricas.

> [!CAUTION]
> Aunque ciertas transformaciones (e.g, scaling, encoding) deben ser aplicadas a todos los conjuntos, es importante que **los parámetros (e.g., media o SD) sean obtenidas solamente de [X_train_part1.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part1.csv), [X_train_part2.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part2.csv) y [X_train_part3.csv](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/data/X_train_part3.csv)**. 

Esto evita **data leakage** debido a la influencia de los patrones de **validation test** y **test set** sobre el conjunto de datos de entrenamiento, garantizando una mejor generalización del modelo y evitando métricas infladas.

Si una transformación es puramente determinista (e.g., np.log1p), puede aplicarse de forma idéntica a todas las divisiones.

No es necesario imputar la variable objetivo, ya que, como se ha indicado, todos los valores perdidos han sido descartados. Es posible imputar los predictores.

> [!TIP]
> A continuación, hay algunos **ejemplos** de **transformaciones consistentes**, **imputaciones** y **pipeline** para el preprocesamiento.

```python
from sklearn.preprocessing import StandardScaler, OrdinalEncoder
from sklearn.impute import SimpleImputer
from sklearn.pipeline import Pipeline
from sklearn.compose import ColumnTransformer

categorical_columns = ['CategoryFeature']  ## Use for categorical features

## Numerical: median -> scale
numeric_transformer = Pipeline(steps=[
    ('imputer', SimpleImputer(strategy='median')),
    ('scaler', StandardScaler())
])

## Categorical: most_frequent, safe encoding (handles unseen with -1)
categorical_transformer = Pipeline(steps=[
    ('imputer', SimpleImputer(strategy='most_frequent')),
    ('encoder', OrdinalEncoder(handle_unknown='use_encoded_value', unknown_value=-1))
])

## Apply correct transforms per column group (fit on train, transform validation/test)
preprocessor = ColumnTransformer(
    transformers=[
        ('num', numeric_transformer, numeric_columns),
        ('cat', categorical_transformer, categorical_columns)
    ],
    remainder='drop' ## Keep only specified columns
)

X_train_processed = preprocessor.fit_transform(X_train)
X_val_processed = preprocessor.transform(X_val)
X_test_processed = preprocessor.transform(X_test)
```

## Codebook

Schaffner, S., &  Thiel, P. (2024). [FDZ Data description: Real-Estate Data for Germany Campus Files (RWI-GEO-RED Panel and RWI-GEO-RED Cross v5) - Advertisements on the Internet Platform ImmobilienScout24 for teaching purposes](https://github.com/Doctorado-UDP/data-mining-2025/blob/main/prediction_challenge/docs/Datenbeschreibung-Campus-v5.pdf). Codebook.

- **obid**. Housing unit identifier. Each property is uniquely identified by an artificial ID number. IDs are propertyspecific and do not change over time even if the object is temporarily withdrawn from the pool of advised real estates and offered again at a later time. Some IDs may be re-used over time when agents re-use previous advertisements.
- **plz**. Postcode. It gives the postal code of the city the housing unit is located in.
- **mieteinnahmenpromonat**. Rental income per month in EUR. For housing units offered for sale, this indicates the rent income if the housing unit is rented out. This is on a monthly basis and in EUR rounded to two decimal digits.
- **heizkosten**. Heating costs. This indicates the monthly heating costs in EUR and is rounded to two decimal digits.
- **baujahr**. Year that housing unit was built. Year in which the housing unit was built. Observations that lie in the future are not necessarily faulty entries, potentially indicating that an housing unit is still under construction.
- **letzte_modernisierung**. Year of last modernization of housing unit. Indicator for the year of the last modernisation.
- **wohnflaeche**. Living area. Living space in square meters. The precision of entries varies between natural numbers and numbers with two decimal places.
- **grundstuecksflaeche**. Plot area. This variable indicates the plot area of the housing unit in square meters. Numbers are rounded to two decimal digits.
- **nutzflaeche**. Usable floor space. This indicates the usable floor space in square meters. Numbers are rounded to two decimal digits.
- **zimmeranzahl**. Number of rooms. Number of rooms, excluding kitchen, bath or corridors. In several cases, “zimmeranzahl” is not a natural number, which is not necessarily due to a faulty entry. In Germany there is the concept of half rooms (i.e., between 6 and 10 square meters).
- **nebenraeume**. Number of ancillary rooms.
- **schlafzimmer**. Number of bedrooms.
- **badezimmer**. Number of bathrooms.
- **parkplatzpreis**. Price of parking space in EUR.
- **ev_kennwert**. Energy consumption per year and square meter (kWh).
- **laufzeittage**. Days of availability of ad. This variable indicates the number of days the respective advertisement has been online.
- **hits**. Number of hits of ad. This variable shows the number of hits that the advertisement got.
- **click_schnellkontakte**. Number of clicks on contact button. This variable indicates the number of clicks on the contact button.
- **click_customer**. Number of clicks on customer profile. This variable indicates the number of clicks on the customer profile.
- **click_weitersagen**. Number of clicks on share button. 
- **click_url**. Number of clicks on customer URL. 
- **liste_show**. Number of hits through result list. The variable describes how often the advertisement appeared in the result list while searching the website.
- **liste_match**. Number of hits through search request. The variable describes how often the advertisement fit a pre-specified search request.
- **immobilientyp**. Type of real estate. This artificial number indicates the type of a property.
- **denkmalobjekt**. Protected historic building. This is an indicator of whether or not the property is protected.
- **einbaukueche**. Kitchenette in housing unit. This variable indicates the presence of a fitted kitchen.
- **einliegerwohnung**. Granny flat in housing unit. 
- **ev_wwenthalten**. Warm water consumption included in energy consumption. This is a binary variable indicating whether the warm water consumption was included in the calculation of the energy consumption value.
- **ferienhaus**. Usable as holiday home. This is a binary indicator for whether the housing unit can be used as a holiday home. It is only filled for apartments.
- **foerderung**. Public housing. This is a binary variable indicating that a certificate of eligibility to public housing is needed to rent the apartment.
- **gaestewc**. Guest toilet in housing unit. 
- **garten**. (Shared) garden available. 
- **kaufvermietet**. Rented when sold. This variable indicates if a housing unit for sale is already rented out.
- **keller**. Cellar in housing unit. This variable indicates if an housing unit has a cellar or a cellar room.
- **parkplatz**. Garage/parking space available. This is a binary variable indicating whether a parking space is available.
- **rollstuhlgerecht**. Accessible, no steps. This is a binary indicator for step-free access to the housing unit.
- **bauphase**. Construction phase. This variable indicates whether the housing unit is still under construction. Missings likely indicate that the housing unit is not under construction.
- **ausstattung**. Facilities of housing unit. This is an artificial category number indicating the facilities of the housing unit.
- **energieeffizienzklasse**. Energy Efficiency Rating. The Energy Efficiency rating is represented here as an artificially created categorical variable.
- **energieausweistyp**. Type of Energy Performance Certificates (EPCs). This variable indicates the type of Energy Performance Certificate that the customer has for the housing unit.
- **haustier_erlaubt**. Pets allowed. This binary indicator shows whether pets are allowed in the housing unit.
- **heizungsart**. Type of heating. This is an artificially created category number indicating the type of heating.
- **kategorie_Haus**. House type. The artificial category number indicates which housing unit category a property belongs to. Each property is assigned exactly one category number. This variable is filled for houses only.
- **objektzustand**. Condition of housing unit. The artificial condition number indicates the condition of a property. Each property is assigned exactly one out of 11 possible numbers.
- **ergg_1km**. 1-skm raster cell following INSPIRE. This variable indicates the grid cell of a 1-square-km raster of Germany according to the INSPIRE guideline.
- **blid**. German federal states (Bundesländer).
- **gid2019**. Municipality identifier (AGS, 2019). This is the municipality identifier according to the German Official Municipality Key (Amtlicher Gemeindeschluessel). It is based on the territorial definition of 2019 (end of year).
- **kid2019**. District identifier (AGS, 2019). This is the district identifier according to the German Official Municipality Key (Amtlicher Gemeindeschluessel). It is based on the territorial definition of 2019 (end of year).
- **bef1**. Firing type. Firing type of heating system; if there are several heating types than they are listed in bef2, bef3 etc.
- **bef2**. Firing type. Firing type of heating system; if there are several heating types than they are listed in bef2, bef3 etc.
- **bef10**. Firing type. Firing type of heating system; if there are several heating types than they are listed in bef2, bef3 etc.
- **bef9**. Firing type. Firing type of heating system; if there are several heating types than they are listed in bef2, bef3 etc.
- **bef8**. Firing type. Firing type of heating system; if there are several heating types than they are listed in bef2, bef3 etc.
- **bef7**. Firing type. Firing type of heating system; if there are several heating types than they are listed in bef2, bef3 etc.
- **bef6**. Firing type. Firing type of heating system; if there are several heating types than they are listed in bef2, bef3 etc.
- **bef5**. Firing type. Firing type of heating system; if there are several heating types than they are listed in bef2, bef3 etc.
- **bef4**. Firing type. Firing type of heating system; if there are several heating types than they are listed in bef2, bef3 etc.
- **bef3**. Firing type. Firing type of heating system; if there are several heating types than they are listed in bef2, bef3 etc.
- **anbieter**. Type of offeror. Type of offeror like private, real-estate agent etc.
- **duplicateid**. Classification of housing unit identifiers used more than once. This is a generated variable, indicating whether a duplicate spell is likely to be the same housing unit, or a new housing unit. New housing units can have the same ID when customers re-use a previous advertisement for another apartment, or when an housing unit is re-rented/resold. In City Campus File only.
- **spell**. Spell counter within housing unit identifier. This is an artificially generated variable indicating the spell within each housing unit ID, should an ID occur more than once. Spells are ordered chronologically. In City Campus File only.
- **hits_gen**. Number of hits of ad, adjusted by ad availability. This variable shows the number of hits that the advertisement got. The value
is adjusted by the availability of ad (i.e., laufzeittage).
- **click_schnellkontakte_gen**. Number of clicks on contact button, adjusted by ad availability. This variable indicates the number of clicks on the contact button. The value is adjusted by the availability of ad (i.e., laufzeittage).
- **click_weitersagen_gen**. Number of clicks on share button, adjusted by ad availability. This variable indicates the number of clicks on the share button. The value is adjusted by the availability of ad (i.e., laufzeittage).
- **click_url_gen**. Number of clicks on customer url, adjusted by ad availability. This variable indicates the number of clicks on the customer’s URL. The value is adjusted by the availability of ad (i.e., laufzeittage).
- **liste_show_gen**. Number of hits through result list, adjusted by ad availability. The variable describes how often the advertisement appeared in the result list while searching the website. The value is adjusted by the availability of ad (i.e., laufzeittage).
- **liste_match_gen**. Number of hits through search request, adjusted by ad availability. The variable describes how often the advertisement fit a pre-specified search request. The value is adjusted by the availability of ad (i.e., laufzeittage).
- **adat**. Beginning of ad, month. This is a numerical variable, which refers to the month during which a housing unit is first advertised. If a housing unit is advertised at least at some point in time during a certain month, this advertisement is included in the respective wave. If an advertisement is updated during a specific month, only the last update is recorded and enters the dataset.
- **edat**. Ending of ad, month. This numeric variable refers to the month of the end of the advertisement. This can be misleading of the advertisement is split into two spells due to the timing of the data extraction from the database (see Section 2 for more information).
- **price_sqm**. Price per sqm in EUR. Calculated price per square meter by price and size of house/size of apartment.
