## Lab 3

1. Quel est le meilleur modèle ? Peut-on le prouver ?
Oui. Dans MLflow je trie les runs par f1 : trial-1 et trial-3 sont à 0.889, trial-2 à 0.333. C'est enregistré avec la date donc c'est une preuve. Je garde trial-3 car il est plus simple (sans salaire).

2. Peut-on redonner exactement le modèle de l'essai 1 ?
Oui, chaque run garde son propre modèle. On le recharge avec mlflow.sklearn.load_model("runs:/<id>/model"), plus besoin de réentraîner.

3. Un camarade peut-il reproduire mon travail ?
En partie. Il a le code sur Git, et chaque run garde les paramètres et les versions des librairies (requirements.txt). Mais l'environnement n'est pas forcément le même, ça sera réglé avec Docker.