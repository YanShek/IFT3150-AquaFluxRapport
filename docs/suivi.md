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
- Consolidation de la documentation autour de la pipeline de donnees et du pretraitement.
- Mise en ordre des notebooks de traitement pour mieux distinguer extraction, nettoyage, donnees brutes et table analytique.
- Clarification du role de `df_main.csv` comme table principale pour les analyses et la modelisation.

### Décisions et ajustements
- Mettre la documentation technique directement dans le depot AquaFlux pour que le workflow soit plus facile a reprendre.
- Garder les anciens notebooks comme reference, mais faire ressortir les fichiers qui servent vraiment dans la pipeline actuelle.

### Difficultés rencontrées
- Plusieurs fichiers historiques se recoupent, donc il faut documenter ce qui est encore utile sans effacer trop vite le contexte herite.

## Semaine 12 (31 mars - 6 avril)
### Objectifs de la période
- Stabiliser le workflow de traitement brut
- Preparer une sortie unique plus simple a reutiliser

### Travail réalisé
- Analyse du notebook `raw_data_processed.ipynb` pour identifier les etapes de transformation necessaires.
- Debut de la separation entre les transformations de base et les enrichissements MAIA.
- Travail sur la logique de fusion des mesures tres proches dans le temps.

### Décisions et ajustements
- Avancer vers un seul fichier nettoye final plutot que plusieurs checkpoints intermediaires difficiles a suivre.
- Conserver davantage de resolution temporelle avant les etapes de reechantillonnage.

### Difficultés rencontrées
- Les mesures des capteurs ne sont pas toutes enregistrees exactement au meme instant, ce qui rend les fusions temporelles sensibles aux seuils choisis.

## Semaine 13 (7-13 avril)
### Objectifs de la période
- Rafraichir les donnees MAIA utiles a la pipeline
- Mieux integrer les evenements de frass et de transfert d'eau
- Transformer le travail de prediction de temperature en pipeline reutilisable

### Travail réalisé
- Mise a jour des fichiers MAIA utilises pour les transferts d'eau et les ajouts de frass.
- Preparation des sorties `H2O-AQ_MIN_latest.csv` et `frass_sorted_0413.csv`.
- Adaptation des etapes de merge pour que `water_transfer` et `quantity_frass` puissent etre ajoutes separement a `dataClean.csv`.
- Remplacement progressif du workflow de prediction de temperature par le script `temp_prediction_pipeline.py`.
- Ajout d'une sortie `dataClean_temp8_pred.csv` pour remplir les valeurs manquantes de `TEMP-EAU_8` en conservant les mesures existantes.
- Ajout d'une sortie optionnelle `df_main_temp8_pred.csv` pour tester l'effet de la temperature reconstruite sur la modelisation de l'EC.

### Décisions et ajustements
- Garder les merges MAIA comme cellules ou etapes autonomes afin de pouvoir rafraichir les evenements sans relancer tout le traitement brut.
- Utiliser les fichiers MAIA les plus recents comme reference pour les fusions aval.
- Sortir la prediction de temperature d'un notebook afin de la rendre plus reproductible.

### Difficultés rencontrées
- Le telechargement MAIA n'est pas entierement automatise pour tous les types de donnees, donc une partie du workflow demande encore une verification manuelle.
- Il fallait eviter de remplacer des temperatures mesurees par des predictions et ne remplir que les valeurs manquantes.
- Les performances du modele de temperature dependent fortement de l'alignement entre `TEMP-EAU_6`, `TEMP-EAU_8` et `TEMP-AIR_12`.

## Semaine 14 (14-20 avril)
### Objectifs de la période
- Corriger la validation du notebook de prediction EC
- Eviter que le modele utilise des donnees futures pour predire le passe

### Travail réalisé
- Modification de `anox_ec_prediction_lr.ipynb` pour que les phases d'entrainement, validation et test suivent un decoupage chronologique.
- Remplacement de l'ancien split aleatoire afin de ne pas utiliser de donnees futures pour predire des observations passees.
- Verification du role des differents fichiers de prediction EC dans le depot.
- Constat que le script actuel de prediction EC mentionne dans le workflow etait absent du depot.
- Annulation du travail fait dans le notebook lorsque j'ai constate qu'il etait devenu deprecie par rapport au workflow attendu.
- Mise a jour de la documentation pour signaler que ce notebook ne doit plus etre considere comme la pipeline principale de prediction EC.

### Décisions et ajustements
- Conserver l'idee du decoupage chronologique comme critere de validation important pour les modeles temporels.
- Ne pas continuer a investir dans un notebook deprecie
- Ajuster la documentation pour refleter l'etat reel du depot plutot qu'un workflow idealise.

### Difficultés rencontrées
- Le notebook contenait encore de la logique utile, mais il ne representait plus clairement la source de verite du projet.
- L'absence du script de prediction EC a force une correction de trajectoire apres avoir deja commence a modifier le notebook et la documentation.

## Semaine 15 (21-27 avril)
### Objectifs de la période
- Rendre la structure du depot plus lisible
- Documenter les workflows principaux pour une nouvelle personne sur le projet

### Travail réalisé
- Refactorisation de la structure du code pour ameliorer la lisibilite et la maintenabilite.
- Ajout et mise a jour de documents de reference: `ONBOARDING.md`, `DATA_PIPELINE.md`, `MAIA_RUNBOOK.md`, `SYSTEM_MAP.md`, `VALIDATION.md` et `PROJECT_PIPELINE_MERMAID.md`.
- Mise a jour du `README.MD` pour expliquer les points d'entree principaux du projet.
- Documentation des interactions entre fichiers, scripts, notebooks, donnees InfluxDB et donnees MAIA.

### Décisions et ajustements
- Faire du dossier `Documentation/` la source principale pour expliquer la pipeline et les choix techniques.
- Distinguer clairement la branche analytique historique basee sur `df_main.csv` et la branche brute basee sur `dataClean.csv`.

### Difficultés rencontrées
- La documentation devait rester assez complete pour expliquer le projet, mais pas devenir une copie ligne par ligne des notebooks.
