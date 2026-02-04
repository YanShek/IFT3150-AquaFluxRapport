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

> :bulb: Cette page documente l’évolution du projet dans le temps.
> Elle sert à rendre visibles les décisions, ajustements et apprentissages.
> Les entrées peuvent être hebdomadaires ou bi-hebdomadaires.  
> N'oubliez pas d’effacer ou de mettre en commentaires les notes (`>`) avant la remise finale.

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
