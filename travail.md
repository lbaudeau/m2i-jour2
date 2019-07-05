



# Archiver un dossier vide

creation d'une branche de travail b01

Poisitionner un fichier .gitkeep afin d'archiver un dossier. 

```bash
touch .gitkeep
```

Creer le fichier gitkeep de maniere recursive pour tous les dossiers de votre structure

```bash
find . -type d -empty -not -path "./.git/*" -exec touch {}/.gitkeep \;
```


creer un fichier .gitignore

```bash
echo 'xxx' > .gitignore 
```


# Récuperer un comit spécifique

permet dde recuperer un commit spécifique

```bash
git cherry-pick hash
```

