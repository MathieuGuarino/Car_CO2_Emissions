# Emissions de gaz pour les voitures en 2013 et 2015

# Is there a link between how a country consume energy and health ?
# How is changing energy consumption and production over the years ?


*Antoine Theillac & Mathieu Guarino*

*[Iron Hack, DataAnalyze & 24/07/2021]*

## Content
- [Project Description](#project-description)
- [Hypothèses / Questions](#hypotheses-/-questions)
- [Dataset](#dataset)
- [Workflow](#workflow)
- [Liens](#liens)

<a name="project-description"></a>

## Description du projet
Nous avons plusieurs dataset sur les immatriculations Françaises en 2013 et 2015. Nous allons chercher des liens entre les caractéristiques des voitures et les émissions de gaz associé, si certains types de voiture émettent plus ou moins certains types de gaz

<a name="hypotheses-/-questions"></a>

## Hypothèses / Questions :
- Le poids, la puissance, norme sont corrélés aux émissions de gaz
- Les véhicules qui sont Diesel émettent + de particules fines et émettent moins de CO2
- Quels sont les facteurs importants dans l'émissions de gaz ?

<a name="dataset"></a>

## Dataset
Le dataset provient de :
[Emissions de CO2 et de polluants des véhicules commercialisés en France](https://www.data.gouv.fr/fr/datasets/emissions-de-co2-et-de-polluants-des-vehicules-commercialises-en-france/)

Les données sont découpées en plusieurs fichiers par année, avec des formats et un nombre de colonne différents. Dans le cadre de cet exercice, nous nous sommes limités à 2 fichiers.

<a name="workflow"></a>

## Workflow
La première difficulté était de déterminer quel type de données pourrait-on prédire, il y avait plusieurs approches : la qualité de la voiture (citadine, berline, premium ...). Ensuite, le dataset avait beaucoup de données en doublon, des colonnes apportant les mêmes informations, un travail de transformation de l'information était également nécessaire pour extraire seulement les informations pertinentes, la transformation des types de données également.
Une fois les données homogénéisées sur les deux fichiers, on a pu les concatener et explorer les données. 
Nous avons de nouveau retiré plusieurs colonnes non utiles pour l'apprentissage du machine learning, réalisé du standard scaling et normalisé certaines données (qui n'avaient pas la moyenne centrée), nous avons également réalisé du one hot enconding.

Le jeu de données à été découpé en deux set de 80/90% pour l'apprentissage et 20/10% pour les tests, plusieurs modèles ont été testés afin de trouver quel modèle était le plus efficace. Une fois le modèle trouvé, nous essaierons de l'améliorer puis de le valider sur les données de test.


<a name="links"></a>

## Liens

[Repository](https://github.com/screamzz/Car_CO2_Emissions/)   
[Slides](https://docs.google.com/presentation/d/1S--k2ATpx7-ZB8DW-CKB1UwcDBGFnogNY7cCvO14OKQ/edit?usp=sharing)

# Conclusion

Nous avons pu trouver plusieurs modèles efficaces pour réaliser l'apprentissage de nos données. L'amélioration de modèle n'est pas évident mais permets d'avoir de meilleurs résultats. La préparation de données est très importante, mais également de garder une cohérence dans les formats de données, d'une année à l'autre, sinon il y a une perte de temps pour préparer ces données mais également des erreurs sont créées plus loin dans l'éxecution du process.

# Going further

Nous avons à peine éffleuré la partie visible du dataset, nous pouvons en effet creuser et voir si la qualité de la voiture et l'évolution des normes de pollution automobile influencent les émissions de gaz. Les données les plus récentes datent de 2015, les véhicules hybrides et 100% électriques n'étaient pas très présents sur le parc automobile, c'est pour ça que nous les avons retirés de nos données d'entrées, mais il serait intéressant de voir l'effet de l'hybride sur les gaz et si le gain vaut l'utilisation de matière premières pour la réalisation de la batterie électrique.
