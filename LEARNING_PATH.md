# Learning Path — fil conducteur unique

Ce fichier donne **l'ordre logique de progression** du parcours.

Il complete `SKILLS.md` :

- `SKILLS.md` = base de donnees de toutes les competences a construire ;
- `LEARNING_PATH.md` = ordre dans lequel les travailler ;
- `ROADMAP.md` = jalons mensuels et direction globale ;
- GitHub Project = travail concret de la semaine.

L'objectif ici est d'eviter de sauter d'un sujet a l'autre.

---

# Regle principale

Suivre les blocs dans cet ordre :

```text
1. Stats descriptives + Data
        ↓
2. Probabilites
        ↓
3. Inference statistique
        ↓
4. Calculus + algebre lineaire essentiels
        ↓
5. Fondamentaux Time Series
        ↓
6. Validation / Backtesting
        ↓
7. Modeles statistiques de forecasting
        ↓
8. Machine Learning
        ↓
9. Feature Engineering Time Series
        ↓
10. Forecast probabiliste + decisions SCM
        ↓
11. Software Engineering / Pipeline
        ↓
12. MLOps / Cloud / Scale
        ↓
13. Specialisations : Deep Learning / ETA / Agents
```

Ne pas commencer un bloc avance simplement parce qu'il est interessant.

On avance quand les notions du bloc courant sont suffisamment solides pour etre utilisees dans le projet.

---

# Fil projet permanent : M5

M5 commence des le premier bloc et grandit avec le niveau acquis.

```text
Stats descriptives
    → EDA M5

Probabilites
    → distributions / zeros / variabilite / simulation simple

Inference
    → estimation / incertitude / regression simple

Calculus + algebre lineaire
    → comprendre loss, optimisation et modeles a venir

Time Series
    → structure temporelle M5

Backtesting
    → evaluation temporelle correcte

Modeles statistiques
    → benchmark ETS / ARIMA / baselines

Machine Learning
    → arbres / boosting / LightGBM / XGBoost

Feature Engineering
    → lags / rolling / calendrier / prix / promotions

Probabiliste + SCM
    → quantiles / intervalles / simulation stock

Engineering
    → pipeline reproductible et executable

MLOps / Scale
    → tracking / monitoring / retraining / gros volumes
```

Le projet ne remplace pas le cursus : il sert a appliquer et verifier les notions apprises.

---

# 1. Stats descriptives + Data

## Pourquoi commencer ici

Avant de prevoir quoi que ce soit, il faut savoir ce que represente une ligne, une variable, une serie, une distribution et une agregation.

## Ordre interne

1. population / echantillon ;
2. observation / variable / granularite ;
3. types de variables ;
4. moyenne / mediane / mode ;
5. variance / ecart-type ;
6. quantiles / percentiles ;
7. IQR / MAD ;
8. distribution empirique ;
9. outliers ;
10. covariance / correlation ;
11. visualisation exploratoire ;
12. valeurs manquantes vs zeros ;
13. duplicats / anomalies ;
14. agregation / desagregation ;
15. dates / calendriers ;
16. jointures et cardinalite.

## Outils a utiliser en parallele

- Python / pandas ;
- NumPy de base ;
- SQL : `SELECT`, `WHERE`, `ORDER BY`, `GROUP BY`, `JOIN` ;
- Git de base.

## Application M5

- definir le probleme ;
- charger les tables ;
- comprendre les cles ;
- verifier la granularite ;
- selectionner quelques series ;
- produire une premiere EDA ;
- comparer niveaux, dispersion, zeros et profils temporels.

## Preuve pour passer au bloc 2

Je peux prendre une serie M5 inconnue, produire une EDA descriptive propre et expliquer mes indicateurs sans suivre un tutoriel pas a pas.

---

# 2. Probabilites

## Pourquoi maintenant

La statistique descriptive decrit ce qui a ete observe. La probabilite donne le langage necessaire pour raisonner sur l'incertitude et preparer le forecasting probabiliste.

## Ordre interne

1. experiences / evenements ;
2. probabilites ;
3. probabilite conditionnelle ;
4. independance ;
5. variable aleatoire ;
6. PMF ;
7. PDF ;
8. CDF ;
9. esperance ;
10. variance d'une variable aleatoire ;
11. loi normale ;
12. loi binomiale ;
13. loi de Poisson ;
14. simulation Monte Carlo de base ;
15. loi des grands nombres ;
16. theoreme central limite.

