# Roadmap globale

Cette roadmap donne la direction sur environ 12 mois. Elle n'est pas un planning journalier fixe.

## Règle de gel

La structure de cette roadmap est désormais considérée comme **figée**.

On ne la modifie pas à chaque difficulté ou nouvelle idée. Les ajustements se font d'abord dans les issues et dans le planning hebdomadaire. Une modification structurelle de la roadmap n'est envisagée qu'en revue mensuelle si une hypothèse de départ est clairement devenue fausse.

---

# Cible professionnelle

## Rôle principal

**Forecasting Data Scientist / Applied ML Engineer spécialisé SCM**

L'objectif n'est pas de devenir simultanément Data Scientist, Data Engineer, MLE, chercheur deep learning et spécialiste agents. Le cœur du parcours est la prévision appliquée à la Supply Chain, avec assez d'engineering pour construire et exploiter un système réel.

## Core — obligatoire

- statistiques descriptives, probabilités et inférence ;
- calculus et algèbre linéaire essentiels ;
- Python et SQL ;
- EDA et qualité des données ;
- séries temporelles ;
- validation temporelle / backtesting / leakage ;
- modèles statistiques de forecasting ;
- machine learning et feature engineering ;
- forecasting probabiliste ;
- concepts SCM : demande, stock, service level, lead time, hiérarchies ;
- software engineering de base : fonctions, modules, tests, logs, configuration, Git ;
- pipeline reproductible et automatisé.

## Support — compétence opérationnelle, pas expertise senior requise

- R / fable comme environnement analytique complémentaire ;
- Docker ;
- orchestration ;
- experiment tracking ;
- monitoring ;
- cloud ;
- Parquet / DuckDB / formats colonne ;
- Spark / PySpark / Databricks si les mesures de volume le justifient ;
- CI/CD de base.

## Optional — spécialisations à couper en premier si le planning dérive

1. agents IA avancés ;
2. deep learning / foundation models avancés ;
3. ETA temps réel avancé ;
4. Databricks / Spark avancés au-delà du besoin démontré.

Les blocs Core ne sont pas sacrifiés pour conserver un bloc Optional.

---

# Capacité et budget

## Hypothèse de travail

- capacité disponible : **48 h / semaine** (8 h × 6 jours) ;
- charge planifiée : **40 h / semaine** ;
- buffer : **8 h / semaine** pour bugs, retard, fatigue, rendez-vous, révisions et imprévus ;
- environ **46 semaines actives** planifiées ;
- environ **6 semaines non engagées** sur l'année pour congés, maladie, dérive ou approfondissement.

Les heures ci-dessous sont des **budgets cibles**, pas des quotas à remplir. Un bloc peut finir plus tôt si la preuve est obtenue. Un bloc Core peut être prolongé si le checkpoint échoue.

| Bloc | Budget cible | Heures planifiées | Résultat principal |
|---|---:|---:|---|
| 1. Stats descriptives + Data / EDA | 3 sem. | 120 h | EDA M5 correcte et reproductible |
| 2. Probabilités | 3 sem. | 120 h | Raisonnement probabiliste opérationnel |
| 3. Inférence statistique | 3 sem. | 120 h | Estimation, incertitude et régression comprises |
| 4. Calculus + algèbre linéaire essentiels | 2 sem. | 80 h | Dérivées, gradients et matrices suffisants pour le ML |
| 5. Fondamentaux séries temporelles | 4 sem. | 160 h | Structure temporelle analysée correctement |
| 6. Backtesting / évaluation | 3 sem. | 120 h | Backtest rolling-origin sans leakage |
| 7. Modèles statistiques | 4 sem. | 160 h | Benchmark naïf / ETS / ARIMA reproductible |
| 8. Machine Learning | 5 sem. | 200 h | Modèle ML comparé proprement aux baselines |
| 9. Feature engineering temporel | 3 sem. | 120 h | Features point-in-time correctes + ablations |
| 10. Forecast probabiliste + SCM | 4 sem. | 160 h | Quantiles / calibration + simulation décisionnelle |
| 11. Software engineering / pipeline | 4 sem. | 160 h | Pipeline exécutable hors notebook avec tests / logs |
| 12. MLOps / cloud / scale | 5 sem. | 200 h | Tracking, monitoring et limites de scale mesurées |
| 13. Transfert / spécialisation | 3 sem. | 120 h | Réutilisation sur autre dataset, ETA ou autre extension |
| **Total planifié** | **46 sem.** | **1 840 h** | |

