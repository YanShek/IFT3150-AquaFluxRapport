---
title: Résumé du projet
---

<style>
    @media screen and (min-width: 76em) {
        .md-sidebar--primary {
            display: none !important;
        }
    }
</style>

# Résumé du projet

## Introduction

Le projet AquaFlux s'inscrit dans le contexte de l'aquaponie urbaine, en collaboration avec ÉAU - Écosystèmes Alimentaires Urbains. Dans ce type de système, les déchets issus de l'élevage de poissons sont transformés en nutriments pour les plantes, notamment par un processus de minéralisation dans un bassin anoxique.

L'électroconductivité (EC) de l'eau sert d'indicateur indirect de la concentration en minéraux dissous. Elle est donc utile pour suivre la qualité de la solution nutritive, mais sa mesure directe repose sur des sondes spécialisées. Le projet cherche à mieux structurer les données disponibles et à évaluer dans quelle mesure l'EC peut être prédite à partir d'autres variables mesurées ou enregistrées, comme la température, le pH, l'ORP, les transferts d'eau et les ajouts de frass.

## Méthodologie et analyse

La démarche a d'abord consisté à reprendre les travaux des cohortes précédentes afin de comprendre le pipeline existant, les modèles déjà utilisés et les limites des données disponibles. Une visite chez ÉAU a également permis de relier les fichiers et notebooks au fonctionnement réel du système.

Le travail s'est ensuite concentré sur la consolidation des données issues d'InfluxDB et de MAIA. Les mesures de capteurs ont été nettoyées, alignées temporellement et enrichies avec des événements opérationnels. Une attention particulière a été portée à la conservation d'un maximum d'information, plutôt qu'à un rééchantillonnage trop agressif. Les valeurs d'EC compensées automatiquement par les sondes ont aussi été transformées pour produire des valeurs brutes plus exploitables.

Une autre partie importante de l'analyse a porté sur la reconstruction des valeurs manquantes de `TEMP-EAU_8`, la température de la solution nutritive. Un modèle de forêt aléatoire a été utilisé pour imputer uniquement les valeurs absentes, en conservant les mesures réelles lorsqu'elles existaient. Cette variable reconstruite a ensuite été testée dans le pipeline de prédiction de l'EC afin d'en mesurer l'effet sur les performances.

## Architecture et conception

La solution repose sur un pipeline de données plus clair et plus réutilisable. Le traitement brut est centralisé autour du notebook `raw_data_processed.ipynb`, qui produit un fichier consolidé `dataClean.csv`. Ce fichier sert de base analytique plus détaillée, car il conserve davantage d'information temporelle et regroupe les données de capteurs, les variables dérivées et les événements MAIA.

Le projet distingue aussi deux usages complémentaires des données. D'une part, `dataClean.csv` sert à l'analyse et au nettoyage plus fin des observations. D'autre part, `df_main.csv` et sa version enrichie `df_main_temp8_pred.csv` servent aux essais de prédiction de l'EC. La prédiction de température a été sortie progressivement d'un notebook pour être rendue plus reproductible dans le script `temp_prediction_pipeline.py`.

Enfin, une documentation technique a été ajoutée pour faciliter la continuité du projet. Elle décrit l'organisation du dépôt, les étapes du pipeline, l'accès aux données MAIA, les fichiers importants et les validations nécessaires.

## Résultats et réalisations

Le projet a permis de produire une base de données consolidée plus complète, intégrant les mesures de capteurs, les événements de transfert d'eau, les ajouts de frass et les variables d'EC brutes. Il a aussi permis de mettre en place un processus réutilisable pour reconstruire les valeurs manquantes de `TEMP-EAU_8`.

La comparaison entre le pipeline de prédiction original et la version enrichie avec la température imputée montre une amélioration des performances hors échantillon. Dans le rapport final, le RMSE de validation passe de 17,57 à 13,48 µS/cm, et le RMSE de test passe de 9,42 à 7,23 µS/cm. Ces résultats suggèrent que l'ajout d'une température reconstruite peut apporter une information utile au modèle.

Le travail a également clarifié l'état du dépôt et réduit la dépendance à des notebooks difficiles à interpréter. Les principaux fichiers et workflows sont maintenant mieux documentés, ce qui devrait faciliter la reprise du projet par de futurs étudiants.

## Évaluation et limites

L'évaluation s'appuie sur une séparation chronologique des données d'entraînement, de validation et de test. Ce choix est essentiel pour éviter d'utiliser des données futures afin de prédire le passé, ce qui aurait surestimé les performances dans un contexte de série temporelle.

Les résultats doivent toutefois être interprétés avec prudence. Le modèle de prédiction de l'EC dépend encore fortement de l'historique récent de `EC_6`, notamment par l'utilisation de lags et de moyennes mobiles. Il s'agit donc davantage d'une prédiction à court terme avec historique EC disponible que d'une démonstration qu'une sonde EC peut être entièrement remplacée.

De plus, la variable `TEMP-EAU_8` imputée reste une estimation produite par un modèle. Elle permet de tester l'effet d'une information manquante, mais ne remplace pas une mesure directe fiable. La qualité des conclusions demeure donc liée à la qualité des capteurs, à la synchronisation des horodatages et à la durée limitée des périodes observées.

## Conclusion et perspectives

Le projet a renforcé la base technique d'AquaFlux en rendant le pipeline de données plus structuré, plus documenté et plus réutilisable. Il a aussi montré qu'un enrichissement des données, notamment par l'imputation de la température de la solution nutritive, peut améliorer la prédiction de l'électroconductivité dans le protocole testé.

Pour la suite, il serait pertinent d'évaluer des modèles moins dépendants de l'historique direct de l'EC afin de mieux mesurer le potentiel réel d'une prédiction à partir de capteurs moins coûteux. L'ajout de tests automatisés sur les transformations critiques, les colonnes attendues et les séparations temporelles permettrait aussi de renforcer la reproductibilité du pipeline.
