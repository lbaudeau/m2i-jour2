
## Les branches du depots

master          - cette branche contient le code de production. Tout le code de développement est fusionné en masterquelque temps.
develop         - cette branche contient du code de pré-production. Lorsque les fonctionnalités sont terminées, elles sont fusionnées pour se développer.

ces branches sont verrouillés. Seuls les PR acceptés (examinés par deux développeurs) peuvent être fusionnés.

les mises a jours sur develop se fond par pull request 

Au cours du cycle de développement, diverses branches de support sont utilisées:


### `<branch-type>/<branch-name>`

#### `<branch-type>`
```
feature/<feature-name>          - chaque nouvelle fonctionnalité aura un préfixe feature.
refactor/<feature-name>         -
fix/<bug-name>                  - corrections, régressions et corrections rapides.
chore/<chore-name> 
doc/<feature-name> 
tests/<test-related-code>       - tout test lié à notre infrastructure d'automatisation de test - notre framework Selenium, nos dépendances de test, nos tests unitaires, d'intégration et d'interface graphique.
perf/<performance-name> 

rfc/<feature-name>              - c'est une branche instable et sera rebasée à l'avenir. Il est seulement poussé pour la révision du code.
junk/<experiment-name>           - chaque recherche, chaque POC (Point of Concept) et tout autre code associé sont effectués dans les branches expérimentales. Ces branches ne sont jamais fusionnées en développement 
 ou en master et sont supprimées une fois "l'expérience" terminée.

infra/<prerelease-version> -
prerelease/<prerelease-version> -
release/<release-version>       - les branches de publication sont prêtes pour le déploiement, code testé en production. Tous les tests doivent réussir la branche de la dernière version.

```

```RegEx
^(feature|refactor|fix|conf|doc|tests|perf|rfc|junk|prerelease|release||)\/[a-z0-9._-]+$
```

De plus, vous pouvez les combiner ensemble:

feature / eglebegle / refactor / xyzzy - utiliser /refactor/ne fait qu'ajouter de la sémantique
feature / xyzzy / rfc / xyzzy-2.0 - juste pour revoir le code, puis refactoriser / corriger les problèmes, rebaser et fusionner pour créer une branche
Nous avons décidé d'utiliser hyphen-notationpour les nom

Autre :
<contexte>/(<périmètre>/)<fonction>
soit : <author>/<branch-type>/<branch-name>






#### `<name>`
Utilisez toujours des tirets pour séparer les mots et restez bref.

#### Examples
```
feat/renderer-cookies
hotfix/dockerfile-base-image
bug/login-ie
```


## Nommage des Pull Requests

Le format à respecter est le suivant : [#<PR_ID>] [<TAG>] <DESCRIPTION> (US-<US_ID>)., ex : "[#123] [FEATURE] Création de compte (US-987)."

PR_ID
PR_ID correspond au numéro de la PR généré par GitHub. Pour l'obtenir il faut... créer une PR depuis une branche.

Le fait d'utiliser le PR_ID plutôt que le numéro de story – pour rappel, généré par Trello dans le board du Product Backlog – permet de naviguer en un clic jusqu'aux modifications de code associées.

TAG
Nom	Usage
FEATURE	PR relative à une story
BUGFIX	PR relative à une correction d'un bug (hors itération)
CLEANUP	PR relative à du refactoring
INFRA	PR relative à du code technique / d'infra
DOC	PR relative à de la documentation

DESCRIPTION
La description de l'US doit être en français, car il s'agit d'un produit francophone et qu'on souhaite que les gens, même loin de l'informatique, s'intéressent à notre CHANGELOG.

US_ID
US_ID correspond à l'identifiant unique de la story dans le Product Backlog, généré et géré par Trello.




