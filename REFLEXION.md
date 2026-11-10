## Lab 3

1. Quel est le meilleur modèle ? Peut-on le prouver ?
Oui maintenant on peut. Dans l'interface MLflow j'ai trié les runs par f1 et on voit que trial-1 et trial-3 ont le même score (0.889) alors que trial-2 est beaucoup plus bas (0.333). Tout est sauvegardé donc je peux le montrer. Entre les deux je prends trial-3 parce qu'il donne le même résultat sans utiliser le salaire.

2. Peut-on redonner exactement le modèle de l'essai 1 ?
Oui, contrairement au TP1 où model.pkl était écrasé à chaque fois. Là chaque run a son propre modèle, et avec son id on peut le recharger (load_model) sans refaire l'entraînement. Je l'ai testé avec reload_model.py.

3. Un camarade peut-il reproduire mon travail ?
Pas complètement. Il peut récupérer le code depuis GitHub et il voit les paramètres et les versions des librairies dans chaque run. Par contre il n'aura pas mes runs (mlruns n'est pas sur git) et son environnement peut être différent. Pour ça il faudra Docker plus tard.