# Les Branches

>Une branche dans Git est simplement un pointeur déplaçable vers l'un des commits. Le nom de la branche par défaut dans Git est *Master*. Lorsque vous commencez à effectuer des commits, vous recevez la branche *Master* qui pointe vers le dernier commit que vous avez fait.
A chaque fois que vous commettez, le pointeur de la branche *Master* avance automatiquement.

## Créer une nouvelle branche
>Que se passe t-il quand vous créez une nouvelle branche ?
Supposons que vous souhaitiez créer une nouvelle branche appelée **testing**. Pour cela, on se sert de la commande suivante :
```shell
$ git branch testing
```
>Cela crée un nouveau pointeur vers le même commit sur lequel vous êtes actuellement.

![](assets/fig1.png?)
>Comment Git sait-il dans quelle branche vous êtes actuellement? Il garde un pointeur spécial appelé **HEAD**.
Dans ce cas,vous êtes toujours en *Master*. La commande git branch a uniquement créé une nouvelle branche.Elle n'a pas basculé vers cette branche.

![](assets/fig2.png?)
>Vous pouvez facilement voir cela en exécutant une simple commande git log qui vous montre où les pointeurs de branche pointent. Cette option s'appelle --decorate.
```shell
$ git log --oneline --decorate
f30ab (HEAD -> master, testing) Add feature #32 - ability to add new formats to the
central interface
34ac2 Fix bug #1328 - stack overflow under certain conditions
98ca9 Initial commit
```
>Vous pouvez voir les branches master et testing qui se trouvent juste à côté du commit f30ab.

## Changer de branche
>Pour basculer vers une branche existante, vous exécutez la commande git checkout. Passons à la nouvelle branche **testing** :
```shell
$ git checkout testing
```
>Cela déplace HEAD pour qu'il pointe vers la branche **testing**.

![](assets/fig3.png?)
>Quelle est la signification de cela ? Eh bien, faisons un autre commit:
```shell
$ git commit -a -m 'made a change'
```
![](assets/fig4.png?)
>C'est intéressant, car maintenant votre branche **testing** a avancé, mais votre branche **Master** pointe toujours vers le commit sur lequel vous étiez lorsque vous avez exécuté git checkout pour changer de branche. Retournons maintenant à la branche **Master** :
```shell
$ git checkout master
```
![](assets/fig5.png?)
>Il est important de noter que lorsque vous changez de branche dans Git, les fichiers de votre répertoire de travail vont changer. Si vous passez à une ancienne branche, votre répertoire de travail sera rétabli pour ressembler à ce qu'il était la dernière fois quand vous vous êtes engagés dans cette branche.

>Apportons quelques modifications et recommençons:
```shell
$ git commit -a -m 'made other changes'
```
>L'historique de votre projet a maintenant divergé. Vous avez créer et basculer vers une nouvelle branche. Vous avez effectué quelques modifs, puis vous êtes revenus à la branche **Master** et de nouvelles modifs ont été apportées.
Toutes ces modifications sont isolées dans des branches séparées : vous pouvez basculer entre les branches et les fusionner lorsque vous le souhaitez.

![](assets/fig6.png?)
>Vous pouvez le voir facilement avec la commande git log. Si vous exécutez git log --oneline --decorate --graph --all ça va afficher l'historique de vos commits, tout en montrant où se trouvent vos pointeurs de branche et comment votre historique a divergé.
```shell
$ git log --oneline --decorate --graph --all
* c2b9e (HEAD, master) Made other changes
| * 87ab2 (testing) Made a change
|/
* f30ab Add feature #32 - ability to add new formats to the central interface
* 34ac2 Fix bug #1328 - stack overflow under certain conditions
* 98ca9 initial commit of my project
```
## Créer une nouvelle branche et y basculer en même temps
>Cela peut être fait en une seule opération avec git checkout -b
*nouvellebranche*.
## Le Branching & le merging
>Passons en revue un exemple simple de branchement et de fusion avec un flux de travail que vous pourriez utiliser dans
le monde réel. Vous suivrez ces étapes:
>1. Travailler sur un site Web.
>2. Créer une branche pour une nouvelle user story sur laquelle vous travaillez.
>3. Travailler dans cette branche.

