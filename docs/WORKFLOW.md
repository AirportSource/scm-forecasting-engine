# Learning Flow & Build Loop

Ce document explique **comment naviguer dans le système d'apprentissage**, comment vérifier qu'une compétence est réellement acquise et comment transformer la roadmap en travail concret.

Le système contient volontairement **deux boucles différentes** :

1. une **Learning Loop globale**, qui fait progresser les connaissances dans un ordre logique ;
2. une **Build Loop locale**, utilisée pour chaque issue / expérimentation dans le projet M5.

La revue de littérature et le reverse engineering de repositories publics alimentent les deux boucles.

---

# 1. Learning Flow global

Le parcours de connaissance ne consiste pas simplement à faire une issue puis passer à la suivante. Chaque bloc doit être **compris, appliqué, vérifié et transféré** avant de considérer qu'il est suffisamment solide pour avancer.

```text
                         ROADMAP.md
                 vision + jalon du moment
                              |
                              v
                      LEARNING_PATH.md
                 prochain bloc logique
                              |
                              v
                         SKILLS.md
              compétences associées au bloc
                              |
                              v
                 APPRENTISSAGE STRUCTURÉ
             livre / cours / documentation
                              |
                              v
                      PETITS EXERCICES
                calcul / code / explication
                              |
                              v
                         PROJET M5
                  application sur cas réel
                              |
                              v
                TESTER + INTERPRÉTER
                              |
                              v
                    REPRODUIRE / TRANSFÉRER
              autre série / autre exemple
                              |
                              v
                    +---------+---------+
                    |                   |
               VALIDÉ ? NON          OUI
                    |                   |
                    v                   v
              DIAGNOSTIQUER        PREUVE OBTENUE
                    |                   |
          +---------+---------+         v
          |                   |    mise à jour
   problème conceptuel   problème code       SKILLS.md
          |                   |              |
          v                   v              v
   cours / littérature    debug / tests   LEARNING_LOG.md
   exercice ciblé         docs / refactor     |
          |                   |              v
          +---------+---------+       BLOC SUIVANT
                    |
                    +-------> retour M5
```

## Ce que signifie « validé »

Une compétence n'est pas validée uniquement parce que le notebook tourne.

Elle doit passer trois contrôles :

- **Correction conceptuelle** : je peux expliquer ce que la méthode mesure / suppose / produit et confronter mon interprétation à une source fiable.
- **Correction technique** : le code passe des contrôles simples, produit des résultats plausibles et ne dépend pas d'une erreur silencieuse.
- **Transfert** : je peux reproduire l'idée sur une autre série, un autre petit dataset ou un exemple reconstruit sans copier mon premier notebook.

Si un de ces trois contrôles échoue, **je reste dans le bloc actuel** et je boucle. Je ne monte pas artificiellement le niveau dans `SKILLS.md`.

---

# 2. Fil conducteur des connaissances

Le parcours principal reste volontairement continu :

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
Calculus / algèbre        -> optimisation / loss / gradients
Time Series               -> structure temporelle M5
Backtesting               -> validation sans leakage
Modèles statistiques      -> ETS / ARIMA / baselines
Machine Learning          -> LightGBM / XGBoost
Feature engineering       -> lags / rolling / calendrier / prix
Forecast probabiliste     -> quantiles / intervalles
SCM                       -> décisions de stock
Engineering               -> pipeline automatisé
MLOps / Scale             -> exploitation et montée en charge
```

---

# 3. Boucle de revue de littérature & reverse engineering

La lecture de littérature, de documentation, de notebooks et de repositories publics n'est **pas une activité séparée du projet**. C'est une boucle d'inspiration et de contrôle qui alimente le backlog et remet en question les choix déjà faits.

```text
                 PROBLÈME / BLOC ACTUEL
                          |
                          v
                PREMIÈRE COMPRÉHENSION
                + tentative personnelle
                          |
                          v
              REVUE CIBLÉE DE SOURCES
        livres / papers / docs / repos publics
                          |
                          v
                 EXTRAIRE LES IDÉES
       hypothèses / patterns / features / méthodes
                          |
                          v
                 COMPARER À MON APPROCHE
                          |
              +-----------+-----------+
              |                       |
       idée non comprise         idée pertinente
              |                       |
              v                       v
      notion à apprendre        issue / expérience
              |                       |
              +-----------+-----------+
                          |
                          v
                     TESTER SUR M5
                          |
                          v
                 mesurer / interpréter
                          |
                          v
                garder / rejeter / adapter
                          |
                          +------> nouvelle revue
