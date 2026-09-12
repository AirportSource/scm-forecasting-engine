# Learning Flow, Practice Loop & Research Loop

Ce document sépare volontairement **trois mécanismes différents** :

1. **Boucle d'apprentissage** : construire et consolider une compétence théorique / technique.
2. **Boucle pratique projet** : utiliser les compétences pour faire avancer le moteur de forecasting sur M5.
3. **Boucle littérature / reverse engineering** : s'inspirer, comparer, challenger et découvrir de meilleures approches.

Le but est d'éviter de confondre :

- *j'ai lu / compris une notion* ;
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

```text
                   GITHUB PROJECT
                        |
                 prochaine issue
                        v
                 J'ESSAIE DE FAIRE
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
            DIAGNOSTIC      COMMIT
                 |             |
       +---------+---------+   v
       |                   | PREUVE ISSUE
 problème technique   problème conceptuel |
       |                   |               v
       v                   v          issue -> DONE
 debug / tests       BOUCLE             |
 docs / refactor   D'APPRENTISSAGE      v
       |                   |         LEARNING_LOG.md
       +---------+---------+
                 |
                 +-------> retour au projet M5
```

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
- les limites sont identifiées ;
- la preuve demandée dans l'issue est satisfaite.

---

# 3. Les deux boucles ensemble

La **Learning Loop** et la **Practice Loop** tournent en parallèle et se nourrissent mutuellement.

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
     théorie -> exercices           issue -> code / analyse
     -> rappel -> transfert         -> tests -> interprétation
                 |                         |
                 +------------+------------+
                              |
                    connaissances appliquées
                              |
                              v
                    VALIDATION CROISÉE
             comprendre + faire + reproduire
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
J'APPLIQUE SUR M5
   ↓
JE TESTE ET J'INTERPRÈTE
   ↓
JE REPRODUIS AILLEURS
   ↓
JE DÉCOUVRE CE QUI EST ENCORE FRAGILE
   ↓
JE RETOURNE APPRENDRE OU JE CORRIGE LE PROJET
   ↓
JE RE-APPLIQUE
```

Il n'y a donc **pas une seule grande boucle**. Il y a deux boucles autonomes reliées par des passerelles.

---

# 4. Boucle littérature / reverse engineering

Cette boucle reste transversale aux deux précédentes.

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

## Règle de lecture

La revue doit être **ciblée** et produire quelque chose.

Une lecture / un repo est utile s'il mène à au moins un de ces résultats :

- une notion à approfondir ;
- une hypothèse à tester ;
- une issue à créer ;
- une erreur détectée ;
- une meilleure façon de structurer le code ;
- une décision argumentée de ne pas utiliser l'approche observée.

Pour le reverse engineering de solutions M5 : essayer d'abord de comprendre suffisamment le problème et d'avoir une baseline personnelle. Cela donne un point de comparaison et évite le copier-coller aveugle.

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
       rappel / reproduction                tests / interprétation
       transfert                            reproduction
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
          nourrit et challenge les deux boucles
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
   +------------+------------+
                |
                v
          revue hebdomadaire
                |
                v
     continuer / consolider / avancer
```

Le planning hebdomadaire doit donc contenir **les deux types de travail** :

- temps d'apprentissage structuré ;
- temps de projet / production.

La cible générale reste environ **30 % apprentissage / 70 % pratique**, sans obligation de respecter ce ratio exactement chaque jour.

---

# 7. Questions de contrôle

Avant de monter une skill ou de fermer une issue, se demander :

1. Est-ce que je peux expliquer ce que j'ai fait sans relire le notebook ?
2. Est-ce que le code est techniquement correct ?
3. Ai-je vérifié le résultat autrement que par « ça s'exécute » ?
4. Est-ce que mon interprétation est compatible avec la théorie ?
5. Puis-je reproduire l'idée sur une autre série ou un autre exemple ?
6. Est-ce que j'ai identifié les limites de l'approche ?
7. Si j'ai repris une idée externe, est-ce que je comprends pourquoi elle fonctionne ici ?

Si la réponse importante est non, la boucle continue.

---

# 8. Principe général

`ROADMAP.md` dit **où aller**.

`LEARNING_PATH.md` dit **dans quel ordre apprendre**.

`SKILLS.md` est la **base de données des compétences**.

La **Learning Loop** construit la compréhension.

La **Practice Loop** construit le système réel.

La **Research Loop** apporte les idées externes et challenge les choix.

Ces trois mécanismes doivent rester distincts, mais connectés.