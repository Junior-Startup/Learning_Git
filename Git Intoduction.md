# Introduction sur Git
## Git est un système de contrôle de version distribué Open Source . Voilà beaucoup de mots pour définir Git. Il se decompose en trois partie :

- **Système de contrôle**: cela signifie essentiellement que Git est un suivi de contenu. Ainsi, Git peut être utilisé pour stocker du contenu - il est principalement utilisé pour stocker du code en raison des autres fonctionnalités qu'il fournit.

- **Système de contrôle de version** : le code stocké dans Git ne cesse de changer à mesure que du code est ajouté. De plus, de nombreux développeurs peuvent ajouter du code en parallèle. Ainsi, le système de contrôle de version aide à gérer cela en conservant un historique des changements qui se sont produits. De plus, Git fournit des fonctionnalités telles que les branches et les fusions, que je couvrirai plus tard.

- **Système de contrôle de version distribué**  : Git a un référentiel distant qui est stocké dans un serveur et un référentiel local qui est stocké dans l'ordinateur de chaque développeur. Cela signifie que le code n'est pas seulement stocké dans un serveur central, mais que la copie complète du code est présente sur tous les ordinateurs des développeurs. Git est un système de contrôle de version distribué puisque le code est présent dans l'ordinateur de chaque développeur.


## Pourquoi un système de contrôle de version comme Git est nécessaire:
```
Les projets réels ont généralement plusieurs développeurs travaillant en parallèle. Un système de contrôle de version comme Git est donc nécessaire pour s'assurer qu'il n'y a pas de conflit de code entre les développeurs.

De plus, les exigences de ces projets changent souvent. Ainsi, un système de contrôle de version permet aux développeurs de revenir à une ancienne version du code.

Enfin, il arrive que plusieurs projets exécutés en parallèle impliquent la même base de code. Dans un tel cas, le concept de branchement dans Git est très important.
```