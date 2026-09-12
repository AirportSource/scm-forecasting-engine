# Cadence — exécuter sans replanifier en permanence

`ROADMAP.md` donne la direction, `LEARNING_PATH.md` l'ordre, `SKILLS.md` la base de compétences, `docs/WORKFLOW.md` les boucles de travail. Ce fichier fixe uniquement le rythme.

## 1. Capacité hebdomadaire

- maximum disponible : 48 h ;
- **planifié : ~40 h** ;
- buffer : ~8 h.

Le buffer n'est pas rempli à l'avance. Il absorbe bugs, fatigue, imprévus, rappel supplémentaire ou petite dérive.

## 2. Journée type — environ 6 h 40 de travail réel

| Bloc | Durée | Contenu |
|---|---:|---|
| Ouverture | 15 min | choisir une issue / compétence et écrire la preuve attendue |
| Profond 1 | 90 min | théorie neuve ou problème difficile |
| Profond 2 | 90 min | exercice / implémentation directe |
| Projet | 105 min | M5 / issue courante |
| Moyen | 45 min | reverse engineering ciblé, tests, refactor ou doc technique |
| Rappel | 30 min | récupération active / notions fragiles |
| Clôture | 25 min | preuve/trace du jour, learning log, première action demain |

Les pauses et le repas sont hors de ces 6 h 40.

La journée peut être redistribuée selon le bloc. Le ratio 30 % apprentissage / 70 % pratique est une tendance hebdomadaire, pas une contrainte quotidienne.

## 3. Règle de trace

**Aucune journée travaillée sans preuve ou trace.**

La trace peut être :
- code ou test ;
- notebook d'exploration ;
- exercice ;
- résultat de checkpoint ;
- note dans `LEARNING_LOG.md` ;
- issue mise à jour.

Un commit n'est exigé que lorsqu'un incrément utile existe. Pas de commits artificiels pour maintenir une streak.

## 4. Revue hebdomadaire — 60 min

1. heures réelles ;
2. preuves produites ;
3. skills réellement montées de niveau ;
4. notions fragiles ;
5. dérive hors bloc ;
6. budget consommé ;
7. **un objectif principal + trois issues maximum** pour la semaine suivante.

Le samedi est idéalement consacré en partie à consolidation, reproduction et revue plutôt qu'à l'ajout d'un gros nouveau concept.

## 5. Checkpoint mensuel — 2 à 3 h

- état du bloc / version cible ;
- budget prévu vs réel ;
- checkpoint de `docs/CHECKPOINTS.md` si un bloc se termine ;
- décision explicite : continuer / consolider / couper du scope ;
- nettoyage léger du backlog.

Les modifications structurelles du plan ne se font qu'ici, sauf erreur critique évidente.

## 6. Recovery / Drift Protocol

### Blocage technique

Bloqué ~90 min sans progrès :
1. écrire attendu / obtenu / essais ;
2. réduire à un exemple minimal ;
3. documentation ou implémentation de référence ;
4. si nécessaire, demander de l'aide ;
5. reprendre lorsque l'hypothèse de bug est plus précise.

Un blocage conceptuel renvoie à la Learning Loop ; un bug renvoie à la Practice Loop.

### Retard

- < 1 jour : buffer ;
- 1–3 jours : supprimer stretch tasks et lectures optionnelles ;
- > 1 semaine : décaler la trajectoire ;
- > 25 % du budget mensuel : réduire le scope Support/Optional.

**Jamais de rattrapage par augmentation durable des heures.**

### Maladie / interruption

Pause officielle, sans dette morale ni compression du Core. À la reprise : rappel court + reprise de la dernière issue ou du dernier checkpoint pertinent.

### Démotivation

Pendant une semaine : réduire à 4 h/jour si nécessaire, viser une petite preuve concrète, ne pas réorganiser le repo comme substitut au travail réel.

## 7. Ordre de coupe

1. agents IA avancés ;
2. deep learning / foundation models ;
3. ETA temps réel avancé ;
4. Spark / Databricks avancés ;
5. approfondissements R non nécessaires à FPP3.

Ne pas couper : EDA, validation/backtesting, baselines, modèles statistiques, ML/feature engineering, probabiliste/SCM, pipeline reproductible.

## 8. Gel de la méta

À partir de maintenant :
- pas de nouveau fichier d'organisation sauf besoin concret démontré ;
- pas de nouvel outil sans issue expliquant le besoin ;
- pas de changement de dataset principal avant que le socle soit suffisamment stable ;
- pas de refonte de la roadmap hors checkpoint mensuel.
