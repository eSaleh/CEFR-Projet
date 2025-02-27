# Projet CEFR - Prédiction du niveau CECRL de textes en anglais
## Description du projet
Ce projet a été développé dans le cadre de la compétition Kaggle "Prediction of the CEFR level of English texts". L'objectif est de prédire automatiquement le niveau de compétence linguistique en anglais selon le Cadre Européen Commun de Référence pour les Langues (CECRL).
## Contexte
Le CECRL est un cadre développé par le Conseil de l'Europe pour définir et décrire différents niveaux de maîtrise d'une langue étrangère. Il établit six niveaux de référence (A1, A2, B1, B2, C1 et C2), bien que cette compétition se concentre uniquement sur cinq niveaux (A1, A2, B1, B2 et C1).
Dans ce challenge, nous avons développé un algorithme basé sur l'apprentissage automatique et l'apprentissage profond pour prédire le niveau de compétence d'un apprenant à partir de ses productions écrites en anglais.

## Technologies utilisées
Notre projet repose sur les technologies et bibliothèques suivantes :

* Python : Langage de programmation principal
* Transformers (Hugging Face) : Pour l'implémentation et le fine-tuning des modèles BERT, RoBERTa, DistilBERT, GPT-2 et DistilGPT-2
* Preprocessing : Fonctions de prétraitement fournies par le projet Kaggle pour la normalisation des textes
* Pandas : Pour la manipulation et l'analyse des données structurées
* Scikit-learn : Pour l'implémentation des modèles baseline (Random Forest et SVM), l'évaluation des performances et le système de vote

## Notre approche
Notre solution combine plusieurs modèles pour obtenir des prédictions robustes et précises :
1. Modèles baseline
Nous avons d'abord implémenté des modèles classiques pour établir une référence de performance :

Random Forest : Un modèle d'ensemble qui construit plusieurs arbres de décision et fusionne leurs prédictions.
SVM (Support Vector Machine) : Un modèle discriminant particulièrement adapté aux tâches de classification comme celle-ci. Les SVMs sont efficaces pour cette tâche car ils se concentrent sur la frontière entre les classes plutôt que sur la modélisation des distributions de chaque classe.

2. Modèles transformers
Nous avons ensuite exploré plusieurs architectures basées sur les transformers, qui excellent dans le traitement du langage naturel :

BERT : Bidirectional Encoder Representations from Transformers, qui utilise un encodage bidirectionnel pour comprendre le contexte.
RoBERTa : Une version optimisée de BERT avec un entraînement amélioré.
DistilBERT : Une version plus légère et plus rapide de BERT qui conserve 97% de ses performances.
GPT-2 : Un modèle génératif qui, bien que conçu pour la génération de texte, peut être adapté pour la classification.
DistilGPT-2 : Une version distillée de GPT-2, offrant un bon équilibre entre performance et efficacité.

3. Ensemble voting
Pour notre solution finale, nous avons implémenté un système de vote majoritaire qui combine les prédictions de tous nos modèles avec une importance égale. Cette approche permet de :

Réduire la variance et améliorer la stabilité des prédictions
Limiter l'impact des erreurs individuelles de chaque modèle
Améliorer la robustesse face à différents styles d'écriture et niveaux de langue

## Structure du projet
```
├── datasets/              # Données d'entraînement et de test
└── README.md              # README.md du projet
└── bert.ipynb              # Ce fichier qui s'occupe de l'entraînement des modèles type BERT
└── gpt2.ipynb              # Ce fichier qui s'occupe de l'entraînement des modèles type GPT-2
```
## Résultats
Notre approche d'ensemble a permis d'obtenir des résultats significativement meilleurs que les modèles individuels, démontrant l'efficacité de la combinaison de différentes architectures pour cette tâche de classification linguistique.

## Équipe
Ce projet a été réalisé par Elie Saleh, Victor Berhault et Raphaël Brochenin.