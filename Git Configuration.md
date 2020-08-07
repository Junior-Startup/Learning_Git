# Configuration de base

> Initialisation de votre dossier en local qui va être lié avec Github.
on doit exécuter la commande suivante pour que les commandes de Git peuvent être lues par la terminale.
```
$ cd user/desktop/monDepot

$ git init

```

> Vous devez créer un repository sur Github
```
aller sur le navigateur
```

> Il va falloir tout d’abord récupérer l’URL du dépôt distant.
```
Allez dans GitHub et accédez au dépôt distant de notre projet, puis Cliquez sur le bouton Clone or download.

```
> Vous avez la fameuse URL dont nous allons avoir besoin. Copiez-la dans le presse-papier, retournez sur votre teminale et tapez la commande suivante :

```
$ git remote add  https://github.com/exemple/ProjetOpenSource.git

```
> Maintenant que notre dépôt local pointe sur le dépôt distant, nous allons cloner son contenu et le dupliquer en local. Afin de réaliser le clonage, nous allons utiliser la commande 

```
$ git clone https://github.com/exemple/ProjetOpenSource.git

```
Cela devrait afficher ces petites lignes de commandes !

 ![](assets/image_clone.png?)