## Application projet

- relier distributions theoriques et distributions observees ;
- simuler des variables simples ;
- raisonner sur probabilites, quantiles et evenements ;
- analyser la frequence des zeros et la variabilite sur M5.

## Preuve pour passer au bloc 3

Je peux expliquer une variable aleatoire, esperance, variance, CDF et probabilite conditionnelle, puis les utiliser sur de petits exercices sans memoriser seulement des formules.

---

# 3. Inference statistique

## Pourquoi maintenant

Une fois l'incertitude comprise, il faut apprendre comment passer d'un echantillon a une conclusion plus generale et comment quantifier l'incertitude d'une estimation.

## Ordre interne

1. parametre / statistique / estimateur ;
2. echantillonnage ;
3. sampling distribution ;
4. biais d'un estimateur ;
5. standard error ;
6. intervalle de confiance ;
7. test d'hypothese — intuition ;
8. p-value — intuition ;
9. erreurs de type I / II ;
10. effet / puissance — intuition ;
11. regression lineaire simple ;
12. regression multiple ;
13. diagnostics de regression.

Les tests specialises ne sont pas prioritaires. Ils sont ajoutes seulement quand un besoin concret apparait.

## Preuve pour passer au bloc 4

Je peux distinguer parametre, estimateur, erreur standard et intervalle de confiance et expliquer ce qu'une regression estime sans confondre association et causalite.

---

# 4. Calculus + algebre lineaire essentiels

## Pourquoi ici

Ce bloc n'est pas un cursus de mathematiques complet. Il fournit uniquement les outils necessaires pour comprendre optimisation, regression, fonctions de perte, gradient boosting et deep learning plus tard.

## Ordre interne — Calculus

1. fonctions ;
2. pente / taux de variation ;
3. logarithmes / exponentielles ;
4. derivee ;
5. regles de derivation ;
6. chain rule ;
7. derivees partielles ;
8. gradient ;
9. minimum / maximum ;
10. optimisation d'une fonction de perte ;
11. gradient descent — intuition.

## Ordre interne — Algebre lineaire

1. scalaires ;
2. vecteurs ;
3. matrices ;
4. dimensions ;
5. addition / multiplication ;
6. produit scalaire ;
7. produit matriciel ;
8. interpretation matricielle d'une regression — intuition.

## Preuve pour passer au bloc 5

Je peux expliquer ce que mesure une derivee, ce qu'est un gradient et pourquoi minimiser une loss revient a chercher des parametres qui reduisent l'erreur.

---

# 5. Fondamentaux Time Series

## Pourquoi maintenant

Une serie temporelle n'est pas un dataset tabulaire ordinaire : l'ordre temporel, la dependance entre observations et la disponibilite de l'information changent toute la validation.

## Ordre interne

1. index temporel / frequence ;
2. forecast origin ;
3. forecast horizon ;
4. tendance ;
5. saisonnalite ;
6. cycle / bruit ;
7. lags ;
8. autocorrelation ;
9. ACF ;
10. PACF ;
11. bruit blanc ;
12. stationnarite ;
13. differenciation ;
14. transformations log / Box-Cox ;
15. STL ;
16. effets calendrier ;
17. ruptures structurelles ;
18. series intermittentes.

## Application M5

- visualiser les structures temporelles ;
- identifier saisonnalites et ruptures ;
- comparer des series tres differentes ;
- raisonner sur ce qui est connu a une date donnee.

## Preuve pour passer au bloc 6

Je peux decrire la structure temporelle d'une serie et expliquer pourquoi un split aleatoire classique serait incorrect.

---

# 6. Validation / Backtesting

## Pourquoi avant les modeles avances

Un modele performant avec une mauvaise validation n'a aucune valeur. Le moteur d'evaluation doit exister avant de multiplier les modeles.

## Ordre interne

1. train / validation / test chronologiques ;
2. forecast origin ;
3. rolling-origin cross-validation ;
4. expanding window ;
5. rolling window ;
6. multi-horizon evaluation ;
7. leakage temporel ;
8. feature availability ;
9. point-in-time correctness ;
10. tuning sans fuite ;
11. benchmark identique entre modeles ;
12. MAE ;
13. RMSE ;
14. MAPE et limites ;
15. MASE / RMSSE ;
16. forecast bias ;
17. evaluation par horizon / segment.

## Application M5

