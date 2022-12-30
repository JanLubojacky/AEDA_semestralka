# Semestralni prace na AEDA

**Authors: Hlavaty, Lubojacky**
**CVUT FEL, 2022**


### Setup
- Krizek :x: => neni hotove
- Fajfka :white_check_mark: => je hotove
- In progress :hammer_and_wrench:, J => a kdo na tom dela

## EDA (exploratory data analysis) :white_check_mark:
- **Hodit ocko na data** :white_check_mark:
    - Kategoricke, numericke i count (skore z dotazniku) promene
    - Clinical information - Seems OK
    - Demographic information - Seems OK mostly
    - UPDRS III - dotaznikova skore
    - Medication - Not sure if we can use this? Only a couple of subjects are on medication
    - Speech, vektor z $\mathbb{R}^{12}$ pro oboji - Tohle bude asi nejvic uzitecne
        - Reading passage
        - Monologue
        
- **Separate data** :white_check_mark:
    - xls file loading is trash (at least in R, maybe matlab handles it better), it will be easier to separate the data into csv files and work with that
    - Bacha, excel to vyexportoval s ";" jako separatorem, most likely to budes muset pri nacitani specifikovat
- **Prohlednout si data, udelat grafy** :x:
    - Pro UPDRS final skore?
    - Pripadne udelat dim reduction na jednotlivych skore
    - Pro clinical information mozna??
    - Pro speech data urcite, tady bude asi nejvic uzitecne udelat redukci dimenze
    - Data maji ruzne skaly / jednotky, pro nektere metody je bude mozna treba normalizovat ci pouzit jen to co dava smysl

## Hypotezy :x:
- Rozdily mezi parkinson a sleepers : :x:
    - Na zaklade vysledku z dotazniku UPDRS_III :x:
    - Udelat nejaky statisticky testy pro rozdily mezi skupinami, zname ze cvik :x:
    - Rozdily mezi vsemi skupinami na zaklade speech dat (to je asi jediny podle ceho to pujde) :x:
        - ANOVA
        - Selekce promenych (aka v cem jsou nejvetsi rozdily)

## Clustering : :hammer_and_wrench: J
- Hotove LDA :white_check_mark:
- PCA :x:
- Nejake nelinearni clustrovani Isomap, UMAP?
- Na zaklade speech dat, je tam vysoka dimenzionalita, tudiz bude potreba udelat redukci, PCA, kernel PCA, ISOMAP, UMAP, ...

## Hotova feature selection pro reading a monolog dohromady :white_check_mark:
- pomoci logisticke regrese s l1 a l2 regularizicemi se vyberou variables, ktere maji nejvetsi vliv na rozrazeni do trid

## Klasifikace : :x:
- Jsou tam ruzne typy promenych kategoricke, count, numericke, tudiz by z toho mozna sel postavit decision tree (parkinson vs. sleeper, prip do vsech 3, ale tam nepujdou pouzit vsechny variables, protoze pro HC tam nejsou)
- Dat ke kazde skupine je celkem dost, tudiz by melo jit udelat train, test split a vyzkouset ruzne metody
- Napady: KNN, Logisticka regrese, DT, SVM, XGBoost (to je docela SOTA pro tabularni data, takze tady bych cekal uspechy), ...
