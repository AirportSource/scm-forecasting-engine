# Learning Flow, Practice Loop & Research Loop

Ce document sépare volontairement **trois mécanismes différents**, mais connectés :

1. **Boucle d'apprentissage** : construire et consolider une compétence théorique / technique.
2. **Boucle pratique projet** : faire avancer le moteur de forecasting sur M5, en s'appuyant aussi sur les pratiques et processus déjà utilisés par des personnes expérimentées.
3. **Boucle littérature / reverse engineering** : s'inspirer, comparer, challenger et découvrir de meilleures approches.

Le but est d'éviter de confondre :

- *j'ai lu / compris une notion* ;
- *j'ai vu quelqu'un d'autre le faire* ;
- *j'ai réussi à l'appliquer une fois* ;
- *je sais réellement la reproduire, l'interpréter et la transférer*.

---

# 1. Boucle d'apprentissage

Cette boucle concerne **la connaissance elle-même**. Elle existe même si aucune issue projet n'est en cours.

Elle sert pour les statistiques, probabilités, calculus, time series, ML, SQL, engineering, etc.

```text
                    ROADMAP.md
               jalon du mois actuel
                         |
                         v
                 LEARNING_PATH.md
              prochain bloc logique
                         |
                         v
                    SKILLS.md
             compétences du bloc
                         |
                         v
              APPRENTISSAGE STRUCTURÉ
          livre / cours / documentation
                         |
                         v
              COMPRÉHENSION ACTIVE
       reformuler / expliquer / prédire
                         |
                         v
                PETITS EXERCICES
        calcul manuel / code / questions
                         |
                         v
              REPRODUIRE SANS NOTES
                         |
                         v
                RAPPEL ESPACÉ
             J+1 / J+3 / J+7...
                         |
                         v
                 TEST DE TRANSFERT
       nouvel exemple / nouvelle variante
                         |
                         v
                  +------+------+ 
                  |             |
             PAS SOLIDE       SOLIDE
                  |             |
                  v             v
             DIAGNOSTIC     PREUVE SKILL
                  |             |
          +-------+-------+     v
          |               |  SKILLS.md
   incompréhension     oubli / manque
          |               |
          v               v
   revenir théorie     rappel ciblé
   + exercice ciblé    + nouvel exercice
          |               |
          +-------+-------+
                  |
                  +-------> retour dans la boucle
```

## Critère de sortie de la boucle d'apprentissage

Une notion n'est pas « acquise » parce que je l'ai lue ou parce qu'un exemple fonctionne.

Je considère qu'elle est suffisamment solide pour avancer lorsque je peux :

- **expliquer** la notion avec mes mots ;
- **faire un exercice simple sans solution sous les yeux** ;
- **reconstruire le raisonnement ou le code essentiel sans copier** ;
- **reconnaître quand la notion est pertinente ou non** ;
- **la transférer sur un nouvel exemple**.

Le niveau peut rester imparfait : on ne cherche pas la maîtrise définitive avant d'avancer. Les notions seront renforcées plus tard par la pratique.

---

# 2. Boucle pratique projet

Cette boucle concerne **la construction réelle du projet M5**.

Elle ne décide pas de tout ce que j'apprends : elle consomme les connaissances de la Learning Loop et révèle de nouveaux besoins.

Le **reverse engineering fait partie de cette boucle pratique** : avant de construire une solution importante, je regarde comment le problème a déjà été abordé par des personnes expérimentées, afin d'identifier les architectures, contrôles, patterns, pièges et processus utiles. Le but n'est pas de copier leur code, mais de ne pas construire dans le vide.