Construire un backtest reproductible avec au minimum naive et seasonal naive.

## Preuve pour passer au bloc 7

Je peux lancer le meme backtest sur plusieurs series, verifier qu'aucune information future n'est utilisee et comparer les modeles avec les memes regles.

---

# 7. Modeles statistiques de forecasting

## Ordre interne

1. mean forecast ;
2. naive ;
3. seasonal naive ;
4. drift ;
5. SES ;
6. Holt ;
7. damped trend ;
8. Holt-Winters ;
9. ETS / state space — intuition ;
10. AR ;
11. MA ;
12. ARMA ;
13. ARIMA ;
14. SARIMA ;
15. time-series regression ;
16. dynamic regression / SARIMAX ;
17. diagnostics residuels ;
18. Ljung-Box.

## Outils

- FPP3 / fable pour comprendre et analyser ;
- statsmodels pour inspection Python ;
- StatsForecast pour benchmark multi-series scalable.

## Preuve pour passer au bloc 8

Je peux benchmarker plusieurs modeles statistiques avec le meme protocole et expliquer pourquoi un modele gagne ou perd sur certaines series.

---

# 8. Machine Learning

## Pourquoi seulement maintenant

Le ML arrive une fois les donnees, la validation temporelle, les baselines et le fonctionnement des previsions classiques compris.

## Ordre interne

1. fonction de perte ;
2. underfitting / overfitting ;
3. bias-variance trade-off ;
4. regularisation ;
5. generalisation ;
6. regression lineaire vue comme modele ML ;
7. Ridge / Lasso ;
8. decision trees ;
9. Random Forest ;
10. gradient boosting ;
11. XGBoost ;
12. LightGBM ;
13. hyperparametres ;
14. tuning ;
15. modeles locaux vs globaux ;
16. recursive vs direct vs multi-output ;
17. feature importance ;
18. SHAP — avec prudence ;
19. cold start / nouveaux SKU.

## Application M5

Comparer LightGBM / XGBoost aux baselines et modeles statistiques dans le meme backtest.

## Preuve pour passer au bloc 9

Je peux entrainer un modele boosting sur plusieurs series sans fuite temporelle et expliquer ce que la loss, les features et le protocole de validation apportent.

---

# 9. Feature Engineering Time Series

## Ordre interne

1. lag features ;
2. rolling features ;
3. expanding features ;
4. calendar features ;
5. prix ;
6. promotions ;
7. evenements ;
8. Fourier features ;
9. encodage categoriel ;
10. interactions ;
11. variables futures connues vs inconnues ;
12. feature leakage.

## Preuve pour passer au bloc 10

Je peux creer un jeu de features point-in-time correct, expliquer la disponibilite de chaque variable au moment du forecast et mesurer son impact par backtest.

---

# 10. Forecast probabiliste + decisions SCM

## Ordre interne

1. distribution predictive ;
2. quantiles predictifs ;
3. prediction intervals ;
4. intervalle de confiance vs intervalle de prediction ;
5. calibration ;
6. coverage ;
7. sharpness ;
8. pinball loss ;
9. interval score ;
10. CRPS — intuition ;
11. demande intermittente ;
12. lead time ;
13. lead-time demand ;
14. safety stock ;
15. reorder point ;
16. service level / fill rate ;
17. cout de rupture / stockage ;
18. newsvendor / quantile optimal ;
19. simulation de stock ;
20. hierarchies et reconciliation ;
21. Forecast Value Added / overrides humains.

## Preuve pour passer au bloc 11

Je peux montrer non seulement quel modele predit mieux, mais comment l'incertitude predictive change une decision de stock.

---

# 11. Software Engineering / Pipeline

Les bases de Git, fonctions et organisation du code sont utilisees depuis le debut. Ici, elles deviennent un vrai systeme de production.

## Ordre interne

1. structure de projet ;
2. fonctions / modules ;
3. exceptions ;
4. typing de base ;
5. environnements / dependances ;
6. configuration ;
7. tests ;
8. logging ;
9. CLI ;
10. packaging ;
11. ingestion ;
12. validation des donnees ;
13. feature pipeline ;
14. training pipeline ;
15. backtesting pipeline ;
16. forecast pipeline ;
17. sauvegarde des predictions et metadonnees ;
18. idempotence ;
19. retries / checkpoints ;
20. Docker ;
21. orchestration.

## Preuve pour passer au bloc 12

