# Installation de Git

> Avant de commencer à utiliser Git, il faut qu’il soit disponible sur votre ordinateur. Même s’il est déjà installé, c’est probablement une bonne idée d’utiliser la dernière version disponible. Vous pouvez l’installer soit comme paquet ou avec un installateur, soit en téléchargeant le code et en le compilant par vous-même.

## Installation sur Linux :

> Si vous voulez installer les outils basiques de Git sur Linux via un installateur binaire, vous pouvez généralement le faire au moyen de l’outil de gestion de paquet fourni avec votre distribution. Sur Fedora, par exemple, vous pouvez utiliser dnf :

```
$ dnf install git-all
```
> Sur une distribution basée sur Debian, telle que Ubuntu, essayer apt-get :

```
$ apt-get install git-all
```
> Pour plus d’options, des instructions d’installation sur différentes versions Unix sont disponibles sur le site web de Git, à http://git-scm.com/download/linux.

## Installation sur Windows :

> Il existe aussi plusieurs manières d’installer Git sur Windows. L’application officielle est disponible au téléchargement sur le site web de Git. Rendez-vous sur http://git-scm.com/download/win et le téléchargement démarrera automatiquement. Notez que c’est un projet nommé Git for Windows (appelé aussi msysGit), qui est séparé de Git lui-même ; pour plus d’information, rendez-vous à http://msysgit.github.io/.

> Une autre méthode facile pour installer Git est d’installer Github for Windows. L’installateur inclut une version en ligne de commande avec l’interface graphique. Elle fonctionne aussi avec PowerShell et paramètre correctement les caches d’authentification et les réglages CRLF. Nous en apprendrons plus sur ces sujets plus tard, mais il suffit de savoir que ces options sont très utiles. Vous pouvez télécharger ceci depuis le site de Github for Windows, à l’adresse http://windows.github.com.