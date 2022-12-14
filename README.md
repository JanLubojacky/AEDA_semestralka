# Semestralni prace na AEDA

**Authors: Hlavaty, Lubojacky**
**CVUT FEL, 2022**

Prezentace:
https://docs.google.com/presentation/d/1OgtbYg4KLLxsYM9PNC9rhcmC_UgKenjSbkglwne1Css/edit?usp=sharing

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
- **Prohlednout si data, udelat grafy** ✅:
    - Pro UPDRS final skore?
    - Pripadne udelat dim reduction na jednotlivych skore
    - Pro clinical information mozna??
    - Pro speech data urcite, tady bude asi nejvic uzitecne udelat redukci dimenze
    - Data maji ruzne skaly / jednotky, pro nektere metody je bude mozna treba normalizovat ci pouzit jen to co dava smysl

## Hypotezy :white_check_mark:
- Rozdily mezi parkinson a sleepers : :white_check_mark:
    - Na zaklade vysledku z dotazniku UPDRS_III :white_check_mark:
    - Udelat nejaky statisticky testy pro rozdily mezi skupinami, zname ze cvik :white_check_mark:
    - Rozdily mezi vsemi skupinami na zaklade speech dat (to je asi jediny podle ceho to pujde) :white_check_mark:
        - ANOVA
        - Selekce promenych (aka v cem jsou nejvetsi rozdily)

## Dimension redcution : :white_check_mark:
- Na zaklade speech dat, je tam vysoka dimenzionalita, tudiz bude potreba udelat redukci, PCA, kernel PCA, ISOMAP, UMAP, ...
- LDA :white_check_mark:
- PCA :white_check_mark:
- Nejake nelinearni clustrovani Isomap, UMAP? :white_check_mark:

## Hotova feature selection pro reading a monolog dohromady :white_check_mark:
- pomoci logisticke regrese s l1 a l2 regularizicemi se vyberou variables, ktere maji nejvetsi vliv na rozrazeni do trid

## Klasifikace : :x:
- Jsou tam ruzne typy promenych kategoricke, count, numericke, tudiz by z toho mozna sel postavit decision tree (parkinson vs. sleeper, prip do vsech 3, ale tam nepujdou pouzit vsechny variables, protoze pro HC tam nejsou)
- Dat ke kazde skupine je celkem dost, tudiz by melo jit udelat train, test split a vyzkouset ruzne metody
- Napady: KNN, Logisticka regrese, DT, SVM, XGBoost, ...
