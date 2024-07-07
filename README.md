# Détection d'Enchères Robotiques

Ce projet vise à développer un modèle de classification pour détecter les enchères effectuées par des robots sur une plateforme d'enchères en ligne. L'objectif est de prévenir la fraude et d'améliorer l'intégrité des enchères en identifiant de manière fiable les activités d'enchères automatisées.

## Table des matières

1. [Introduction](#introduction)
   - [Contexte et objectifs](#contexte-et-objectifs)
   - [Description des données](#description-des-données)
2. [Analyse exploratoire des données (AED)](#analyse-exploratoire-des-données-aed)
   - [Prétraitement des données](#prétraitement-des-données)
   - [Analyse exploratoire des données](#analyse-exploratoire-des-données)
3. [Feature Engineering](#feature-engineering)
   - [Description de démarche](#description-de-démarche)
   - [Choix des features](#choix-des-features)
4. [Modélisation Prédictive](#modélisation-prédictive)
   - [Decision Tree (DT)](#decision-tree-dt)
   - [Random Forest (RF)](#random-forest-rf)
   - [Gradient Boosting (GB)](#gradient-boosting-gb)
5. [Comparaison des modèles](#comparaison-des-modèles)
6. [Conclusion](#conclusion)

---

## Introduction

### Contexte et objectifs

Ce projet explore la détection de comportements frauduleux dans les enchères en ligne, en se concentrant sur l'identification des enchères effectuées par des robots plutôt que par des humains.

### Description des données

Les données utilisées incluent deux ensembles principaux : `train.csv` contenant des informations sur les enchérisseurs et `bids.csv` contenant des données sur les enchères elles-mêmes. Les données comprennent des variables telles que `bidder_id`, `auction`, `merchandise`, et des étiquettes indiquant si l'enchérisseur est un robot (`outcome = 1`) ou un humain (`outcome = 0`).

---

## Analyse exploratoire des données (AED)

### Prétraitement des données

Les données ont été nettoyées en fusionnant les ensembles `train.csv` et `bids.csv` par `bidder_id`, en traitant les valeurs manquantes et en supprimant les données non pertinentes.

### Analyse exploratoire des données

L'analyse des données a révélé des insights importants sur la répartition des résultats d'enchères entre humains et robots, ainsi que sur les tendances temporelles et géographiques des enchères.

---

## Feature Engineering

### Description de démarche

Le feature engineering a impliqué la création de nouvelles caractéristiques telles que le nombre total d'enchères par utilisateur, la proportion d'enchères robotiques par pays, et l'analyse des comportements d'enchères par adresse IP et URL.

### Choix des features

Les features sélectionnées incluent celles qui ont montré une corrélation significative avec la prédiction des résultats d'enchères robotiques, comme démontré par l'analyse de corrélation et l'importance des features dans les modèles.

---

## Modélisation Prédictive

### Decision Tree (DT)

Un modèle d'arbre de décision a été entraîné avec une précision de 94% pour la classification des enchérisseurs humains et robots. L'importance des features a été évaluée pour interpréter les résultats.

### Random Forest (RF)

Un modèle de Random Forest a été configuré avec une précision de 94% et une AUC de 95%. L'analyse des features a montré des similitudes et des différences par rapport au modèle d'arbre de décision.

### Gradient Boosting (GB)

Le modèle Gradient Boosting a atteint une précision de 95% et une AUC de 98%, montrant une performance améliorée par rapport aux modèles précédents. L'analyse des features a souligné l'importance des URLs et d'autres caractéristiques dans la prédiction des résultats d'enchères.

---

## Comparaison des modèles

La comparaison des modèles a été réalisée sur plusieurs métriques telles que la précision, le rappel, le F1-score et l'AUC-ROC, montrant que le Gradient Boosting offre un équilibre optimal entre ces métriques pour la détection des enchères robotiques.

---

## Conclusion

Ce projet a réussi à développer des modèles efficaces pour la détection de comportements d'enchères robotiques en ligne. Les insights tirés de l'analyse des features ont contribué à une meilleure compréhension des différences entre les enchérisseurs humains et robots, offrant ainsi une base solide pour la prévention de la fraude dans les enchères en ligne.
