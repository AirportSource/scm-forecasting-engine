# Système cible — V0 à V5

Ce fichier décrit ce que le moteur doit réellement savoir faire. La progression se juge d'abord par les capacités du système, pas par le nombre de chapitres lus.

## Cible professionnelle

**Forecasting Data Scientist / Applied ML Engineer spécialisé SCM**

### Core — obligatoire
- statistiques, probabilités, inférence et maths utiles ;
- Python / SQL ;
- séries temporelles, backtesting et prévention du leakage ;
- modèles statistiques, ML et feature engineering ;
- forecasting probabiliste et décisions SCM ;
- software engineering suffisant pour rendre le système reproductible et exploitable.

### Support — opérationnel, sans viser l'expertise senior
- R / fable comme environnement analytique secondaire ;
- Docker, orchestration, experiment tracking, monitoring, cloud ;
- Parquet / DuckDB / Polars ;
- Spark / PySpark / Databricks uniquement si les mesures de volume le justifient.

### Optional — coupé en premier si le planning dérive
1. agents IA avancés ;
2. deep learning / foundation models avancés ;
3. ETA temps réel avancé ;
4. Spark / Databricks avancés au-delà du besoin démontré.

---

## V0 — Je vois les données · cible fin M2

Le chargement est reproductible et je peux décrire honnêtement ce que contiennent les séries.

**Contenu**
- échantillon M5 initial figé et documenté ;
- granularité, clés, cardinalités, dates, zéros et valeurs manquantes compris ;
- contrôles de qualité de base ;
- EDA écrite sur plusieurs séries contrastées.

**Preuve** — sur trois séries non étudiées auparavant, produire une EDA propre et expliquer les différences sans tutoriel.

## V1 — Je sais mesurer · cible fin M5

**C'est la version la plus importante.** Tout le reste dépend d'un moteur d'évaluation fiable.

**Contenu**
- rolling-origin backtesting ;
- horizons et fenêtres paramétrables ;
- baselines mean / naive / seasonal naive / drift ;
- MAE, RMSE, MASE/RMSSE, biais et détail par horizon/segment ;
- test anti-leakage ;
- exécution reproductible hors notebook ;
- résultats persistés avec config et métadonnées.

**Preuve** — même backtest relancé sur le même input = mêmes résultats, et une fuite volontaire est détectée.

## V2 — Je sais modéliser · cible fin M7

**Contenu**
- ETS, ARIMA/SARIMA, régression dynamique ;
- LightGBM/XGBoost global ;
- features point-in-time : lags, rolling, calendrier, prix, promotions ;
- benchmark commun et reproductible ;
- analyse par segment et hypothèses explicatives prudentes.

**Preuve** — un leaderboard régénérable par commande, avec chaque feature et chaque protocole de validation défendables.

## V3 — Je sais décider · cible fin M8

**Contenu**
- forecasts quantiles / intervalles ;
- pinball loss, coverage, sharpness, calibration ;
- demande intermittente ;
- lead-time demand, safety stock, reorder point, service level ;
- simulation simple de politique de stock et de coûts.

**Preuve** — relier les différences de forecast à une conséquence décisionnelle chiffrée. La divergence entre meilleur score prédictif et meilleur coût métier est analysée si elle apparaît ; elle n'est pas imposée artificiellement.

## V4 — Ça tourne tout seul · cible fin M10

**Contenu**
- pipeline ingestion → validation → features → entraînement/backtest → forecast → archivage ;
- config, tests, logs, packaging, CLI ;
- idempotence, retries et fallback ;
- experiment tracking et monitoring ;
- profiling temps/mémoire et optimisation mesurée avant tout outil distribué.

**Preuve** — exécutions planifiées reproductibles et incidents diagnostiquables à partir des logs et artefacts.

## V5 — Ça se transfère · cible fin M12

**Contenu**
- le socle tourne sur un second contexte sans réécriture du cœur ;
- une seule spécialisation est livrée si le Core est solide : ETA, deep learning ou agents ;
- documentation suffisante pour qu'une autre personne puisse lancer et comprendre le projet.

**Preuve** — un tiers peut cloner, installer et exécuter le workflow principal à partir du README.

---

## Tableau de bord

| Version | Cible | Statut | Date réelle | Commentaire |
|---|---|---|---|---|
| V0 — Je vois les données | fin M2 | | | |
| V1 — Je sais mesurer | fin M5 | | | |
| V2 — Je sais modéliser | fin M7 | | | |
| V3 — Je sais décider | fin M8 | | | |
| V4 — Ça tourne tout seul | fin M10 | | | |
| V5 — Ça se transfère | fin M12 | | | |

---

## Règle de conception

Les notebooks servent à explorer et visualiser. La logique réutilisable vit dans `src/`. Les outils ne sont ajoutés qu'après apparition d'un besoin mesuré.