```text
                    GITHUB PROJECT
                         |
                  prochaine issue
                         v
                    CADRER LE BESOIN
          objectif / entrée / sortie / preuve
                         |
                         v
              PREMIÈRE IDÉE PERSONNELLE
          comment je pense m'y prendre ?
                         |
                         v
             REVERSE ENGINEERING CIBLÉ
       repos / notebooks / docs / solutions pro
                         |
                         v
                 EXTRAIRE LES PATTERNS
      architecture / process / contrôles / pièges
                         |
                         v
                CHOISIR CE QUE JE TESTE
        garder / adapter / rejeter / comparer
                         |
                         v
                 CODE / ANALYSE M5
                         |
                         v
                TESTS TECHNIQUES
       types / dimensions / joins / erreurs
                         |
                         v
                  SANITY CHECKS
       calcul manuel / cas jouet / baseline
                         |
                         v
                   INTERPRÉTER
        que signifie réellement le résultat ?
                         |
                         v
              REPRODUIRE / TRANSFÉRER
          autre série / autre période / cas
                         |
                         v
                  +------+------+ 
                  |             |
               ÉCHEC            OK
                  |             |
                  v             v
             DIAGNOSTIC      COMPARER
                  |         aux approches externes
       +----------+---------+   |
       |                    |   v
 problème technique   problème conceptuel
       |                    |   |
       v                    v   |
 debug / tests        BOUCLE    |
 docs / refactor    D'APPRENTISSAGE
       |                    |   |
       +----------+---------+---+
                  |
                  v
          CORRIGER / AMÉLIORER
                  |
           +------+------+
           |             |
     preuve insuffisante  preuve suffisante
           |             |
           v             v
     retour au projet   COMMIT
                         |
                         v
                    PREUVE ISSUE
                         |
                         v
                   issue -> DONE
                         |
                         v
                  LEARNING_LOG.md
```

## Pourquoi le reverse engineering est dans la boucle projet

Pour une issue importante, les questions à poser avant de coder sont :

- Comment des practitioners expérimentés structurent-ils ce type de problème ?
- Quels contrôles font-ils systématiquement ?
- Quelles erreurs essaient-ils d'éviter ?
- Quelle architecture de données ou de code revient souvent ?
- Quelles baselines utilisent-ils avant les modèles complexes ?
- Comment organisent-ils le backtesting, les features, les métriques et les artefacts ?
- Qu'est-ce qui semble spécifique à leur contexte et ne doit pas être copié tel quel ?

Le reverse engineering peut concerner :

- solutions publiques M5 / Kaggle ;
- repositories Nixtla, statsforecast, mlforecast ou autres projets forecasting ;
- code de projets industriels open source ;
- articles techniques et engineering blogs ;
- papers avec implémentation ;
- documentation officielle de librairies.

### Règle anti-copie

Avant de reprendre une idée externe, je dois pouvoir écrire :

1. **quel problème elle résout** ;
2. **pourquoi elle pourrait être utile ici** ;
3. **quelles hypothèses elle fait** ;
4. **comment je vais vérifier qu'elle fonctionne sur M5**.

Une idée externe devient donc une **hypothèse à tester**, pas une vérité à reproduire.

## Une issue n'est pas `Done` si...

- le code tourne mais je ne comprends pas le résultat ;
- l'interprétation est douteuse ;
- le résultat ne passe pas un sanity check ;
- je ne peux pas le reproduire sur une autre série ;
- une fuite de données est possible ;
- j'ai essentiellement copié une solution sans pouvoir l'expliquer ;
- le code casse dès que le cas change légèrement.

## Une issue peut être `Done` quand...

- le résultat attendu existe ;
- le code est raisonnablement reproductible ;
- les contrôles essentiels passent ;
- je peux expliquer le choix réalisé ;
- je sais en quoi mon approche ressemble ou diffère des approches étudiées ;
- les limites sont identifiées ;
- la preuve demandée dans l'issue est satisfaite.

---

# 3. Les deux boucles ensemble

La **Learning Loop** et la **Practice Loop** tournent en parallèle et se nourrissent mutuellement. Le reverse engineering est une passerelle importante entre connaissance externe et construction personnelle.

