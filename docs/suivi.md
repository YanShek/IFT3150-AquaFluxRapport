---
title: Suivi du projet
---

<style>
    @media screen and (min-width: 76em) {
        .md-sidebar--primary {
            display: none !important;
        }
    }
</style>

# Suivi de projet
<!--
 :bulb: Cette page documente l’évolution du projet dans le temps.
 Elle sert à rendre visibles les décisions, ajustements et apprentissages.
 Les entrées peuvent être hebdomadaires ou bi-hebdomadaires.  
 N'oubliez pas d’effacer ou de mettre en commentaires les notes (`>`) avant la remise finale. -->

---

## Semaine 1 (13–19 janvier)

### Objectifs de la période
- Comprehension initiale du projet


### Travail réalisé

- Lecture des rapports des étudiants precedents
- Lecture et tentative de comprehension des notebooks
- Visite chez ÉAU pour avoir une compréhension concrète du système avec une attention particulière sur la minéralisation.

### Décisions et ajustements

- Creation d'un nouveau script pour pouvoir chercher l'information du site maia-app.ca, notamment sur la temperature, l'ohp, et le pH de l'eau.

### Difficultés rencontrées

Probleme dans l'obtention du token de la base de donnes MAIA. Cela empeche l'execution des fichiers python pour obtenir des donnes.
Résolution du probleme en utilisant les outils développeurs du navigateur. 


## Semaine 2 (19-27)
### Objectifs de la période
- Chargement des donnés et exploration des donnés.


### Travail réalisé
- Avec les informations de connexion pour InfluxDB, j'ai pu obtenir directement le token pour extraire les donnés.
- Poursuite de la lecture des notebooks et comprendre ce qui a été fait.

### Décisions et ajustements

### Difficultés rencontrées
- Je ne trouvais pas où se trouvait les données sur l'ajout de frass et donc j'ai perdu du temps à fouiller dans Influx et dans les 'sources' du site MAIA.

## Semaine 3 (27-03)
### Objectifs de la période
- Telecharger les donnees, les nettoyer et comprehension des travaux precedents.


### Travail réalisé
- Utilisation des scripts pythons et les notebook existants pour etablir ce qui fonctionne et ne fonctionne pas.

### Décisions et ajustements
- J'ai decide de faire un notebook compilatoire base sur le code existant pour avoir ce qui fonctionne a un endroit.

### Difficultés rencontrées
- Comprendre ce qui a ete fait afin d'identifier ce qui est deprecie et ne fonctionne pas avec certitude.
- La tentative a deviner l'intention derriere le code
- Le telechargement de donnes varie entre 2 ordinateurs. Sur la tour, il permet le telechargement de l'ensemble des donnes alors que sur le portable, il est restraint par un interval de temps

## Semaine 4 (03-10)
### Objectifs de la période
- Televerser les donnes dans Google Drive
- Documenter et valider le travail de l'etudiant precedent

### Travail réalisé
- Avec les informations de connexion pour InfluxDB, j'ai pu obtenir directement le token pour extraire les donnés.
- Poursuite de la lecture des notebooks et comprendre ce qui a été fait.

### Décisions et ajustements

### Difficultés rencontrées
- Je ne trouvais pas où se trouvait les données sur l'ajout de frass et donc j'ai perdu du temps à fouiller dans Influx et dans les 'sources' du site MAIA.

## Semaine 5 (10-16 février)
### Objectifs de la période
- Creer un fichier de donnees bruts avec la temperature non-normalise

### Travail réalisé
- Reutilisation d'une partie du code d'un etudiant precedent pour enlever la compensation de la temperature d'une sonde.
- Combiner cela avec le trvail precedent pour pouvoir avoir les donnes bruts: 
- - On resamplait les donnees aux 5 minutes $\rightarrow$  On prend toutes les mesures
- - On enleve la compensation de la temperature sur l'electroconductivite.

### Décisions et ajustements
- Comme il y avait plusieurs fichiers qui faisaient la meme affaire, j'en ai fait un global pour avoir une version finale de ce qui foncitonne.

### Difficultés rencontrées
- Il y avait plusieurs fichiers qui essayait d'accomplir une meme tache, mais il y a eu des mises a jours de la base de donnee rendant ces fonctionnalites invalide.
- J'avais essaye de comprendre des fonctionnalites depreciees des fichiers pythons pour le projet.