---

# Checkpoints objectifs et timeboxés

## Règle commune

Chaque bloc se termine par une épreuve datée, enregistrée dans le repo ou dans le learning log.

Conditions générales :

- sans notes pour la partie de compréhension ;
- exemple ou série différente de ceux utilisés pendant l'apprentissage ;
- durée limitée ;
- résultat vérifiable ;
- pas de copier-coller depuis l'exercice précédent ;
- pour les blocs de forecasting : aucune fuite temporelle tolérée.

### Score de passage

Checkpoint noté sur 5 dimensions :

1. exactitude conceptuelle ;
2. exactitude technique ;
3. interprétation ;
4. reproductibilité ;
5. transfert sur un cas nouveau.

**Passage : 4/5 minimum**, sans erreur critique de type leakage, jointure incorrecte, cible mal définie ou résultat techniquement faux.

En cas d'échec : revue ciblée pendant 24–48 h puis **un retry**. Après deux échecs, un bloc Core peut être prolongé d'une semaine maximum avant réévaluation. Pour un bloc Support / Optional, on réduit le scope ou on reporte.

| Bloc | Checkpoint de sortie | Timebox |
|---|---|---:|
| Stats descriptives + Data | EDA de 3 séries M5 non utilisées auparavant : granularité, moyenne/médiane, dispersion, quantiles, anomalies, interprétation écrite | 2 h |
| Probabilités | Série de problèmes mixtes + simulation Python : conditionnelle, indépendance, VA, espérance, variance, lois usuelles | 90 min |
| Inférence | Construire et interpréter estimation / SE / IC sur un échantillon nouveau + expliquer une p-value et ses limites | 90 min |
| Calculus + algèbre | Dériver des fonctions simples, calculer un gradient de MSE simple et effectuer les opérations matricielles de base sans notes | 75 min |
| Time Series | Diagnostiquer une série inconnue : tendance, saisonnalité, lags, ACF, stationnarité, transformation / différenciation justifiée | 2 h |
| Backtesting | Reconstruire un rolling-origin simple sur petit jeu de données et prouver l'absence de fuite sur quelques prédictions | 2 h |
| Modèles statistiques | Comparer seasonal naïve, ETS et ARIMA avec exactement le même protocole de backtest et expliquer le gagnant | 3 h |
| Machine Learning | Entraîner un modèle tabulaire sur split temporel correct, comparer à la baseline et expliquer overfit / généralisation | 3 h |
| Feature engineering | Construire lags / rolling / calendrier point-in-time corrects et faire une petite ablation de features | 3 h |
| Probabiliste + SCM | Produire plusieurs quantiles, mesurer calibration / pinball et les utiliser dans une simulation stock simple | 3 h |
| Software engineering | Lancer le pipeline depuis une commande hors notebook ; tests essentiels, logs, config et sortie reproductible | 3 h |
| MLOps / cloud / scale | Rejouer une expérience tracée, détecter un échec simulé et mesurer temps / mémoire sur un volume supérieur | 4 h |
| Transfert | Réutiliser le socle sur un second contexte sans recopier l'implémentation M5 telle quelle | 4 h |

---

# Protocole Recovery / Drift

Ce protocole évite de compenser un retard par des journées infinies ou par la suppression silencieuse des fondations.

