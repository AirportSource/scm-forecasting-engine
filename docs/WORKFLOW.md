# Learning Flow & Build Loop

Ce document explique **comment naviguer dans le système d'apprentissage** et comment transformer la roadmap en travail concret.

## 1. Learning Flow global

```text
                         ROADMAP.md
                 vision + jalon du moment
                              |
                              v
                      LEARNING_PATH.md
                ordre logique des notions
                              |
                              v
                         SKILLS.md
              base de données des compétences
                              |
                              v
                  sélectionner uniquement
             les skills utiles au jalon actuel
                              |
                              v
                      GITHUB PROJECT
              créer / choisir les issues utiles
                              |
                              v
                     THIS WEEK (3–5)
                              |
                              v
                         IN PROGRESS
                              |
                              v
              +---------------+---------------+
              |                               |
         JE SAIS FAIRE                    JE BLOQUE
              |                               |
              |                               v
              |                        APPRENTISSAGE
              |                   cours / livre / doc ciblée
              |                               |
              |                               v
              |                         PETIT EXERCICE
              |                      sans copier la solution
              |                               |
              +---------------+---------------+
                              |
                              v
                         PROJET M5
                   application sur cas réel
                              |
                              v
                    TESTER / INTERPRÉTER
                              |
                              v
                            COMMIT
                              |
                              v
                        PREUVE OBTENUE
                              |
                   +----------+----------+
                   |                     |
                   v                     v
             issue -> DONE       mise à jour SKILLS.md
                                        |
                                        v
                                LEARNING_LOG.md
                                        |
                                        v
                              prochaine issue utile
```

### Rôle de chaque élément

- **`ROADMAP.md`** : dit **où aller** sur plusieurs mois et quel résultat viser.
- **`LEARNING_PATH.md`** : dit **dans quel ordre apprendre** les grands blocs pour conserver une continuité logique.
- **`SKILLS.md`** : sert de **base de données de compétences**. Il ne définit pas à lui seul l'ordre d'apprentissage.
- **GitHub Project** : transforme le jalon et les skills actives en **travail concret de la semaine**.
- **Issues** : décrivent une production ou une preuve observable, pas simplement « lire un chapitre ».
- **`LEARNING_LOG.md`** : conserve une trace légère des apprentissages, difficultés et décisions.

## 2. Fil conducteur des connaissances

Le parcours principal reste volontairement linéaire :

```text
STATS DESCRIPTIVES + DATA
          |
          v
     PROBABILITÉS
          |
          v
       INFÉRENCE
          |
          v
CALCULUS + ALGÈBRE LINÉAIRE ESSENTIELS
          |
          v
     TIME SERIES
          |
          v
     BACKTESTING
          |
          v
 MODÈLES STATISTIQUES
          |
          v
 MACHINE LEARNING
          |
          v
 FEATURE ENGINEERING
          |
          v
FORECASTING PROBABILISTE + SCM
          |
          v
 SOFTWARE ENGINEERING
          |
          v
 MLOPS / CLOUD / SCALE
          |
          v
DEEP LEARNING / ETA / AGENTS
```

M5 accompagne ce parcours dès le début : il devient progressivement plus sophistiqué à mesure que les connaissances augmentent.

```text
Stats descriptives       -> EDA M5
Probabilités              -> distributions / incertitude des données
Inférence                 -> estimation / variabilité / régression
Time Series               -> structure temporelle M5
Backtesting               -> validation sans leakage
Modèles statistiques      -> ETS / ARIMA / baselines
Machine Learning          -> LightGBM / XGBoost
Forecast probabiliste     -> quantiles / intervalles
SCM                       -> décisions de stock
Engineering               -> pipeline automatisé
MLOps / Scale             -> exploitation et montée en charge
```

## 3. Boucle d'une tâche

Le projet suit ensuite une boucle très simple : apprendre uniquement ce qui est nécessaire pour avancer, appliquer, tester et valider avant de passer à la suite.

```text
                    GITHUB PROJECT
                         |
                 prochaine tâche
                         v
                 J'ESSAIE DE FAIRE
                         |
             +-----------+-----------+
             |                       |
        JE SAIS FAIRE           JE BLOQUE
             |                       |
             |                       v
             |               APPRENTISSAGE
             |                cours / doc
             |                       |
             |                       v
             |                   EXERCICE
             |                       |
             +-----------+-----------+
                         v
                        M5
                         |
                         v
                     TESTER
                         |
                         v
                      COMMIT
                         |
                         v
                   PREUVE OBTENUE
                         |
                         v
                       DONE
                         |
                         v
                prochaine tâche
```

## 4. Règle de fonctionnement

1. Regarder le **jalon actuel** dans `ROADMAP.md`.
2. Vérifier dans `LEARNING_PATH.md` quelle est la prochaine étape logique.
3. Chercher dans `SKILLS.md` les compétences correspondant à cette étape.
4. N'activer qu'un petit ensemble de compétences réellement utiles maintenant.
5. Transformer ces compétences en 3 à 5 issues concrètes pour la semaine.
6. Essayer de réaliser l'issue avant d'ouvrir de nouvelles ressources.
7. En cas de blocage, identifier précisément la notion manquante.
8. Apprendre cette notion avec une ressource ciblée, puis faire un petit exercice.
9. Revenir immédiatement au projet M5 et appliquer la notion.
10. Tester techniquement le résultat et vérifier qu'il peut être expliqué.
11. Faire un commit clair.
12. Mettre l'issue en `Done` seulement lorsque la preuve attendue existe.
13. Mettre à jour `SKILLS.md` uniquement lorsqu'une progression est réellement démontrée.
14. En fin de semaine, choisir les prochaines issues en fonction de ce qui a réellement été acquis.

## 5. Définition de « preuve obtenue »

Une tâche n'est pas terminée uniquement parce que le code s'exécute. Selon la tâche, la preuve doit couvrir au moins une partie de ces trois dimensions :

- **Compréhension** : je peux expliquer ce que je fais et pourquoi.
- **Réalisation** : le résultat fonctionne et peut être reproduit.
- **Transfert** : je peux réutiliser la compétence sur une variante, une autre série ou un autre problème.

## 6. Principe d'apprentissage

La roadmap donne la direction, `LEARNING_PATH.md` impose une continuité logique, `SKILLS.md` conserve la carte complète des compétences et le GitHub Project ne contient que le travail utile à court terme.

Le planning reste court : les connaissances sont consolidées par le rappel actif, les exercices, la reproduction sans notes et surtout leur réutilisation dans le projet.
