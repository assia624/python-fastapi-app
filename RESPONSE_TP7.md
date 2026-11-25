
# TP7 – Actions tierces et actions personnalisées

## Q1. Pourquoi actions/checkout n'a-t-il pas besoin de with alors que setup-node en a besoin ?

L'action actions/checkout@v4 utilise des paramètres par défaut suffisants pour récupérer le dépôt courant. En revanche, actions/setup-node@v4 a besoin du paramètre node-version pour savoir quelle version de Node.js installer. Le bloc with permet de transmettre ce paramètre.

## Q2. Pourquoi le job verify ne retrouve-t-il pas report.txt sans l'artefact, alors que les deux jobs partagent le même dépôt ?

Chaque job GitHub Actions s'exécute généralement sur un runner indépendant avec son propre système de fichiers. Les fichiers créés dans le job build ne sont donc pas automatiquement accessibles dans le job verify. Il faut utiliser upload-artifact pour sauvegarder le fichier et download-artifact pour le récupérer dans l'autre job.

## Q6. Pourquoi actions/checkout doit-il s'exécuter avant l'appel d'une action locale ?

L'action locale se trouve dans le dépôt. actions/checkout récupère le code source du dépôt sur le runner. Sans cette étape, le dossier contenant l'action locale n'est pas encore disponible et GitHub Actions ne peut pas la trouver.

## Q7. Pourquoi shell: bash est-il obligatoire sur les steps run d'une action composite ?

Dans une action composite, chaque étape utilisant run doit préciser le shell à utiliser. La propriété shell permet à GitHub Actions de savoir quel interpréteur exécuter pour la commande.