- **Retard < 1 jour** : absorbé par le buffer hebdomadaire. Rien ne change dans la roadmap.
- **Retard de 1 à 3 jours** : supprimer les tâches stretch / lectures optionnelles de la semaine ; conserver le jalon Core.
- **Retard > 1 semaine** : décaler le calendrier. Ne pas compresser un bloc Core pour « rattraper » une date.
- **Blocage technique > 4 h** : arrêter de tourner en rond ; produire un exemple minimal, lire la doc / une implémentation de référence, isoler le bug et créer une sous-issue si nécessaire.
- **Checkpoint raté 2 fois** : prolonger un bloc Core d'une semaine maximum, puis réévaluer ; pour Support / Optional, réduire ou reporter.
- **Dérive mensuelle > 25 % du budget** : couper du scope, pas augmenter les heures. Ordre de coupe : agents → deep learning / foundation models → ETA avancé → Spark / Databricks avancés.
- **Maladie / interruption longue** : reprise par un checkpoint court du dernier bloc validé avant de poursuivre. Pas de tentative de « rattrapage » massif.

---

# Jalons fonctionnels

## 1. Cadrage du problème SCM
- cible ;
- granularité ;
- horizon ;
- fréquence de recalcul ;
- informations disponibles ;
- critères métier.

**Preuve attendue :** définition claire du problème et de l'usage des prévisions.

## 2. Données, statistiques et exploration temporelle
- Python / SQL ;
- qualité et jointures ;
- distributions, dispersion, quantiles ;
- visualisation ;
- tendance, saisonnalité et dépendance temporelle.

**Preuve attendue :** données contrôlées et analyse expliquée.

## 3. Références et validation
- naïve et saisonnière ;
- erreurs et biais ;
- rolling-origin backtesting ;
- horizons ;
- leakage ;
- séparation développement / test.

**Preuve attendue :** backtesting reproductible sur plusieurs séries.

## 4. Première chaîne complète
- fonctions ;
- configuration ;
- tests ;
- logs ;
- sauvegarde ;
- exécution hors notebook.

**Preuve attendue :** pipeline V0 exécutable avec un modèle simple.

## 5. Modèles statistiques et ML
- régression ;
- ETS ;
- ARIMA / SARIMA ;
- arbres ;
- gradient boosting ;
- feature engineering ;
- stratégies multi-horizons.

**Preuve attendue :** benchmark commun et défendable.

## 6. Incertitude et décisions SCM
- quantiles ;
- prediction intervals ;
- calibration ;
- pinball loss ;
- demande intermittente ;
- hiérarchies ;
- simulation stock.

**Preuve attendue :** évaluation de l'incertitude et de son intérêt décisionnel.

## 7. Déploiement et exploitation
- scheduling ;
- experiment tracking ;
- monitoring ;
- retries ;
- permissions ;
- fallback ;
- documentation.

**Preuve attendue :** système qui s'exécute régulièrement et incidents diagnostiquables.

## 8. Performance et passage à l'échelle
- temps et mémoire ;
- formats colonne ;
- batch processing ;
- parallélisation ;
- calcul distribué ;
- coûts.

**Preuve attendue :** limites et capacités mesurées.

## 9. Transfert et spécialisations
- autre dataset de demande ;
- ETA ;
- agents d'expérimentation ;
- modèles neuronaux ou pré-entraînés selon besoin.

**Preuve attendue :** réutilisation du socle sur un problème différent.

---

# Calendrier mensuel indicatif

Ce tableau sert uniquement de repère. Les **budgets par bloc et les checkpoints priment sur le numéro du mois**.

| Mois | Direction principale |
|---|---|
| M1 | Stats descriptives + EDA + Python/SQL |
| M2 | Probabilités + inférence statistique |
| M3 | Calculus / algèbre essentiels + début Time Series |
| M4 | Time Series + backtesting |
| M5 | Modèles statistiques |
| M6 | Machine Learning |
| M7 | Feature engineering + ML forecasting |
| M8 | Forecast probabiliste + SCM |
| M9 | Software engineering + pipeline |
| M10 | MLOps / cloud / scale |
| M11 | MLOps / scale + transfert sur second contexte |
| M12 | Consolidation + spécialisation seulement si le Core est solide |
