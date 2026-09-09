# Chômage des jeunes en France par département (2025)

Analyse exploratoire des disparités territoriales du chômage des jeunes 
(15-24 ans) en France, et de leur lien avec le chômage des autres tranches 
d'âge.

## Contexte

En 2025, le taux de chômage des 15-24 ans atteint 19,8 % en France, soit 
plus du double de celui de l'ensemble de la population active. Ce projet 
cherche à comprendre si ce phénomène national masque de fortes disparités 
territoriales, et si le chômage des jeunes reflète simplement la situation 
économique générale de leur département, ou s'il constitue un problème 
spécifique à cette tranche d'âge.

## Problématique

Le chômage des jeunes suit-il les mêmes disparités territoriales que celui 
des autres tranches d'âge, ou existe-t-il des départements où les 15-24 ans 
sont spécifiquement plus pénalisés que le reste de la population active ?

## Démarche

Cette analyse est de nature **exploratoire** : elle vise à décrire et 
quantifier des disparités territoriales, sans établir de lien de 
causalité. Elle combine :

- une analyse descriptive et territoriale (classements, cartographie),
- des tests de corrélation de Spearman entre le chômage des jeunes et celui 
  des autres tranches d'âge,
- une classification non supervisée (K-means), validée statistiquement par 
  un test de Kruskal-Wallis, pour identifier des profils de départements.

## Données

- **Source** : Insee, taux de chômage localisés, 2025
- **Niveau géographique** : département (France métropolitaine + DOM pour 
  les tableaux et graphiques ; métropole uniquement pour la carte, faute 
  de contours DOM disponibles dans la source cartographique utilisée)
- **Variables** : taux de chômage global, par tranche d'âge (15-24, 25-49, 
  50 ans ou plus), et écart hommes-femmes

## Résultats clés

- Le taux de chômage des 15-24 ans varie de 13 % à 45 % selon le 
  département (moyenne : 20,3 %).
- Forte corrélation entre le chômage des jeunes et celui des 25-49 ans 
  (rho de Spearman = 0,91 ; p < 0,001) : les disparités territoriales du 
  chômage des jeunes suivent en grande partie celles du reste de la 
  population active.
- Une classification en 3 profils de départements (K-means, validée par 
  un test de Kruskal-Wallis, H = 56,77 ; p < 0,001) fait émerger un groupe 
  de 4 départements (les DOM) où **toutes** les tranches d'âge connaissent 
  un chômage nettement plus élevé — signe d'une fragilité économique 
  structurelle plutôt que d'un problème spécifique à l'insertion des 
  jeunes dans ces territoires.

## Limites et pistes d'approfondissement

Cette analyse porte sur des corrélations et des regroupements statistiques 
et ne permet pas d'établir de causalité. Elle ne prend pas en compte 
d'autres facteurs potentiellement déterminants (niveau de diplôme, domaine 
de formation, structure du tissu économique local), qui pourraient 
enrichir cette étude dans un prolongement futur — actuellement en cours 
d'exploration.

## Technologies

Python, Pandas, Matplotlib, Seaborn, Scikit-learn, SciPy, GeoPandas

## Structure du projet

```
chomage-jeunes-insee/
├── data/
│   └── 50_MTS-52_CHO.xlsx
├── notebook.ipynb
└── README.md
```

## Utilisation

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy geopandas openpyxl
jupyter notebook notebook.ipynb
```