Je peux lancer le pipeline hors notebook de facon reproductible et diagnostiquer une erreur grace aux tests, logs et artefacts sauvegardes.

---

# 12. MLOps / Cloud / Scale

## Ordre interne

1. experiment tracking ;
2. version des donnees / modeles / features ;
3. model registry ;
4. archivage forecasts + actuals ;
5. monitoring ;
6. data drift / model drift / biais ;
7. alertes ;
8. fallback ;
9. retraining ;
10. champion / challenger ;
11. rollback ;
12. CI/CD ;
13. secrets / permissions ;
14. profiling temps / memoire ;
15. Parquet / formats colonne ;
16. partitionnement ;
17. batching ;
18. vectorisation ;
19. parallelisation ;
20. DuckDB ;
21. cloud / AWS — bases ;
22. Spark ;
23. PySpark ;
24. Databricks ;
25. cout / performance ;
26. tests de passage a l'echelle vers de tres nombreuses series.

## Preuve pour passer au bloc 13

Je connais les limites mesurees de mon systeme, je peux l'executer regulierement, suivre ses performances et expliquer quand une infrastructure distribuee devient necessaire.

---

# 13. Specialisations

Ces sujets arrivent apres le socle. Ils ne doivent pas perturber le parcours principal avant que les blocs precedents soient operationnels.

## Deep Learning / modeles avances

1. tenseurs ;
2. forward / backward pass ;
3. backpropagation ;
4. optimizers ;
5. PyTorch ;
6. DeepAR / modeles probabilistes ;
7. Transformers time series ;
8. GluonTS ;
9. Nixtla ;
10. foundation models / TimeGPT ;
11. zero-shot / fine-tuning ;
12. benchmark contre les baselines existantes.

## ETA / temps reel

1. definition trip / event ;
2. GPS / AIS / trajectoires ;
3. nettoyage spatial / temporel ;
4. labels depart / arrivee ;
5. features distance / temps / congestion ;
6. baseline ETA ;
7. ML ETA ;
8. evaluation par phase du trajet ;
9. API ;
10. SDK ;
11. WebSocket / streaming ;
12. monitoring temps reel.

## Agents IA

1. LLM / structured outputs ;
2. tool calling ;
3. API / SDK ;
4. boucle agent ;
5. etat / memoire ;
6. permissions ;
7. sandboxing ;
8. evaluation agent ;
9. cout / latence ;
10. reproductibilite ;
11. agent qui propose une experience ;
12. moteur deterministe qui execute ;
13. benchmark automatique ;
14. validation avant promotion en production.

---

# Regles transversales

Ces pratiques existent depuis le debut mais ne changent pas l'ordre principal :

- Git : utiliser des le jour 1 ;
- Python / SQL : apprendre au fur et a mesure des besoins du bloc courant ;
- tests : commencer simples puis les approfondir au bloc Engineering ;
- documentation : laisser une preuve courte de chaque resultat important ;
- retrieval / repetition espacee : reutiliser les notions plutot que relire passivement ;
- M5 : rester le terrain principal jusqu'a ce que le moteur soit suffisamment solide pour etre transfere.

---

# Comment choisir quoi faire aujourd'hui

Toujours utiliser cette chaine :

```text
LEARNING_PATH.md
      ↓
bloc courant
      ↓
SKILLS.md
      ↓
competences du bloc courant
      ↓
GitHub Project
      ↓
1 issue concrete
      ↓
travail
      ↓
preuve
      ↓
Done
```

Si une notion avancee apparait pendant le travail :

- si elle bloque immediatement le projet, apprendre uniquement le minimum necessaire ;
- sinon, l'ajouter au backlog et revenir au bloc courant.

---

# Point de depart actuel

Le parcours commence ici :

> **Bloc 1 — Stats descriptives + Data, appliquees a M5.**

Ordre immediat :

```text
Definir le probleme M5
    ↓
Comprendre / charger les donnees
    ↓
Population / echantillon / variables / granularite
    ↓
Moyenne / mediane
    ↓
Variance / ecart-type
    ↓
Quantiles / IQR / MAD
    ↓
Distribution empirique / outliers
    ↓
Premiere EDA M5
    ↓
Reproduction sur d'autres series
```

Tant que ce bloc n'est pas suffisamment maitrise, ne pas travailler XGBoost, ARIMA, Databricks, PySpark, Deep Learning ou Agents comme sujets principaux.
