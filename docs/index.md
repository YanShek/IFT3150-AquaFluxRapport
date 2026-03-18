---
title: Vue d'ensemble du projet
---

<style>
    @media screen and (min-width: 76em) {
        .md-sidebar--primary {
            display: none !important;
        }
    }
</style>

# Vue d'ensemble du projet

!!! info "Informations générales"
    **Session**: Hiver 2026  
    **Auteur(s)**: <!-- Nom de chaque membre (matricule)  -->  Yan Shek - 20244110
    **Thème(s)**: <!-- Thèmes principaux abordés dans le projet  -->  Aquaponie, Mineralisation de l'eau, Bacteries
    **Superviseur(s)**: <!-- Nom du superviseur (affiliation)  -->  Fabian Bastin   
    **Collaborateur(s):** <!-- Nom de(s) collaborateur(s) et partenaire(s)` -->  

## Description du projet

<!-- > :bulb: N'oubliez pas d'effacer ou mettre en commentaires les notes (`>`) en début de section -->
L’aquaponie combine l’aquaculture et l’hydroponie en recyclant l’eau des bassins à poissons pour nourrir les plantes. Un élément clé de ce processus est la minéralisation, qui transforme les déchets organiques en nutriments assimilables par les plantes. Ce traitement s'effectue dans un réservoir anaérobie, dont le comportement est difficile à modéliser, mais qui peut être abordé comme une boîte noire, en se concentrant uniquement sur les composés en entrée et en sortie.

### Contexte

<!-- > Présentez le contexte général dans lequel s’inscrit votre projet (social, organisationnel, technologique, éducatif, environnemental, etc.). -->
Ce projet s’inscrit dans un contexte environnemental et technologique visant à développer des systèmes alimentaires urbains plus durables. L’entreprise ÉAU (Écosystèmes Alimentaires Urbains) exploite un système aquaponique intégrant un réacteur de minéralisation pour optimiser le recyclage interne des nutriments. Cependant, le fonctionnement de ce réservoir repose sur des dynamiques biologiques et physico-chimiques complexes, influencées par la température, la quantité de frass ajouté et l’activité bactérienne.

Sur le plan technologique, le système génère un grand volume de données issues de capteurs (électroconductivité, température, pH, ORP) stockées dans une base de données temporelle. Ce projet s’inscrit donc également dans une démarche de valorisation des données par l’analyse et l’apprentissage automatique afin d’améliorer la compréhension et le contrôle du système.

### Problématique

<!-- > Décrivez le problème central ou la question de recherche que votre projet cherche à adresser, pourquoi s'y intéresser et les faiblesses des solutions actuelles. 
 Le problème doit pouvoir être compris indépendamment de la solution envisagée. -->
Le problème central réside dans la difficulté à prédire et optimiser l’évolution de l’électroconductivité (EC) dans le bassin anoxique après un transfert d’eau ou un ajout de frass. L’EC est un indicateur global de la concentration en nutriments dissous, mais sa dynamique dépend de multiples facteurs interconnectés et non linéaires.

Les approches actuelles reposent principalement sur l’observation empirique et des ajustements manuels (ex. modification de la dose de frass). Cela limite la capacité à anticiper les variations du système, à détecter rapidement des anomalies ou à optimiser les paramètres opérationnels. Il est donc nécessaire de développer une approche quantitative capable de modéliser le comportement du système à partir des données disponibles.

### Proposition et objectifs

<!--> Présentez votre proposition de projet et les objectifs visés. Expliquez en quoi votre approche répond à la problématique identifiée. 
Assurez-vous d'avoir, dans la mesure du possible, des objectifs mesurables, raisonnnables dans le temps et non redondants entre eux.-->
Plutôt que de développer un nouveau modèle à partir de zéro, ce projet vise à consolider, structurer et optimiser les travaux déjà réalisés sur le système de minéralisation aquaponique.

L’objectif principal est d’unifier l’extraction des données, le prétraitement et les modèles prédictifs existants dans un pipeline cohérent, reproductible et scientifiquement robuste, tout en identifiant des pistes d’amélioration mesurables.

Les objectifs spécifiques sont :

Consolider le pipeline existant en regroupant l’extraction, le nettoyage et la modélisation dans une architecture claire et modulaire.

Vérifier la reproductibilité et la robustesse des performances annoncées (R², RMSE) sur des périodes temporelles distinctes.

Identifier et corriger les faiblesses méthodologiques (surajustement potentiel, redondance de variables, dépendance excessive aux features temporelles).

Proposer au moins une amélioration mesurable, telle qu’une réduction du RMSE, une meilleure généralisation temporelle ou une simplification du modèle sans perte significative de performance.

### Méthodologie

<!--> Expliquez comment vous comptez aborder le projet : démarche générale, grandes étapes prévues, itérations, types de validations envisagées. -->
1. Audit technique initial

Analyse détaillée des scripts existants (extraction InfluxDB/API, correction des données, ingénierie des variables, modèles prédictifs).
Identification des dépendances, incohérences ou étapes redondantes.

2. Consolidation du pipeline

Centralisation des étapes dans un workflow clair et reproductible

Standardisation des étapes de prétraitement

Vérification de la cohérence des variables utilisées

L’objectif est de transformer un ensemble de scripts fonctionnels en un pipeline structuré et documenté.

3. Validation des performances existantes

Reproduction des résultats précédemment obtenus en respectant une séparation temporelle stricte des données.
Comparaison des métriques sur différents ensembles (train/validation/test).

4. Analyse critique et améliorations

Étude de l’importance des variables

Analyse du risque de surajustement

Test d’alternatives simples (réduction de features, régularisation, modèles plus parcimonieux)

Évaluation de la stabilité des prédictions lors de nouveaux cycles

L’approche est itérative : chaque modification est testée quantitativement avant validation.

### Validation et Évaluation

<!--> Indiquez comment vous évaluerez que votre solution répond aux objectifs du projet (ex. scénarios d’usage, tests, retours utilisateurs, indicateurs qualitatifs ou quantitatifs).-->
1. Audit technique initial

Analyse détaillée des scripts existants (extraction InfluxDB/API, correction des données, ingénierie des variables, modèles prédictifs).
Identification des dépendances, incohérences ou étapes redondantes.

2. Consolidation du pipeline

Centralisation des étapes dans un workflow clair et reproductible

Standardisation des étapes de prétraitement

Vérification de la cohérence des variables utilisées

L’objectif est de transformer un ensemble de scripts fonctionnels en un pipeline structuré et documenté.

3. Validation des performances existantes

Reproduction des résultats précédemment obtenus en respectant une séparation temporelle stricte des données.
Comparaison des métriques sur différents ensembles (train/validation/test).

4. Analyse critique et améliorations

Étude de l’importance des variables

Analyse du risque de surajustement

Test d’alternatives simples (réduction de features, régularisation, modèles plus parcimonieux)

Évaluation de la stabilité des prédictions lors de nouveaux cycles

L’approche est itérative : chaque modification est testée quantitativement avant validation.

Validation et Évaluation

L’évaluation du projet repose sur des critères quantitatifs et méthodologiques.

1. Indicateurs de performance

Les modèles seront évalués à l’aide de :

RMSE (erreur quadratique moyenne)

MAE (erreur absolue moyenne)

R² (coefficient de détermination)

Une amélioration sera considérée pertinente si elle :

réduit significativement le RMSE sur des données futures,

améliore la stabilité des prédictions,

ou maintient la performance tout en simplifiant le modèle.

2. Robustesse temporelle

Une séparation chronologique stricte sera utilisée afin de simuler un déploiement réel.
Le modèle ne devra pas être évalué sur des données déjà vues.

3. Reproductibilité

Le pipeline consolidé devra permettre de :

reproduire les résultats à partir des données brutes,

exécuter l’ensemble du processus sans intervention manuelle complexe.

4. Pertinence opérationnelle

Enfin, l’évaluation tiendra compte de la capacité du système à :

détecter des écarts anormaux,

fournir des prédictions cohérentes lors de nouveaux cycles,

soutenir les recommandations opérationnelles existantes.


## Équipe
Je suis le seul membre de mon equipe.

## Échéancier

!!! info
    Le suivi complet est disponible dans la page [Suivi de projet](suivi.md).

| Activités                      | Début   |   Fin   | Livrable                            | Statut      |
|--------------------------------|---------|---------|-------------------------------------|-------------|
| Ouverture de projet            | 12 jan. | 12 jan. | Proposition de projet               | ✅ Terminé  |
| Études préliminaires           | 12 jan. | 23 jan. | Document d'analyse                  | 🔄 En cours |
| Présentation + Rapport         | 17 avr. | 30 avr. | Présentation + Rapport              | ⏳ À venir  |