## Semaine 6 (17-23 février)
### Objectifs de la période
- Tester et valider le travail hérité
- Commencer le nettoyage et la fusion des donnees brutes

### Travail réalisé
- Vérification de la cohérence des scripts et des données déjà récupérées
- Début du nettoyage des données brutes et du regroupement des mesures proches dans le temps
- Poursuite de la structuration d'un workflow plus clair pour la suite du projet

### Décisions et ajustements
- Avancer vers un pipeline progressif plutôt qu'un ensemble de scripts isolés
- Tester une fenêtre de fusion courte pour limiter la fragmentation des mesures

### Difficultés rencontrées
- Alignement de capteurs mesurant presque au même moment mais avec un léger décalage temporel

## Semaine 7 (24 février - 2 mars)

### Objectifs de la période
- Stabiliser le nettoyage des données
- Préparer les données pour la modélisation

### Travail réalisé
- Consolidation des étapes de nettoyage et validation des sorties intermédiaires
- Préparation des données en vue des premiers essais de modélisation
- Detection des "flush" et deletion de ces rangees. 

### Décisions et ajustements
- Conserver une séparation claire entre extraction, nettoyage et modélisation
- Continuer à simplifier les étapes héritées pour ne garder que celles qui sont reproductibles

### Difficultés rencontrées
- Distinguer les transformations nécessaires des étapes devenues obsolètes

## Semaine 8 (3-9 mars)

### Objectifs de la période
- Clarifier la structure du pipeline
- Amorcer le travail sur la prédiction de température

### Travail réalisé
- Poursuite de la consolidation du pipeline existant
- Début de l'adaptation du travail de prédiction de température au contexte actuel
- Réflexion sur l'utilisation de données brutes plutôt que seulement de données rééchantillonnées

### Décisions et ajustements
- Favoriser une structure de travail plus lisible et plus maintenable
- Éviter de dépendre d'outils ou de fichiers intermédiaires devenus fragiles

### Difficultés rencontrées
- Avancer malgré une documentation technique partielle du matériel hérité

## Semaine 9 (10-16 mars)

### Objectifs de la période
- Faire un premier bloc de modélisation de température exploitable
- Ajouter des variables de température utiles au jeu de données

### Travail réalisé
- Réutilisation et adaptation du code existant pour prédire une température manquante du bassin anoxique
- Travail sur un modèle de prédiction pour la température de la solution nutritive
- Ajout de la température de l'air dans le fichier de données brutes

### Décisions et ajustements
- Adapter le code de prédiction, initialement pensé pour des données rééchantillonnées, à un fichier de données plus proche du brut

### Difficultés rencontrées
- Le code hérité repose sur du rééchantillonnage, ce qui complique le traitement des températures des bassins 6 et 8

## Semaine 10 (17-23 mars)

### Objectifs de la période
- Formaliser plus clairement le cadrage du projet
- Consolider dans la documentation les avancées sur la température

### Travail réalisé
- Ajout au suivi du travail de modélisation autour des températures manquantes et de l'intégration de la température de l'air

### Décisions et ajustements
- Mettre l'accent sur la consolidation du pipeline existant plutôt que sur un redéveloppement complet
- Rendre explicites les critères de validation et de reproductibilité du projet

### Difficultés rencontrées
- Transformer des avancées techniques dispersées en documentation cohérente et défendable

## Semaine 11 (24-30 mars)
### Objectifs de la période
- Documenter la pipeline complète des traitements de donnees
- Réorganiser les notebooks et les notes de travail utiles à la remise finale

### Travail réalisé
- Semaine en cours au 26 mars 2026; entrée à compléter à mesure que le travail est poussé ou documenté

### Décisions et ajustements
- Garder cette semaine ouverte pour éviter d'annoncer comme terminé un travail non encore versionné

### Difficultés rencontrées
- Documenter fidèlement l'avancement quand une partie du travail n'est pas encore visible dans le dépôt

## Semaine 11 (31-7 mars)
### Objectifs de la période
- Documenter la pipeline complète des traitements de donnees
- Réorganiser les notebooks et les notes de travail utiles à la remise finale

### Travail réalisé
- Semaine en cours au 26 mars 2026; entrée à compléter à mesure que le travail est poussé ou documenté

### Décisions et ajustements
- Garder cette semaine ouverte pour éviter d'annoncer comme terminé un travail non encore versionné

### Difficultés rencontrées
- Documenter fidèlement l'avancement quand une partie du travail n'est pas encore visible dans le dépôt