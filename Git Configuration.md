# Configuration de base

>Initialisation de votre dossier en locale qui va être liée avec github .
on doit exécuter la commande suivate pour que les commandes de git peuvent être lu par la terminale.
```
$ cd user/desktop/monDepot

$ git init

```

>vous devez créer un repository sur github
```
aller sur le navigateur
```

>Il va falloir tout d’abord récupérer l’URL du dépôt distant.
```
Allez dans GitHub et accédez au dépôt distant de notre projet, puis Cliquez sur le bouton Clone or download.

```
> vous avez la fameuse URL dont nous allons avoir besoin. Copiez-la dans le presse-papie.Retournez sur votre teminale, et tapez la commande suivante :

```
$ git remote add  https://github.com/exemple/ProjetOpenSource.git

```
>Maintenant que notre dépôt local pointe sur le dépôt distant, nous allons cloner son contenu et le dupliquer en local. Afin de réaliser le clonage, nous allons utiliser la commande 

```
$ git clone https://github.com/exemple/ProjetOpenSource.git

```
Cela devrait afficher ces petites lignes de commandes !

 ![](assets/15549712882555_9.png?)