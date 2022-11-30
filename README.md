# Semestralni prace na AEDA

**Authors: Hlavaty, Lubojacky**
**CVUT FEL, 2022**


### Setup
- Krizek &#9744; => neni hotove
- Fajfka &#9745; => je hotove
- Krizek &#9744;, J => in progress a kdo na tom dela

## EDA (exploratory data analysis) &#9744;
- **Hodit ocko na data &#9745;**
    - Kategoricke, numericke i count (skore z dotazniku) promene
    - Clinical information - Seems OK
    - Demographic information - Seems OK mostly
    - UPDRS III - dotaznikova skore
    - Medication - Not sure if we can use this? Only a couple of subjects are on medication
    - Speech, vektor z $\mathbb{R}^{12}$ pro oboji - Tohle bude asi nejvic uzitecne
        - Reading passage
        - Monologue  
- **Separate data &#9745;**
    - xls file loading is trash (at least in R, maybe matlab handles it better), it will be easier to separate the data into csv files and work with that  
- **Prohlednout si data, udelat grafy  &#9744;**
    - Pro UPDRS final skore?
    - Pripadne udelat dim reduction na jednotlivych skore
    - Pro clinical information mozna??
    - Pro speech data urcite, tady bude asi nejvic uzitecne udelat redukci dimenze
    - Data maji ruzne skaly / jednotky, pro nektere metody je bude mozna treba normalizovat ci pouzit jen to co dava smysl

### Hypotezy
- Rozdily mezi parkinson a sleepers : &#9744;
    - Na zaklade vysledku z dotazniku UPDRS_III &#9744;
    - Udelat nejaky statisticky testy pro rozdily mezi skupinami, zname ze cvik &#9744;
    - Rozdily mezi vsemi skupinami na zaklade speech dat (to je asi jediny podle ceho to pujde) : &#9744;
        - ANOVA
        - Selekce promenych (aka v cem jsou nejvetsi rozdily)

## Clustering : &#9744; J
- Na zaklade speech dat, je tam vysoka dimenzionalita, tudiz bude potreba udelat redukci, PCA, kernel PCA, ISOMAP, UMAP, ...

## Klasifikace : &#9744;
- Jsou tam ruzne typy promenych kategoricke, count, numericke, tudiz by z toho mozna sel postavit decision tree (parkinson vs. sleeper, prip do vsech 3, ale tam nepujdou pouzit vsechny variables, protoze pro HC tam nejsou)
- Dat ke kazde skupine je celkem dost, tudiz by melo jit udelat train, test split a vyzkouset ruzne metody
- Napady: KNN, Logisticka regrese, DT, SVM, XGBoost (to je docela SOTA pro tabularni data, takze tady bych cekal uspechy), ...