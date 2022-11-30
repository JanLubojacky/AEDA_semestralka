# Semestralni prace na AEDA

**Authors: Hlavaty, Lubojacky**
**CVUT FEL, 2022**

## Hypotezy
- Rozdily mezi parkinson a sleepers : [&#9744;]
    - Na zaklade vysledku z dotazniku UPDRS_III [&#9744;]
    - Udelat nejaky statisticky testy pro rozdily mezi skupinami, zname ze cvik [&#9744;]
    - Rozdily mezi vsemi skupinami na zaklade speech dat (to je asi jediny podle ceho to pujde) : [&#9744;]
        - ANOVA
        - Selekce promenych (aka v cem jsou nejvetsi rozdily)
- Clustering : [&#9744;]
    - Na zaklade speech dat, je tam vysoka dimenzionalita, tudiz bude potreba udelat redukci, PCA, kernel PCA, ISOMAP, UMAP, ...
- Klasifikace : [&#9744;]
    - Jsou tam ruzne typy promenych kategoricke, count, numericke, tudiz by z toho mozna sel postavit decision tree (parkinson vs. sleeper, prip do vsech 3, ale tam nepujdou pouzit vsechny variables, protoze pro HC tam nejsou)
    - Dat ke kazde skupine je celkem dost, tudiz by melo jit udelat train, test split a vyzkouset ruzne metody
    - Napady: KNN, Logisticka regrese, DT, SVM, XGBoost (to je docela SOTA pro tabularni data, takze tady bych cekal uspechy), ...

## Data
- Kategoricke, numericke i counts (skore z dotazniku) data
- Clinical information - Seems OK
- Demographic information - Seems OK mostly
- UPDRS III - dotaznikova skore
- Medication - Not sure if we can use this? Only a couple of subjects are on medication
- Speech, vektor z $\mathbb{R}^12$ - Tohle bude asi nejvic uzitecne
    - Reading passage
    - Monologue
- Clean data : [&#9744;]
    - xls file loading is trash (at least in R, maybe matlab handles it better), it will be easier to separate the data into csv files and work with that

- EDA (exploratory data analysis)
    - Prohlednout si data, udelat grafy
        - Pro UPDRS final skore?
        - Pripadne udelat dim reduction na jednotlivych skore
        - Pro clinical information mozna??
        - Pro speech data urcite, tady bude asi nejvic uzitecne udelat redukci dimenze
        - Data maji ruzne skaly / jednotky, pro nektere metody je bude mozna treba normalizovat ci pouzit jen to co dava smysl