# Budget temps — 12 mois

Ce fichier chiffre le plan pour détecter tôt les dérives.

## Capacité

- capacité maximale disponible : **48 h/semaine** ;
- charge planifiée : **40 h/semaine** ;
- buffer : **8 h/semaine** pour bugs, fatigue, rendez-vous, rappel, retard et imprévus ;
- **46 semaines actives planifiées** ;
- **6 semaines non engagées** pour congés, maladie, dérive ou approfondissement.

Le budget de travail planifié est donc d'environ **1 840 h**. On ne planifie jamais 48 h parfaites toutes les semaines.

## Allocation par bloc

Les numéros sont identiques à `LEARNING_PATH.md`.

| Bloc | Sujet | Budget | Heures |
|---|---|---:|---:|
| B1 | Stats descriptives + Data / EDA | 3 sem. | 120 h |
| B2 | Probabilités | 3 sem. | 120 h |
| B3 | Inférence statistique | 3 sem. | 120 h |
| B4 | Calculus + algèbre linéaire essentiels | 2 sem. | 80 h |
| B5 | Fondamentaux séries temporelles | 4 sem. | 160 h |
| B6 | Validation / backtesting | 3 sem. | 120 h |
| B7 | Modèles statistiques | 4 sem. | 160 h |
| B8 | Machine Learning | 5 sem. | 200 h |
| B9 | Feature engineering temporel | 3 sem. | 120 h |
| B10 | Forecast probabiliste + SCM | 4 sem. | 160 h |
| B11 | Software engineering / pipeline | 4 sem. | 160 h |
| B12 | MLOps / cloud / scale | 5 sem. | 200 h |
| B13 | Transfert / spécialisation | 3 sem. | 120 h |
| **Total** | | **46 sem.** | **1 840 h** |

Les budgets sont des plafonds de planification, pas des heures à consommer obligatoirement. Si le checkpoint est réussi plus tôt, on avance.

## Diagnostic initial

Les niveaux de `SKILLS.md` ne doivent pas être interprétés comme un niveau réel tant qu'ils n'ont pas été vérifiés. Les compétences déjà opérationnelles réduisent le temps du bloc correspondant et libèrent du budget pour l'engineering, le probabiliste ou le transfert.

## Timebox et dette

Chaque bloc possède un checkpoint dans `docs/CHECKPOINTS.md`.

- premier échec : 8 à 12 h de travail ciblé puis un retry ;
- bloc Core encore fragile : prolongation maximum d'une semaine, puis décision explicite ;
- un manque non bloquant peut devenir une issue `[DEBT]` dans le backlog ;
- un manque bloquant n'est pas repoussé si le bloc suivant en dépend directement.

### Hard gate

**B6 — validation / backtesting** ne peut pas être contourné : pas de passage aux benchmarks avancés avec un doute sérieux sur le leakage, les origines de forecast ou le calcul des métriques.

Pour les autres blocs, on distingue :
- **noyau bloquant** : nécessaire au bloc suivant → consolidation obligatoire ;
- **détail non bloquant** : documenté en dette puis revu lorsqu'il redevient utile.

## Suivi mensuel

| Mois | Heures planifiées | Heures réelles | Écart cumulé | Bloc en cours | Version atteinte |
|---|---:|---:|---:|---|---|
| M1 | 160 | | | | |
| M2 | 160 | | | | |
| M3 | 160 | | | | |
| M4 | 160 | | | | |
| M5 | 160 | | | | |
| M6 | 160 | | | | |
| M7 | 160 | | | | |
| M8 | 160 | | | | |
| M9 | 160 | | | | |
| M10 | 160 | | | | |
| M11 | 120 | | | | |
| M12 | 120 | | | | |

Les mois sont indicatifs. Les **budgets par bloc + checkpoints** font foi.

## Règle de dérive

- < 1 jour : buffer hebdomadaire ;
- 1–3 jours : supprimer stretch tasks et lectures optionnelles ;
- > 1 semaine : décaler le calendrier, sans compresser le Core ;
- > 25 % de dérive sur un mois : réduire le scope Optional/Support avant d'augmenter les heures.

Ordre de coupe : **agents → deep learning/foundation models → ETA avancé → Spark/Databricks avancés**.
