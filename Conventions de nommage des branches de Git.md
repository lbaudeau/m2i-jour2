Vous avez donc décidé d'utiliser les branches de fonctionnalités pour gérer le développement de votre application. Toutes nos félicitations! (Si ce n’est pas le cas, consultez cet article sur les avantages des branches d’entités et sur la façon de les accomplir dans git).

Vous avez défini la structure de vos branches principales et la manière dont elles seront déployées dans vos différents environnements. Le moment est venu de commencer à travailler sur une nouvelle fonctionnalité. Vous extrayez la dernière version de develop et tapez git checkout -b ... mais comment l'appelez-vous? 
Le problème

C'est un problème aussi vieux que la programmation elle-même. Comme Phil Karlton l'a dit,

"Il n’ya que deux choses difficiles en informatique: l’invalidation du cache et le nommage".

Si vous travaillez en équipe, et même si vous ne l'êtes pas, sans une sorte de guide de style, vous allez vous retrouver avec des noms de branche comme:

cool-nouvelle-fonctionnalité
bugfixForThatOneIssue
story_123456
Si vous êtes comme moi, des noms comme ça vous dérangent et vous vous dites: «Il doit y avoir un meilleur moyen de le faire». Après avoir cherché sur Google pour trouver des idées et me présenter les mains vides, je me suis mis à créer ma propre convention de nommage pour les branches git.

Les objectifs
Comme beaucoup de startups ou de projets logiciels complexes, ASAPer utilise un ensemble d’outils pour nous aider à gérer nos cycles de développement. Actuellement, nous utilisons Pivotal Tracker pour le suivi des histoires, Git pour le contrôle de source et GitHub en tant que référentiel central pour les requêtes d'extraction, la révision de code et la fusion.

Lorsque je me suis mis à codifier un guide de style pour les noms de branche, je souhaitais que la convention de dénomination atteigne les objectifs suivants:

Être facile à lire (je peux dire quelle est la branche à partir d'une liste de branches)
Être lié au logiciel de gestion de l'histoire
Soyez facile à voir s'il s'agit d'une branche de fonctionnalité, d'un correctif de bogue, etc.
Être facile à taper
La solution
La convention de dénomination sur laquelle j'ai opté comporte trois sections:

Type d'histoire 
ft == Caractéristique
bg == Bug
ch == Corvée
Résumé court: 2-3 mots sur le contenu de la branche
Pivotal Tracker ID
Ces trois sections sont séparées par des traits d'union. Le résultat final ressemble à ceci:

{story type}-{2-3 word summary}-{pivotal tracker id}
Si nous travaillions sur une application de chat, comme WhatsApp par exemple, et notre histoire était une fonctionnalité qui donnait à l'utilisateur la possibilité d'envoyer son emplacement. Nous commencerions par une histoire de suivi cruciale ressemblant à ceci:



Nous allions le marquer comme démarré et copier l'ID. Maintenant que nous avons tous les composants nécessaires, nous pouvons extraire une branche de fonctionnalité portant le nom suivant:

ft-send-my-location-66296256  
En plus d'atteindre notre objectif de relier une demande d'attraction à son histoire dans un outil de suivi pivotant, l'utilisation de l'id sert un objectif moins évident: elle nous oblige à marquer l'histoire comme étant en cours lorsque nous allons créer une nouvelle branche. Cela nous oblige également à faire en sorte que toutes les branches soient liées à une histoire.

Voilà pour être facile à taper…
Cette solution a atteint 3 de mes 4 objectifs initiaux, mais qu’en est-il d’être facile à taper? Nous avons trouvé quelques moyens d’améliorer le processus de travail avec ces noms de branches plutôt difficiles à manier.

Onglets complets
En téléchargeant le script bash git-completion et en ajoutant quelques lignes à votre fichier .bashrc, vous pouvez compléter les noms de branches par des tabulations, comme vous le feriez pour les noms de fichiers.

Basculer entre les branches git
Il est assez courant de basculer entre une branche principale, comme develop, et une branche fonctionnelle. Ceci est trivial en utilisant git checkout -, ou gc -si vous avez gcaliasé pour git checkoutm'aimer.

Copier et coller
Si tout échoue, copier et coller est votre ami. Assurez-vous simplement que vous utilisez un terminal offrant une bonne prise en charge du presse-papiers du système.

Voilà donc comment nous gérons actuellement les noms de nos succursales et cela fonctionne très bien pour nous. J'aimerais entendre parler d'autres conventions de nommage.