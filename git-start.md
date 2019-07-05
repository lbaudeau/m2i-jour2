# GitStart

Premirere journée de formation Git.

## Aide pour l'utilisation de GIT.

	1. Aller sur le site de GitHub.
	(github.com)

	2. Créer un compte ou se connecter.

	3. Créer un nouveau répertoire (new repository).
	ATTENTION : Ne pas cocher la case qui propose de créer le fichier README.md !

### Prérequis

	Installer l'outil GIT disponible en téléchargement :
	https://git-scm.com/download/win

### Créer un nouveau répertoire en ligne de commande.
--------------------------------------------------------------------
	
	1. Créer un répertoire qui va contenir un projet.
	(mkdir "MonProjet")

	2. Se placer dans le projet.
	(cd "MonProjet")

	3. Créer du contenu dans le projet.
	(echo "# MonProjet" >> README.md)

	4. Initialiser le Git local, la base de fichiers.
	(git init)

	5. Mettre à jour la révision (modification réalisé en le moment T0 et T1).
	(git add README.md OU git add .)

	6. Ajouter la révision dans la base de fichier. (Valider l'ajout des révisions.).
	(git commit -a -m "Ceci est un commentaire et il est obligatoire de le mettre 
	lorsqu'un COMMIT est réalisé. Il permet de decrire les modifications que 
	comporte la révision.")

	7. Connecter le Git local (la base de fichier locale) au site de GitHub (la base de fichier distante).
	(git remote add origin https://github.com/VotreNomUtilisateurGitHub/MonProjet.git)

	8. Uploader (pousser) le contenu de la base de fichier local sur la base de fichiers distant (Local -> Distant).
	(git push -u origin master)
	
Lorsque l'on a modifié en local un projet (fichiers/répertoires modifiés ou créés), que ce projet est connecté au git distant (git init, git remote add origin URL), il faut réaliser les étapes suivantes :
--------------------------------------------------------------------
	1. Mettre à jour la révision.
	(git add .)
	
	2. Valider l'ajout des révisions en les ajoutant dans la base de fichier local.
	(git commit -a -m "Décrire rapidement les modification approtées.")


	Cette suite d'action sera répétée tout au long de la journée, à chaque fois que des fichier modifiés auront été enregistré (par example).


	3. Pousser les modification de la base locale vers la base distante.
	(git push -u origin master)
	
	Cette action sera réalisée à la fin de chaque journée, une fois que les tests n'auraont pas mis en échec l'application (par example).

### Récupérer un répertoire déja existant sur GitHub (ne sera pas lié à votre compte GitHub)

	1. Se passer dans le répertoire des téléchargements.
	(cd "C:\Users\%USERNAME%\Downloads")
	
	2. Clonner le projet (= télécharger le projet)
	(git clone URL_DU_PROJET_COMMANCANT_PAR_HTTPS_ET_FINISSANT_PAR_.git)

### Récupérer un répertoire existant sur son propre compte GitHub
	
	1. Connecter la base de ficier locale à la base de fichier distante.
	