```

## Deux moments différents pour lire les autres

### A. Au début d'un bloc : littérature de fond

Objectif : comprendre les concepts et le vocabulaire avec **une ou deux sources de référence**.

Exemples : Think Stats, FPP3, documentation officielle, ouvrage SCM.

### B. Après une première tentative personnelle : reverse engineering

Objectif : comparer sa propre approche à des approches plus avancées sans tomber dans le copier-coller.

Exemples :

- solutions publiques M5 ;
- notebooks de compétition ;
- repositories Nixtla / forecasting ;
- papers pertinents ;
- implementations industrielles documentées.

La règle est :

> **essayer / comprendre d'abord suffisamment pour avoir un point de comparaison, puis étudier les autres pour élargir, corriger ou challenger son approche.**

Une lecture utile doit produire au moins un des résultats suivants :

- une hypothèse à tester ;
- une nouvelle skill à apprendre ;
- une issue à ajouter au backlog ;
- une erreur ou faiblesse détectée dans l'approche actuelle ;
- une décision argumentée de ne pas utiliser la méthode étudiée.

---

# 4. Build Loop d'une issue projet

Cette boucle est **locale**. Elle sert à réaliser une tâche concrète, mais elle ne remplace pas la Learning Loop globale.

```text
                    GITHUB PROJECT
                         |
                 prochaine issue
                         v
                 J'ESSAIE DE FAIRE
                         |
             +-----------+-----------+
             |                       |
        JE SAIS FAIRE           JE BLOQUE
             |                       |
             |                       v
             |                 DIAGNOSTIC
             |               qu'est-ce qui manque ?
             |                       |
             |           +-----------+-----------+
             |           |                       |
             |      connaissance             technique
             |           |                       |
             |           v                       v
             |     cours / doc / paper       debug / tests
             |     + petit exercice          docs / inspection
             |           |                       |
             +-----------+-----------+-----------+
                         |
                         v
                        M5
                         |
                         v
                TESTER / INTERPRÉTER
                         |
                         v
              REPRODUIRE SUR AUTRE CAS
                         |
                         v
                    +----+----+
                    |         |
                  ÉCHEC      OK
                    |         |
                    v         v
                DIAGNOSTIC   COMMIT
                    |         |
                    +---<-----+ si preuve insuffisante
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
```

## Cas d'échec à traiter explicitement

### Le code bug

Ne pas apprendre une nouvelle théorie par réflexe. D'abord :

- lire l'erreur ;
- réduire le problème ;
- vérifier types / dimensions / index / jointures ;
- construire un exemple minimal ;
- comparer à la documentation ;
- ajouter un test si le bug peut revenir.

### Le code tourne mais le résultat semble faux

Faire des **sanity checks** :

- quelques calculs à la main ;
- cas jouet dont on connaît le résultat ;
- ordre de grandeur ;
- comparaison avec une baseline simple ;
- inspection d'observations précises.

### Je ne sais pas interpréter le résultat

Retour à la théorie / littérature. Écrire avec ses mots :

- ce que mesure le résultat ;
- ce qu'il ne permet pas de conclure ;
- quelles hypothèses sont nécessaires ;
- quelle décision éventuelle il pourrait éclairer.

### Je réussis sur une série mais pas sur une autre

C'est précisément un test de transfert. Identifier ce qui change :

- échelle ;
- zéros ;
- saisonnalité ;
- tendance ;
- valeurs atypiques ;
- longueur d'historique ;
- disponibilité des variables.

La différence entre les séries devient alors une nouvelle source d'apprentissage.

---

# 5. Passage hebdomadaire : du jalon aux issues

```text
ROADMAP.md
   |
   v
