# Checkpoints — épreuves de fin de bloc

Les checkpoints remplacent l'auto-évaluation vague par une tâche datée, timeboxée et observable.

## Conditions communes

- la **partie conceptuelle** se fait sans notes, sans tutoriel et sans LLM ;
- la documentation d'API et les signatures de fonctions sont autorisées pour la partie technique ;
- les données/exemples doivent être différents de ceux utilisés pendant l'apprentissage ;
- le résultat et le temps réel sont consignés dans `LEARNING_LOG.md` ou dans un fichier `checkpoints/` ;
- aucun copier-coller du notebook/exercice précédent ;
- un retry est autorisé après 8–12 h de travail ciblé ;
- B6 est un hard gate : aucune dette de validation/leakage n'est acceptée.

Un checkpoint teste la compréhension et la capacité à construire, pas la mémorisation d'une API.

---

## B1 — Stats descriptives + Data / EDA · 2 h

Sur trois séries M5 non étudiées auparavant :
1. définir granularité, types et qualité des données ;
2. produire moyenne/médiane, dispersion, quantiles, zéros/manquants ;
3. produire trois graphiques apportant des informations différentes ;
4. écrire une interprétation courte, avec limites.

**Passage** — résultats corrects, interprétation cohérente, pas de confusion moyenne/médiane/dispersion, pas de conclusion causale abusive.

## B2 — Probabilités · 90 min

Sur des problèmes courts et un petit exemple simulé :
1. conditionnelle / indépendance ;
2. variable aléatoire, espérance, variance ;
3. PMF/PDF/CDF ;
4. normale, binomiale, Poisson ;
5. simulation Monte Carlo et comparaison théorie/simulation.

**Passage** — raisonnement probabiliste correct. Pas d'obligation d'ajuster déjà une loi à une série intermittente M5.

## B3 — Inférence statistique · 90 min

Sur un échantillon nouveau ou un dataset contrôlé :
1. moyenne, standard error et IC à 95 % ;
2. expliquer sampling distribution, biais et p-value ;
3. régression simple/multiple et interprétation prudente ;
4. distinguer association et causalité.

**Passage** — interprétation statistique correcte. L'application M5 reste exploratoire tant que la dépendance temporelle n'a pas été étudiée.

## B4 — Calculus + algèbre linéaire · 75 min

1. dériver des fonctions simples ;
2. appliquer chain rule et dérivées partielles simples ;
3. calculer le gradient d'une MSE simple ;
4. opérations vecteurs/matrices utiles à la régression ;
5. expliquer l'idée de gradient descent.

**Passage** — mécanisme compris ; pas besoin de mémoriser toute l'algèbre de moindres carrés.

## B5 — Fondamentaux séries temporelles · 2 h

Sur des séries inconnues :
1. tendance, saisonnalité, ruptures, intermittence ;
2. lags et ACF/PACF ;
3. STL ;
4. stationnarité / différenciation si nécessaire ;
5. expliquer pourquoi un split aléatoire est problématique.

**Passage** — diagnostics interprétés avec prudence, pas seulement produits.

## B6 — Validation / backtesting · 3 h · HARD GATE

À partir d'un petit jeu de données et de ton package vide ou existant :
1. rolling-origin sur plusieurs séries et plusieurs origines ;
2. naive + seasonal naive ;
3. métrique + biais par horizon ;
4. vérifier manuellement quelques prédictions ;
5. test anti-leakage avec une fuite volontaire ;
6. relance reproductible.

Documentation d'API autorisée. L'ancien notebook ne doit pas être copié.

**Passage** — origine/horizon corrects, aucune observation future utilisée, test anti-fuite effectif, résultats reproductibles. Si ce checkpoint échoue, on ne passe pas aux benchmarks avancés.

## B7 — Modèles statistiques · 3 h

1. ETS et ARIMA/SARIMA dans le même backtest que les baselines ;
2. diagnostics résiduels ;
3. comparaison par série/segment ;
4. formuler des **hypothèses structurelles** expliquant les écarts, sans prétendre à une causalité certaine.

**Passage** — protocole identique entre modèles et interprétation argumentée.

## B8 — Machine Learning · 3 h

1. modèle global LightGBM ou XGBoost ;
2. split/backtest temporel inchangé ;
3. feature set minimal et dates de disponibilité explicites ;
4. comparaison au meilleur modèle statistique ;
5. expliquer où une fuite pourrait apparaître dans le code.

**Passage** — gain mesuré et complexité supplémentaire discutée.

## B9 — Feature engineering · 3 h

1. lags, rolling, calendrier, prix/promotions si disponibles ;
2. date de disponibilité de chaque feature ;
3. fuite volontaire détectée par test ;
4. ablation par groupe de features.

**Passage** — features point-in-time correctes et apport évalué par backtest, pas uniquement par feature importance.

## B10 — Forecast probabiliste + SCM · 3 h

1. produire plusieurs quantiles ;
2. pinball loss, coverage, calibration ;
3. lead-time demand / safety stock simple ;
4. simulation de politique de stock ;
5. comparer classement prédictif et classement décisionnel.

**Passage** — expliquer le résultat observé. Une divergence RMSE/coût n'est pas obligatoire ; si elle n'apparaît pas, expliquer les conditions sous lesquelles elle pourrait apparaître et tester un scénario raisonnable.

## B11 — Software engineering / pipeline · 3 h

1. environnement neuf ;
2. une commande lance le workflow principal ;
3. tests / logs / config ;
4. ajouter un nouveau modèle sans modifier le cœur du backtest.

Documentation technique autorisée.

**Passage** — workflow reproductible et abstraction suffisamment propre pour étendre le moteur.

## B12 — MLOps / cloud / scale · 4 h

1. expérience tracée et rejouable ;
2. anomalie d'entrée détectée ;
3. fallback ou comportement dégradé documenté ;
4. mesures temps/mémoire sur plusieurs volumes ;
5. décision argumentée : optimisation locale suffisante ou calcul distribué justifié.

**Passage** — décision fondée sur des chiffres mesurés, pas sur le prestige d'un outil.

## B13 — Transfert / spécialisation · 4 h

1. réutiliser le socle sur un second contexte ;
2. ne pas réécrire le moteur principal ;
3. livrer **une seule** spécialisation si le Core est solide ;
4. documenter ce qui a été réutilisé, adapté et abandonné.

**Passage** — le système prouve qu'il est transférable, pas seulement spécifique à M5.
