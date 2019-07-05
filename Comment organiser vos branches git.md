Je me souviens d'avoir implémenté git dans mon équipe. Je pense que c'était il y a plus de 6 ans. A cette époque, un modèle de branchement git réussie par Vincent Driessen si vous voulez apprendre à travailler avec git efficacement la lecture était nécessaire. Depuis lors, je suis le style "Git Flow". Cependant, au cours de la dernière année, j'ai été influencé par de nombreux développeurs de la communauté et j'ai commencé à utiliser git de différentes manières en fonction des projets sur lesquels je travaillais.

Avant d’entrer dans les différents styles de branchement, il est important de garder à l’esprit que, bien que de nombreux clients git traitent les barres obliques ("/") comme un séparateur de répertoires, les dossiers et les répertoires n’existent pas dans la spécification git. Vous verrez cela implémenté dans de nombreux clients d'interface utilisateur, mais je ne l'ai jamais trouvé sur les clients de la console ou sur des sites Web tels que Github ou GitLab.

Cela étant dit, explorons différentes manières d’organiser les branches afin de ne pas vous perdre dans un océan de code.

Gitflow
Bien que Gitflow ne mentionne pas les dossiers de branches, de nombreux développeurs utilisent "Branch branches", "Branches de correctifs" et "Libérer les branches" et créent des dossiers en conséquence. 
Donc, fondamentalement, une organisation GitFlow aurait ces trois dossiers:

fonctionnalités]
correctif [es] / corrections
libération [s]
Comme il n'y a pas de document public qui en parle, j'ai vu des copies de travail utilisant ces dossiers au pluriel et d'autres au singulier.



Gitflow avec des stéroïdes
Je me suis retrouvé en train d'ajouter deux autres dossiers à mes dépôts Gitflow:

Docs: Pour les branches liées aux documents de démarquage ou de publication.
Tâche: Pour les branches qui ne sont ni des fonctionnalités ni des correctifs. Tels que nettoyer les scripts ou les refactors.
BPMP (Branch-Push-Merge-Prune)
J'ai souvent vu cela dans de nombreux projets. Branch-push-merge-prune est la méthode anti-dossier. Je ne dis pas que le chaos est une façon d'organiser des branches. Les personnes utilisant cette méthode aiment avoir leur copie de travail propre. Ils se contentent de créer des branches, de pousser, de créer une demande d'extraction, puis de supprimer la branche (manuellement ou via git fetch prune) dès que le PR est fusionné.



Basé sur le module
Je me suis retrouvé à utiliser ce que j'appelle un modèle de branchement "basé sur des modules" sur un gros projet où je me suis perdu dans une mer de fonctionnalités et de correctifs. J'ai donc commencé à créer des branches basées sur ses modules.



Vous pouvez combiner Gitflow avec cette approche basée sur des modules, quelque chose comme "backoffice / billing / fixes / billing-values", mais c'est peut-être trop.

Basé sur la version
J'ai d'abord vu Meir utiliser cette approche et je l'ai aimé. C'est génial pour des projets comme Puppeteer-sharp où la feuille de route est claire. 
Dans un référentiel basé sur la version, vous créez chaque branche dans un dossier "vX.X". Ce qui est génial à propos de cela, c’est qu’il est basé sur le temps, il est donc plus facile de trouver des branches et de supprimer des anciennes versions avec cette simple commande git:

git branch | grep -e "vX.X/" | xargs git branch -D



Encore une fois, cela pourrait être mélangé avec les dossiers Gitflow, mais ...

Basé sur le billet
Si les numéros de tickets (tickets, numéros ou ce que vous appelez) font partie de la langue de votre équipe, utilisez un système basé sur les tickets qui conviendrait parfaitement. 
Vous pouvez utiliser un dossier, tel que "tickets / 242" ou "issues / 242", ou simplement l'appeler "242".



À base d’Emoji
Si aucun de ces systèmes ne vous convient, vous pouvez suivre l'idée de Nick et implémenter un système basé sur Emoji :)



Mots finaux
Deux dernières pensées pour fermer ce post. Premièrement, si vous travaillez dans une équipe où vous contrôlez normalement les autres branches, par exemple pour des tests locaux, je vous recommanderais de partager le style avec votre équipe. 
Et enfin, nettoyez votre copie de travail fréquemment. Cela vous aidera à trouver rapidement vos succursales et à accélérer votre repo locale.