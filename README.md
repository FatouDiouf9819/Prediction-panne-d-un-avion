✈️ Prédiction de la durée de vie utile d’un moteur d’avion — NASA C-MAPSS
Projet de Machine Learning appliqué à la maintenance prédictive, visant à estimer la durée de vie utile restante (RUL — Remaining Useful Life) de moteurs aéronautiques à partir de données de dégradation issues du jeu de données NASA C-MAPSS.
L’objectif est de transformer les données de cycles et de capteurs en une estimation exploitable de la durée de vie restante d’un moteur.
🎯 Objectifs du projet
Le projet s’articule autour de quatre étapes principales :
1. Construction de la variable cible — RUL
Calcul de la durée de vie restante (RUL) de chaque moteur à partir de son cycle courant et de son dernier cycle observé.
2. Prétraitement et nettoyage des données
- Analyse et préparation des données issues des moteurs.
- Sélection des capteurs présentant une information exploitable.
- Détection et traitement des valeurs aberrantes à l’aide de la méthode de l’IQR (Interquartile Range).
- Remplacement des valeurs aberrantes par la médiane.
- Normalisation et mise à l’échelle des variables utilisées pour la modélisation.
3. Modélisation prédictive
Trois approches de régression sont étudiées et comparées :
- Régression linéaire — modèle de référence (baseline)
- Random Forest Regressor — avec recherche d’hyperparamètres
- XGBoost Regressor
4. Application à la maintenance prédictive
Les estimations de RUL peuvent servir d’indicateur pour identifier les moteurs dont la durée de vie utile restante est faible et contribuer ainsi à la priorisation des actions de maintenance.
📊 Dataset — NASA C-MAPSS
Le projet utilise le jeu de données NASA Turbofan Jet Engine Degradation Simulation (C-MAPSS).
Les principales informations exploitées comprennent :
- Identifiant du moteur : unité moteur suivie au cours de son fonctionnement.
- Cycles opérationnels : évolution du moteur au fil des cycles.
- Paramètres opérationnels : conditions de fonctionnement du moteur.
- 21 capteurs : mesures liées notamment à la température, à la pression, aux vitesses de rotation et aux différents paramètres de fonctionnement.
La variable cible RUL représente le nombre de cycles restant avant la fin de vie utile du moteur.
🤖 Modèles de Machine Learning
Régression linéaire
Utilisée comme modèle de référence (baseline) afin d'établir un premier niveau de performance.
Random Forest
Modèle d'ensemble basé sur plusieurs arbres de décision. Une recherche d'hyperparamètres a été utilisée afin d'améliorer ses performances.
XGBoost
Modèle de gradient boosting basé sur des arbres de décision, utilisé pour modéliser les relations non linéaires entre les caractéristiques des moteurs et leur durée de vie restante.
📈 Évaluation des modèles
Les modèles sont comparés à l'aide de trois métriques de régression :
- RMSE (Root Mean Squared Error) : mesure l'écart entre les valeurs réelles et prédites, avec une pénalisation plus forte des grandes erreurs. Plus il est faible, meilleur est le modèle.
- MAE (Mean Absolute Error) : mesure l'erreur absolue moyenne entre les valeurs réelles et prédites. Plus il est faible, meilleur est le modèle.
- R² (coefficient de détermination) : mesure la proportion de la variance de la variable cible expliquée par le modèle. Plus il est élevé, meilleur est le modèle.
📊 Résultats et comparaison des modèles
Les trois modèles ont été évalués sur le même jeu de test à partir des métriques RMSE, MAE et R².
Modèle	RMSE ↓	MAE ↓	R² ↑
Régression linéaire	42.181	32.254	0.593
Random Forest	41.077	30.440	0.614
XGBoost	40.089	29.283	0.633


🏆 Modèle retenu : XGBoost
À l'issue de la comparaison, XGBoost a été retenu comme modèle final pour la prédiction du RUL.
Ce choix repose sur les résultats obtenus sur le jeu de test :
- il présente le RMSE le plus faible : 40.089 ;
- il présente le MAE le plus faible : 29.283 ;
- il obtient le R² le plus élevé : 0.633.
Ainsi, dans la configuration expérimentale utilisée dans ce projet, XGBoost fournit les estimations de RUL les plus proches des valeurs observées parmi les trois modèles étudiés.
Le choix de XGBoost est donc fondé sur les performances prédictives mesurées par les métriques retenues, et non sur une supériorité générale du modèle dans tous les contextes.
🛠️ Technologies et bibliothèques utilisées
Langage
- Python 3
Manipulation des données
- pandas
- numpy
Visualisation
- matplotlib
- seaborn
Machine Learning
- scikit-learn
- xgboost
Environnement
- Jupyter Notebook
📁 Structure du projet
Prediction-panne-d-un-avion/
│
├── README.md
├── Prediction_panne_d_un_avion.ipynb
├── requirements.txt
└── ...
🚀 Installation et utilisation
1. Cloner le dépôt
git clone https://github.com/fatoudiouf/Prediction-panne-d-un-avion.git
cd Prediction-panne-d-un-avion
2. Installer les dépendances
pip install -r requirements.txt
3. Lancer le notebook
jupyter notebook Prediction_panne_d_un_avion.ipynb
Le notebook contient les différentes étapes de préparation des données, de construction du RUL, de modélisation et d'évaluation.
🔬 Compétences mises en pratique
Ce projet met en pratique plusieurs compétences en Data Science et Machine Learning :
- préparation et nettoyage de données ;
- ingénierie de variables ;
- construction d'une variable cible pour un problème de régression ;
- analyse de données de capteurs ;
- entraînement de modèles de Machine Learning ;
- recherche d'hyperparamètres ;
- comparaison de modèles ;
- évaluation des performances ;
- utilisation de modèles d'ensemble ;
- application du Machine Learning à la maintenance prédictive.
Le projet illustre également le lien entre modélisation mathématique, programmation et intelligence artificielle.
🎯 Application
La prédiction du RUL peut contribuer à la maintenance prédictive en fournissant une estimation de la durée de fonctionnement restante d'un moteur.
Dans un contexte industriel, ces estimations peuvent être utilisées comme indicateur d'aide à la décision pour anticiper les opérations de maintenance et mieux gérer les risques liés à la dégradation des équipements.
👩‍💻 Auteur
Fatou DIOUF
Étudiante en Master 1 Modélisation Mathématique et Simulation Numérique