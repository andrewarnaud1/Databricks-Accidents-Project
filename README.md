# Projet Databricks - Accidents de la Route

## Présentation du Projet

Ce projet a été réalisé dans le cadre de l'examen de fin de semestre du cours Formation sur un framework cloud (e.g. Azure) + Formation sur Git. L'objectif est d'utiliser Azure Databricks pour importer, traiter, et construire un modèle prédictif basé sur les données d'accidents de la route. Ce modèle est ensuite hébergé sur Azure pour permettre une utilisation via une API.

## Sources des Données

Les données utilisées pour ce projet proviennent des travaux de recherche d'Ilyes Talbi et ont été initialement publiées sur la [Revue IA](https://larevueia.fr/xgboost-vs-random-forest-predire-la-gravite-dun-accident-de-la-route/). Ces données contiennent diverses informations sur les accidents de la route, qui ont été explorées et utilisées pour construire des modèles prédictifs.

## Éléments du Repository

- `Modelisation.dbc`: Notebook Databricks contenant toutes les étapes de prétraitement des données, la construction des modèles, et l'évaluation de leurs performances.
- `Test API.dbc`: Notebook Databricks permettant de tester le modèle sélectionné via un point d'endpoint API.
- `README.md`: Ce fichier, qui présente le projet, les sources des données, les éléments du repository, et d'autres informations utiles.

## Modèle Retenu et Ses Performances

Parmi les modèles testés (KNeighborsClassifier, DecisionTreeClassifier, RandomForestClassifier), le modèle `DecisionTreeClassifier` a été retenu comme étant le plus performant en termes d'accuracy et de f1-score. Après optimisation avec `GridSearchCV`, les paramètres sélectionnés ont été `max_depth=7`, et `min_samples_leaf=3`. Les performances détaillées du modèle sont documentées dans le notebook `Modelisation.dbc`.

## Endpoint du Modèle

Le modèle est accessible via un endpoint API, permettant une utilisation facile des prédictions. Le lien de l'endpoint est le suivant : `https://adb-5282541070975571.11.azuredatabricks.net/serving-endpoints/bestClassifier/invocations`

## Liens Utiles

- [Tutoriel sur l'utilisation de GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html)
- [Documentation Markdown](https://www.markdownguide.org/cheat-sheet/)
- [Documentation GitHub](https://docs.github.com/fr/get-started/quickstart/hello-world)