```text
                         ROADMAP.md
                              |
                              v
                      LEARNING_PATH.md
                              |
                              v
                         SKILLS.md
                              |
               sélection du bloc actuel
                              |
                              v
                 +------------+------------+
                 |                         |
                 v                         v
        BOUCLE APPRENTISSAGE       BOUCLE PRATIQUE M5
                 |                         |
     théorie -> exercices          cadrage de l'issue
     -> rappel -> transfert        -> idée personnelle
                 |                 -> reverse engineering
                 |                 -> code / analyse
                 |                 -> tests / interprétation
                 |                         |
                 +------------+------------+
                              |
                    connaissances appliquées
                              |
                              v
                    VALIDATION CROISÉE
           comprendre + faire + comparer + reproduire
                              |
                  +-----------+-----------+
                  |                       |
                ÉCHEC                     OK
                  |                       |
                  v                       v
         identifier ce qui manque      PREUVE
                  |                       |
        +---------+---------+             v
        |                   |         SKILLS.md
   théorie fragile       bug / méthode      |
        |                   |               v
        v                   v         LEARNING_LOG.md
 Learning Loop       Practice Loop          |
        |                   |               v
        +---------+---------+         prochaine étape
                  |
                  +-------> nouvelle tentative
```

## Relation entre les deux

La logique est :

```text
J'APPRENDS
   ↓
JE M'EXERCE
   ↓
JE CADRE UNE TÂCHE PROJET
   ↓
JE REGARDE COMMENT LES BONS PRACTITIONERS L'ABORDENT
   ↓
JE CHOISIS CE QUE JE VEUX TESTER
   ↓
J'APPLIQUE SUR M5
   ↓
JE TESTE ET J'INTERPRÈTE
   ↓
JE REPRODUIS AILLEURS
   ↓
JE COMPARE / JE CHALLENGE MON APPROCHE
   ↓
JE DÉCOUVRE CE QUI EST ENCORE FRAGILE
   ↓
JE RETOURNE APPRENDRE OU JE CORRIGE LE PROJET
   ↓
JE RE-APPLIQUE
```

Il n'y a donc **pas une seule grande boucle**. Il y a deux boucles autonomes reliées par des passerelles, avec le reverse engineering comme source régulière d'inspiration et de contrôle.

---

# 4. Boucle littérature / reverse engineering

Cette boucle reste transversale aux deux précédentes, mais elle est aussi **explicitement intégrée dans la Practice Loop**.

Elle permet de ne pas apprendre ou construire dans le vide.

```text
                QUESTION / PROBLÈME ACTUEL
                         |
                         v
                TENTATIVE PERSONNELLE
                         |
                         v
               REVUE CIBLÉE DE SOURCES
      livres / papers / docs / notebooks / repos
                         |
                         v
                  EXTRAIRE LES IDÉES
         méthodes / hypothèses / features / patterns
                         |
                         v
                COMPARER À MON APPROCHE
                         |
              +----------+----------+
              |                     |
      notion mal comprise       idée testable
              |                     |
              v                     v
       Learning Loop           nouvelle issue
                                    |
                                    v
                              Practice Loop
                                    |
                                    v
                         garder / rejeter / adapter
```

## Deux usages du reverse engineering

### A. Inspiration avant implémentation

Je regarde des approches existantes pour comprendre :

- comment le problème est découpé ;
- quelles étapes de pipeline reviennent souvent ;
- quels contrôles sont considérés comme standards ;
- quelles baselines et métriques sont utilisées ;
- quelles erreurs ont déjà été rencontrées.

### B. Comparaison après implémentation

Une fois mon approche fonctionnelle, je reviens aux solutions externes pour demander :

- qu'est-ce que j'ai oublié ?
- qu'est-ce que j'ai fait différemment ?
- leur complexité apporte-t-elle une valeur mesurable ?
- mon implémentation est-elle plus fragile ?
- y a-t-il une amélioration qui mérite une nouvelle expérience ?

## Règle de lecture

