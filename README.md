# 18_alien_vs_predator_part_4

Optimisation de la Classification Alien vs Predator avec la Fusion de Techniques d'Apprentissage Profond

Introduction:
Dans cet épisode 4 d'Alien vs Predator, nous aborderons le développement d'un programme de vision par ordinateur visant à différencier avec précision un Alien d'un Predator. Le projet s'appuiera sur les enseignements des épisodes précédents, mettant en avant la technique de "transfer learning" et explorant les concepts de "data augmentation" et "features extraction" pour améliorer les performances du modèle.

Contexte du Projet:
Suite à la démonstration dans l'épisode 3 que le "transfer learning" peut drastiquement améliorer les performances d'un CNN sur un petit jeu de données, nous avons identifié un léger sur-apprentissage résiduel. L'objectif est d'éliminer ce sur-apprentissage tout en augmentant la précision du CNN. Pour ce faire, nous allons combiner la technique de "data augmentation" étudiée dans l'épisode 2 avec la méthode de "features extraction" vue dans l'épisode 3.

Étapes du Projet:

Chargement du Modèle VGG-16:

Charger à nouveau le modèle VGG-16.
Noter qu'il est impératif de "freezer" le modèle VGG-16 pour préserver ses poids et éviter une rétropropagation inutile.
Concaténation avec un Perceptron Multi-couches (MLP):

Concaténer le modèle VGG-16 avec un perceptron multi-couches.
Exemple de structure MLP:
python
Copy code
model.add(layers.Dense(units=256, activation='relu', input_dim=4 * 4 * 512))
model.add(layers.Dense(units=1, activation='sigmoid'))
La structure du MLP peut être optimisée, notamment en testant différents nombres de neurones dans la couche cachée.
Entraînement avec la Technique de "Data Augmentation":

Utiliser la technique de "data augmentation" pour entraîner l'ensemble du modèle.
Attention aux temps de calcul, et optimiser si nécessaire.
Livrables:

Fournir des Jupyter Notebooks documentés détaillant chaque étape du projet.
Critères de Performance:

Le code Python doit être clair, bien commenté et facile à comprendre.
La technique de "data augmentation" doit être correctement intégrée.
Les résultats doivent montrer une amélioration de la précision du CNN tout en éliminant le sur-apprentissage résiduel.