jalon du mois
   |
   v
LEARNING_PATH.md
   |
   v
bloc logique actuel
   |
   v
SKILLS.md
   |
   v
sélection de 5–10 skills actives maximum
   |
   v
GitHub Project
   |
   v
3–5 issues pour THIS WEEK
   |
   v
Build Loop quotidienne
   |
   v
revue samedi
   |
   +--> acquis -> prochaine étape
   |
   +--> fragile -> nouvelle boucle / nouvelle preuve
```

Le samedi sert à répondre à quatre questions :

1. Qu'est-ce que je peux réellement expliquer sans notes ?
2. Qu'est-ce que j'ai réellement produit ?
3. Qu'est-ce qui reste fragile ou faux ?
4. Quelle est la prochaine étape logique dans `LEARNING_PATH.md` ?

---

# 6. Règles de fonctionnement

1. Regarder le **jalon actuel** dans `ROADMAP.md`.
2. Vérifier dans `LEARNING_PATH.md` quelle est la prochaine étape logique.
3. Chercher dans `SKILLS.md` les compétences correspondant à cette étape.
4. N'activer qu'un petit ensemble de compétences réellement utiles maintenant.
5. Transformer ces compétences en 3 à 5 issues concrètes pour la semaine.
6. Apprendre les fondamentaux du bloc avec une source structurée.
7. Faire des exercices courts sans suivre mécaniquement la solution.
8. Appliquer rapidement la notion à M5.
9. Tester le code **et** l'interprétation.
10. Reproduire sur une autre série ou un autre exemple avant de considérer la compétence solide.
11. Si cela échoue, diagnostiquer : problème conceptuel, problème technique ou limite de la méthode.
12. Utiliser littérature / documentation / repositories publics pour comprendre, comparer et inspirer de nouveaux tests.
13. Faire un commit clair lorsqu'un incrément utile existe ; un commit ne signifie pas automatiquement que la skill est validée.
14. Mettre une issue en `Done` seulement lorsque sa preuve attendue existe.
15. Mettre à jour `SKILLS.md` uniquement lorsqu'une progression est réellement démontrée.
16. En fin de semaine, adapter les prochaines issues en fonction de ce qui a réellement été acquis.

---

# 7. Définition de « preuve obtenue »

Une preuve solide combine idéalement :

- **Compréhension** : je peux expliquer la notion, ses hypothèses et ses limites.
- **Réalisation** : mon code / analyse fonctionne et peut être reproduit.
- **Vérification** : j'ai fait des contrôles indépendants pour réduire le risque d'une erreur silencieuse.
- **Transfert** : je peux réutiliser la compétence sur une autre série, un autre échantillon ou une variante.

Le niveau 3 dans `SKILLS.md` correspond donc à beaucoup plus que « je l'ai déjà fait une fois ».

---

# 8. Principe général

La roadmap donne la direction.

`LEARNING_PATH.md` impose une continuité logique.

`SKILLS.md` est la base de données des compétences.

La **Learning Loop** garantit que l'apprentissage est compris et transférable.

La **Build Loop** transforme cet apprentissage en système réel.

La **revue de littérature et de repositories** apporte de nouvelles idées, révèle des erreurs et empêche de réinventer inutilement ce que d'autres ont déjà appris.

Le but n'est donc pas de parcourir des ressources ou de fermer des issues le plus vite possible, mais de construire progressivement un système de forecasting que je peux **comprendre, défendre, reproduire, améliorer et transférer**.
