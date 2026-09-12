# Ressources de référence

Ce fichier fixe les ressources du parcours afin d'éviter de perdre du temps à chercher sans cesse « le meilleur cours ».

## Règle

- **1 ressource principale + 1 complément maximum par bloc**.
- Les ressources sont utilisées pour débloquer une compétence ou suivre le fil du bloc, pas pour accumuler des lectures.
- On ne change pas de ressource principale au milieu d'un bloc sauf si elle est réellement inadaptée.
- Les documentations officielles servent de référence technique ponctuelle.
- Les repos publics et solutions de compétition servent au reverse engineering, pas au copier-coller.

---

## 1. Statistiques descriptives, probabilités et inférence

### Ressource principale
**Think Stats, 3rd Edition — Allen B. Downey**

Usage : statistiques descriptives, distributions, probabilités, estimation, simulations et intuition statistique par le code.

### Complément
**Statistics for Business Analytics (SBA)**  
https://openforecast.org/sba/

Usage : explications alternatives, statistiques appliquées, régression et mise en contexte business.

### Exercices / rappel si nécessaire
**Khan Academy — Statistics & Probability**

Usage : exercices courts lorsque les bases probabilistes ou statistiques restent fragiles.

---

## 2. Calculus et algèbre linéaire essentiels

### Ressource principale
**Khan Academy — Differential Calculus + Linear Algebra**

Usage : fonctions, dérivées, chain rule, dérivées partielles, vecteurs, matrices et opérations de base.

### Complément intuition
**3Blue1Brown — Essence of Calculus / Essence of Linear Algebra**

Usage : intuition visuelle des dérivées, gradients, vecteurs, transformations et matrices.

Le but n'est pas de suivre un cursus de mathématiques complet : uniquement les notions nécessaires à la compréhension des modèles, losses, gradients et optimisation.

---

## 3. Python / manipulation de données

### Ressource principale
**Python Data Science Handbook — Jake VanderPlas**

Usage : NumPy, pandas, visualisation et bases de l'écosystème data Python.

### Complément
**Minimalist Data Wrangling with Python**

Usage : manipulation propre et pragmatique de données.

### Référence technique
Documentation officielle pandas / NumPy.

---

## 4. R / data analysis

### Ressource principale
**R for Data Science, 2e**  
https://r4ds.hadley.nz/

Usage : tidyverse, dplyr, tidyr, visualisation et workflow data.

### Complément
**Tidy Modeling with R**  
https://www.tmwr.org/

Usage : modélisation et workflow reproductible dans l'écosystème R.

### Plus tard si nécessaire
**Advanced R Programming — ETC4500/5450**

Usage : approfondissement R uniquement si le besoin apparaît.

---

## 5. Séries temporelles et forecasting statistique

### Ressource principale
**Forecasting: Principles and Practice, 3rd edition (FPP3)**  
https://otexts.com/fpp3/

Usage : séries temporelles, décomposition, ETS, ARIMA, régression temporelle, validation, résidus, forecasting probabiliste.

### Complément pratique
**Applied Forecasting — ETC3550/5550**  
https://af.numbat.space/

Usage : exercices et mise en pratique structurée.

### Implémentation Python
**Forecasting: Principles and Practice — The Pythonic Way**  
https://otexts.com/fpppy/

Usage : transposer les concepts en Python sans refaire tout le parcours en double.

### Approfondissement plus tard
**ADAM — Forecasting Book**  
https://www.openforecast.org/adam/

Usage : modèles statistiques avancés après maîtrise d'ETS / ARIMA / probabiliste.

---

## 6. Machine Learning

### Ressource principale
**An Introduction to Statistical Learning — Python (ISLP)**  
https://www.statlearning.com/

Usage : régression, régularisation, arbres, ensembles, resampling, généralisation et principes ML.

Attention : pour les séries temporelles, les exemples de validation aléatoire doivent être adaptés à une validation chronologique.

### Référence technique
Documentation officielle scikit-learn.

---

## 7. Feature engineering

### Ressource principale
**Feature Engineering and Selection — Max Kuhn & Kjell Johnson**  
https://bookdown.org/max/FES/

Usage : transformations, encodage, sélection et raisonnement sur les features.

### Complément
**Feature Engineering A-Z**

Usage : exemples supplémentaires lorsque nécessaire.

Pour le forecasting, priorité aux lags, rolling features, variables calendaires, prix / promotions et surtout à la disponibilité réelle des features au forecast origin.

---

## 8. Supply Chain / Demand Forecasting

### Ressource principale
**Data Science for Supply Chain Forecasting — Nicolas Vandeput**

Usage : lien entre data science, prévision de demande et problématiques SCM.

### Complément
**Demand Forecasting Best Practices — Nicolas Vandeput**

Usage : processus de demand planning, pratiques métier, limites et adoption des prévisions.

---

## 9. Software engineering / pipeline

### Ressources principales
- documentation Python officielle ;
- documentation pytest ;
- documentation Git ;
- documentation Docker.

Usage : fonctions / modules, tests, environnements, packaging, logs, CLI, conteneurisation.

La documentation officielle est privilégiée ici aux cours longs : chaque notion est apprise au moment où elle est intégrée au pipeline.

---

## 10. MLOps / orchestration / tracking

### Références principales
- **MLflow documentation** — experiment tracking / model lifecycle ;
- **Prefect documentation** — orchestration ;
- documentation de l'outil de monitoring utilisé dans le projet.

Usage : uniquement après existence d'un pipeline reproductible.

---

## 11. Scale / data engineering / cloud

### Références principales
- documentation Apache Parquet ;
- documentation DuckDB ;
- documentation Apache Spark / PySpark ;
- documentation Databricks ;
- documentation AWS pour les services réellement utilisés.

Règle : **mesurer d'abord le temps et la mémoire localement**. Spark, PySpark ou Databricks ne sont étudiés en profondeur que si le volume ou le SLA le justifie.

---

## 12. Deep learning / modèles pré-entraînés — Optional

### Référence principale
**PyTorch official tutorials**

Usage : tensors, autograd, optimisation et réseaux neuronaux si ce bloc est activé.

### Outils / bibliothèques à évaluer plus tard
- GluonTS ;
- Nixtla ;
- TimeGPT / modèles foundation time series.

Ils doivent être benchmarkés contre les baselines statistiques et ML existantes.

---

## 13. Reverse engineering / veille

Sources possibles :

- solutions publiques M5 ;
- notebooks Kaggle ;
- repositories GitHub de forecasting ;
- implementations Nixtla ;
- papers ciblés ;
- documentations industrielles / engineering blogs.

Chaque lecture doit produire au moins un résultat concret :

- idée à tester ;
- hypothèse à vérifier ;
- skill manquante ;
- issue GitHub ;
- erreur détectée ;
- décision argumentée de ne pas reprendre l'approche.

---

# Ressources actives au démarrage

Pour le premier bloc, ne pas ouvrir dix ressources.

1. **Think Stats 3e** — principal ;
2. **Python Data Science Handbook / pandas docs** — uniquement pour appliquer sur M5 ;
3. **SBA** — seulement si une notion statistique reste floue.

FPP3, ISLP, Vandeput, ADAM, PyTorch, Databricks, etc. restent fermés tant que le bloc correspondant n'est pas atteint ou qu'un besoin concret ne les rend nécessaires.
