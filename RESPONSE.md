
# TP6 – Variables d'environnement, Inputs et Outputs

## Q1. Pourquoi la variable n'est-elle pas disponible dans la step qui l'a définie, mais seulement dans les suivantes ?

Lorsqu'une variable est écrite dans GITHUB_ENV, GitHub Actions la rend disponible uniquement aux étapes suivantes du même job. La step qui écrit la variable ne peut donc pas l'utiliser immédiatement.

## Q2. Quelle est la portée de GITHUB_ENV ?

GITHUB_ENV possède une portée limitée au job courant. Les variables définies dans un job ne sont pas automatiquement disponibles dans les autres jobs.

## Q3. Que se passe-t-il si on utilise > au lieu de >> dans GITHUB_OUTPUT ?

L'opérateur > remplace le contenu du fichier, tandis que >> ajoute du contenu à la fin. Ainsi, avec plusieurs outputs, utiliser > peut écraser les outputs précédemment enregistrés.

## Q4. Pourquoi GITHUB_ENV ne suffit-il pas ici ?

GITHUB_ENV permet de transmettre des variables entre les étapes d'un même job. GITHUB_OUTPUT permet de définir des outputs de step, qui peuvent être exposés au niveau du job et transmis à d'autres jobs grâce à needs.

## Q5. Que se passe-t-il si on retire needs: build du job deploy ?

Sans needs: build, le job deploy n'a plus de dépendance déclarée envers build et peut s'exécuter en parallèle. Il ne peut donc pas récupérer les outputs avec needs.build.outputs.
