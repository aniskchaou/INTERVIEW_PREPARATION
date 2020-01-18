

## Integration Continue

**L'intégration continue**  est un ensemble de pratiques utilisées en génie logiciel, **consistant à vérifier, à chaque modification de code source que le résultat des modifications ne produit pas de régression dans l'application développée.**
![Image result for continuous integration](https://geekflare.com/wp-content/uploads/2019/12/ci.jpg)

## exemple

Dans une entreprise, il est courant qu'il y ait plusieurs développeurs travaillant sur la même application, et même sur le même code. Avant l'apparition de  **Git**, comme contrôle de code source distribué, il existait d'autres outils comme SVN ou CVS, mais le dépôt était  **centralisé**, ce qui menait à de  **nombreux problèmes d'intégration**  du code.

## But

Le principe de l'intégration continue est justement **de détecter ces problèmes d'intégration au plus tô**t dans le cycle de développement.

## Etapes
![Flow Of Continuous Integration](https://acadgildsite.s3.amazonaws.com/wordpress_images/devops/What_is_Jenkins/02_CI_Image.jpg)
## **Planifiez** votre développement

Afin de **savoir quoi développer**, il est nécessaire d'avoir à disposition un **outil permettant la collaboration entre les développeurs.** Cet outil permettra notamment de gérer les différentes releases et toutes les fonctionnalités, de garantir la priorité du backlog, etc.
`exemple :` **Jira**, **GitLab**, **Confluence**, **ALM Octane** ou encore **Pivotal Tracker**.

## **Compilez** et intégrez votre code.
#### Le contrôle de code source

Le code source se doit d'être disponible à chaque instant sur un dépôt central.
Pour faire du contrôle de source, vous retrouverez les outils  **Git**,  `Example :` **Subversion**,  **GitHub**,  **GitLab**,  **Perforce**  ou bien  **Bitbucket**.

#### L'orchestrateur
Ensuite, toutes les étapes doivent être automatisées par un **orchestrateur**, qui saura reproduire ces étapes et gérer les dépendances entre elles.
`exemple :` **Jenkins**, **TeamCity**, **Azure DevOps**, **GitLab CI**, **Concours CI**, **Travis CI** ou **Bamboo**.

## Testez votre code

#### Les tests unitaires

Dans cette étape,  **l'orchestrateur se charge de lancer les tests unitaires à la suite de la compilation**. Ces tests unitaires, généralement avec un framework associé, garantissent que le code respecte un certain niveau de qualité.
`exemple :` **JUnit**, **NUnit** ou encore **XUnit**

## Mesurez la **qualité** de votre code

Maintenant que les tests unitaires sont écrits et exécutés, nous commençons à avoir une meilleure qualité de code, et à être rassurés sur la fiabilité et la robustesse de l'application.
## Gérez les livrables de votre application
L'étape de qualité de code mesure aussi d'autres métriques, comme le nombre de vulnérabilités au sein du code, la couverture de test, mais aussi les [_code smells_](https://fr.wikipedia.org/wiki/Code_smell) (qui sont des mauvaises pratiques à ne pas implémenter), la [complexité cyclomatique](https://fr.wikipedia.org/wiki/Nombre_cyclomatique) (complexité du code applicatif) ou la duplication de code.
`Exemple :` **SonarQube**, **Cast** ou **GitLab Code Quality**.

Le code, une fois compilé, **doit être déployé dans un dépôt de livrables, et versionné.** Les binaires produits sont appelés **_artefacts_**. Ces artefacts doivent être accessibles à toutes les parties prenantes de l'application, afin de pouvoir les déployer et lancer les tests autres qu'unitaires (test de performance, test de bout en bout, etc.).
Exemple : **Nexus**, **Artifactory**, **GitLab repository**, **Quay**, **Docker Hub**