La revue doit être **ciblée** et produire quelque chose.

Une lecture / un repo est utile s'il mène à au moins un de ces résultats :

- une notion à approfondir ;
- une hypothèse à tester ;
- une issue à créer ;
- une erreur détectée ;
- une meilleure façon de structurer le code ;
- une décision argumentée de ne pas utiliser l'approche observée.

---

# 5. Système complet

```text
                               ROADMAP.md
                                   |
                                   v
                           LEARNING_PATH.md
                                   |
                                   v
                              SKILLS.md
                                   |
                    bloc / compétences actives
                                   |
                 +-----------------+-----------------+
                 |                                   |
                 v                                   v
       BOUCLE APPRENTISSAGE                 BOUCLE PRATIQUE
       théorie / exercices                  projet M5 / issues
       rappel / reproduction                idée personnelle
       transfert                            reverse engineering
                 |                          implémentation / tests
                 |                          interprétation / transfert
                 |                                   |
                 +-----------------+-----------------+
                                   |
                                   v
                         PREUVE / VALIDATION
                                   |
                   +---------------+---------------+
                   |                               |
                 fragile                          solide
                   |                               |
                   v                               v
          retour boucle adaptée              mise à jour skill
                   |                               |
                   |                               v
                   |                        LEARNING_LOG.md
                   |                               |
                   +---------------+---------------+
                                   |
                                   v
                           prochaine étape

         REVUE LITTÉRATURE / REPOS PUBLICS
         <-------------------------------->
          inspire, alimente et challenge la pratique
          + consolide la compréhension théorique
```

---

# 6. Passage du mois à la journée

```text
ROADMAP.md
   |
   v
jalon mensuel
   |
   v
LEARNING_PATH.md
   |
   v
bloc logique
   |
   v
SKILLS.md
   |
   v
skills actives
   |
   +-------------------------+
   |                         |
   v                         v
plan apprentissage      issues GitHub
   |                         |
   v                         v
Learning Loop           Practice Loop
   |                         |
   |                  reverse engineering ciblé
   |                         |
   +------------+------------+
                |
                v
          revue hebdomadaire
                |
                v
     continuer / consolider / avancer
```

Le planning hebdomadaire doit donc contenir **trois types de travail** :

- apprentissage structuré ;
- projet / production ;
- lecture ciblée / reverse engineering pour s'inspirer et challenger les choix.

La cible générale reste environ **30 % apprentissage / 70 % pratique**, le reverse engineering faisant partie de la pratique lorsqu'il sert directement une issue ou une décision de conception.

---

# 7. Questions de contrôle

Avant de monter une skill ou de fermer une issue, se demander :

1. Est-ce que je peux expliquer ce que j'ai fait sans relire le notebook ?
2. Est-ce que le code est techniquement correct ?
3. Ai-je vérifié le résultat autrement que par « ça s'exécute » ?
4. Est-ce que mon interprétation est compatible avec la théorie ?
5. Puis-je reproduire l'idée sur une autre série ou un autre exemple ?
6. Est-ce que j'ai identifié les limites de l'approche ?
7. Ai-je regardé comment le même problème est traité dans des références ou repos sérieux lorsque cela est pertinent ?
8. Si j'ai repris une idée externe, est-ce que je comprends pourquoi elle fonctionne ici ?
9. Ai-je testé cette idée plutôt que de supposer qu'elle est meilleure ?

Si la réponse importante est non, la boucle continue.

---

# 8. Principe général

`ROADMAP.md` dit **où aller**.

`LEARNING_PATH.md` dit **dans quel ordre apprendre**.

`SKILLS.md` est la **base de données des compétences**.

La **Learning Loop** construit la compréhension.

La **Practice Loop** construit le système réel et intègre le reverse engineering comme étape normale d'inspiration, de comparaison et de contrôle.

La **Research Loop** apporte les idées externes et challenge les choix.

Ces trois mécanismes doivent rester distincts, mais connectés.