>À ce stade, vous recevrez un appel indiquant qu’un autre problème est critique et que vous avez besoin d’un correctif. Vous ferez ce qui suit :
>1. Basculer vers votre branche de production.
>2. Créer une branche pour ajouter le correctif.
>3. Une fois le test terminé, fusionner la branche du correctif et passer en production.
>4. Revenir à votre user story d'origine et continuer à travailler.

### Branching
>Tout d'abord, disons que vous travaillez sur votre projet et que vous avez déjà quelques validations sur branche **Master**.

![](assets/fig7.png?)

>Vous avez décidé de travailler sur l'issue n ° 53 dans le système de suivi des issues de votre entreprise. Pour créer une nouvelle branche et y basculer en même temps, vous pouvez exécuter la
commande checkout avec le commutateur -b :
```shell
$ git checkout -b iss53
Switched to a new branch "iss53"
```
![](assets/fig8.png?)

>Vous travaillez sur votre site Web et vous faites quelques commits.

![](assets/fig9.png?)

>Vous recevez maintenant un appel indiquant qu'il y a un problème avec le site Web et que vous devez le résoudre immédiatement. Avec Git, vous n'avez pas à déployer votre correctif avec les modifications iss53 que vous avez apportées.

>Tout ce que vous avez à faire est de revenir à votre **Master**.

>À ce stade, le répertoire de travail de votre projet est exactement tel qu'il était avant de commencer à travailler
sur le problème # 53, et vous pouvez vous concentrer sur votre correctif.

>Ensuite, vous avez un correctif à faire. Créons une branche de correctif sur laquelle vous pourrez travailler jusqu'à ce qu'elle soit terminée:
```shell
$ git checkout -b hotfix
Switched to a new branch 'hotfix'
$ vim index.html
$ git commit -a -m 'Fix broken email address'
[hotfix 1fb7853] Fix broken email address
1 file changed, 2 insertions(+)
```
![](assets/fig10.png?)
>Vous pouvez exécuter vos tests, vous assurer que le correctif est comme vous le souhaitez et enfin fusionner la branche du correctif retour dans votre branche **Master** pour déployer en production. Vous faites cela avec la commande git merge:
```shell
$ git checkout master
$ git merge hotfix
Updating f42c576..3a0874c
Fast-forward
index.html | 2 ++
1 file changed, 2 insertions(+)
```
>Vous remarquerez l'expression "Fast-forward" dans cette fusion. Parce que le commit C4 pointé par le
le correctif de branche dans lequel vous avez fusionné était juste avant le commit C2 sur lequel vous étiez, Git déplace simplement le pointeur vers l'avant. Pour exprimer cela d'une autre manière, lorsque vous essayez de fusionner un commit avec un commit accessible en suivant l'historique du premier commit, Git simplifie les choses en déplaçant le pointeur vers l'avant car il n'y a pas de commits divergents à fusionner - c'est ce qu'on appelle une «Fast-forward».

![](assets/fig11.png?)
>Une fois votre correctif déployé, vous êtes prêts à revenir au travail que vous faisiez avant que vous ne soyez interrompus. Cependant, vous allez d'abord supprimer la branche du correctif, vu que vous n'en avez plus besoin.
```shell
$ git branch -d hotfix
Deleted branch hotfix (3a0874c).
```
>Vous pouvez maintenant revenir à votre branche de travail en cours sur l'issue #53 et continuer à travailler dessus.

```shell
$ git checkout iss53
Switched to branch "iss53"
$ vim index.html
$ git commit -a -m 'Finish the new footer [issue 53]'
[iss53 ad82d7a] Finish the new footer [issue 53]
1 file changed, 1 insertion(+)
```
![](assets/fig12.png?)

>Il convient de noter ici que le travail que vous avez effectué dans votre branche de correctif n'est pas contenu dans les fichiers de votre branche iss53.






