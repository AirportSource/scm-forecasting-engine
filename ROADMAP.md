# Roadmap globale

Cette roadmap donne la direction sur 12 mois. Elle n'est pas un planning journalier fixe.

## 1. Cadrage du probleme SCM
- cible ;
- granularite ;
- horizon ;
- frequence de recalcul ;
- informations disponibles ;
- criteres metier.

**Preuve attendue :** definition claire du probleme et de l'usage des previsions.

## 2. Donnees, statistiques et exploration temporelle
- Python / SQL ;
- qualite et jointures ;
- distributions, dispersion, quantiles ;
- visualisation ;
- tendance, saisonnalite et dependance temporelle.

**Preuve attendue :** donnees controlees et analyse expliquee.

## 3. References et validation
- naive et saisonniere ;
- erreurs et biais ;
- rolling-origin backtesting ;
- horizons ;
- leakage ;
- separation developpement / test.

**Preuve attendue :** backtesting reproductible sur plusieurs series.

## 4. Premiere chaine complete
- fonctions ;
- configuration ;
- tests ;
- logs ;
- sauvegarde ;
- execution hors notebook.

**Preuve attendue :** pipeline V0 executable avec un modele simple.

## 5. Modeles statistiques et ML
- regression ;
- ETS ;
- ARIMA / SARIMA ;
- arbres ;
- gradient boosting ;
- feature engineering ;
- strategies multi-horizons.

**Preuve attendue :** benchmark commun et defendable.

## 6. Incertitude et decisions SCM
- quantiles ;
- prediction intervals ;
- calibration ;
- pinball loss ;
- demande intermittente ;
- hierarchies ;
- simulation stock.

**Preuve attendue :** evaluation de l'incertitude et de son interet decisionnel.

## 7. Deploiement et exploitation
- scheduling ;
- experiment tracking ;
- monitoring ;
- retries ;
- permissions ;
- fallback ;
- documentation.

**Preuve attendue :** systeme qui s'execute regulierement et incidents diagnostiquables.

## 8. Performance et passage a l'echelle
- temps et memoire ;
- formats colonne ;
- batch processing ;
- parallelisation ;
- calcul distribue ;
- couts.

**Preuve attendue :** limites et capacites mesurees.

## 9. Transfert et specialisations
- autre dataset de demande ;
- ETA ;
- agents d'experimentation ;
- modeles neuronaux ou pre-entraines selon besoin.

**Preuve attendue :** reutilisation du socle sur un probleme different.

## Jalons mensuels indicatifs

| Mois | Direction principale | Preuve attendue |
|---|---|---|
| M1 | Stats descriptives + EDA + Python/SQL | Analyser correctement plusieurs series M5 |
| M2 | Probabilites + preparation des donnees | Dataset propre, controle, reproductible |
| M3 | Time series + backtesting | Backtest naive / saisonnier sans leakage |
| M4 | ETS / ARIMA / regression | Benchmark statistique reproductible |
| M5 | ML + feature engineering | LightGBM compare aux modeles statistiques |
| M6 | Software engineering + deploiement | Pipeline automatique local/serveur |
| M7 | Forecast probabiliste + SCM | Quantiles + simulation stock |
| M8 | Performance / gros volumes | Benchmark temps/memoire et optimisation |
| M9 | MLOps / cloud | Monitoring, tracking, retraining |
| M10 | Projet ETA | Prototype ETA reutilisant le socle |
| M11 | Agents IA | Agent lancant des experiences controlees |
| M12 | Consolidation | Projet documente, reproductible, portfolio |
