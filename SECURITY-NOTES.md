
# TP7 – Security Notes

## Vérification du dépôt actions/setup-node

Dépôt officiel : https://github.com/actions/setup-node

- Créateur : GitHub.
- Badge créateur vérifié : à vérifier sur la page du dépôt.
- Nombre d'étoiles : à relever sur GitHub au moment de la vérification.
- Dossier contenant le code source : `src`.

## Q3. Pourquoi faut-il épingler une version (@v4) plutôt que @main ?

Il est préférable d'utiliser une version identifiée comme @v4 plutôt que @main, car la branche main peut être modifiée à tout moment. Une mise à jour non contrôlée pourrait introduire un changement inattendu ou malveillant. L'utilisation d'une version précise améliore la stabilité et la reproductibilité du workflow. Pour une sécurité renforcée, on peut épingler l'action sur un SHA de commit complet.

## Q4. Le badge « créateur vérifié » garantit-il qu'une action est sûre ? Justifiez.

Non. Le badge créateur vérifié confirme l'identité du créateur sur GitHub, mais ne garantit pas que le code de l'action est totalement sûr. Il faut également examiner le code source, les permissions demandées, les dépendances et les mises à jour de l'action.

## Q5. Citez deux vérifications à faire avant d'utiliser, en production, une action d'un fournisseur inconnu.

1. Examiner le code source de l'action, ses dépendances et les permissions nécessaires afin de détecter des comportements suspects.
2. Vérifier la réputation du fournisseur, l'activité du dépôt, les mises à jour, les issues et les éventuelles vulnérabilités. Il est également recommandé d'épingler l'action sur un SHA de commit précis.
