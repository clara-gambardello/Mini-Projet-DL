# Mini-projet Deep Learning

Projet de deep learning - Classification d'images de races de chiens par réseaux de neurones convolutionnels (CNN).

## Le projet

Classification d'images en 5 catégories de races de chiens (Cairn, Chihuahua, Dingo, Pyrénées, Samoyède) à partir d'un jeu de données de 936 images couleur (256×256 pixels).

Le projet compare plusieurs approches, de la plus simple à la plus performante :

* **CNN entraîné from scratch**
* **Transfert learning** avec InceptionV3 (extraction de features, poids pré-entraînés gelés)
* **Data augmentation** pour améliorer la généralisation
* **Fine-tuning** du modèle pré-entraîné (dégel progressif des dernières couches)

## Résultats

| Métrique | Sans augmentation | Avec augmentation | Fine-tuning |
|----------|-------------------|-------------------|-------------|
| Accuracy Train | 99.8% | 95.9% | **97.94%** |
| Accuracy Test | 94.1% | 93.2% | **97.55%** |
| Loss Train | 0.012 | 0.104 | **0.0826** |
| Loss Test | 0.605 | 0.323 | **0.0998** |
| Écart Train-Test | 5.7% | 2.7% | **0.39%** |
| Nombre d'epochs | 26 | 12 | **14** |

La combinaison data augmentation + fine-tuning donne les meilleurs résultats : plus de 97% de précision sur le jeu de test, un écart train-test minimal (bonne généralisation, pas de surapprentissage), et une convergence rapide (14 epochs) grâce aux poids pré-entraînés.

## Structure du projet

* `Images_Small/` : jeu de données, organisé en un sous-dossier par race
* `Projet Gambardello DL.ipynb` : notebook complet (préparation des données, modèles, entraînement, évaluation)

## Lancer le projet

1. Cloner le projet ou télécharger les fichiers
2. Installer les packages nécessaires

```
pip install tensorflow opencv-python numpy matplotlib seaborn scikit-learn
```

3. Ouvrir `Projet Gambardello DL.ipynb` dans Jupyter ou Google Colab (idéalement avec accélération GPU)

## Auteur

Clara GAMBARDELLO
Mini-projet Deep Learning (2026)
