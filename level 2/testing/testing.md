
# Testing Logiciel



## Qualité et Test

Les phases de test dans le cycle de développement d'un produit logiciel permettent **d'assurer un niveau de qualité défini en accord avec le client.**

## Test d'intégration

Dans le monde du développement informatique, le test d'intégration est une phase dans les tests, qui est précédée des tests unitaires et est généralement suivi par les tests de validation

**dans le test d’intégration chacun des modules indépendants du logiciel sont assemblés et testés dans l’ensemble**

## Intégration continue

L'intégration continue est un ensemble de pratiques utilisées en génie logiciel consistant à vérifier à chaque modification de code source que le résultat des modifications ne produit pas de régression dans l'application développée.

Un outil d'intégration continue est ensuite nécessaire, tel que TeamCity,CruiseControl ou Jenkins (fork de Hudson) pour le langage Java par exemple. D'autres outils, comme SonarQube ou Jacoco,

## Méthode d’approche de l’intégration

Il existe plusieurs méthodes pour les tests d’intégration dont voici les plus courants :Top-down, Bottom-up, Sandwich et Big-bang

**Top-down**  On teste les modules les plus hauts puis ceux en dessous . On obtient donc les tests de : • première étape • 1 • seconde étape • 1, 2 et 3 • troisième étape • 1, 2, 3, 4, 5 et 6 • quatrième étape • 1, 2, 3, 4, 5, 6, 7, 8 et 9

**Bottom-up**  On teste les modules du plus bas niveau puis ceux plus hauts qui les appellent. On obtient donc : • première étape • 7 • 8 • 9 • seconde étape • 4 • 5, 7 et 8 • 9 et 6 • troisième étape • 2, 4, 5, 7 et 8 • 3, 6 et 9 • quatrième étape • 1, 2, 3, 4, 5, 6, 7, 8 et 9

**Big-bang**  Il s’agit d'une intégration non-incrémental . On intègre tous les modules d'un coup juste après les tests unitaires.



## Test unitaire

le test unitaire (ou « T.U. », ou « U.T. » en anglais) **est une procédure permettant de vérifier le bon fonctionnement d'une partie précise d'un logiciel ou d'une portion d'un programme (appelée « unité » ou « module »).** Cependant, les méthodes Extreme programming (XP) ou Test Driven Development (TDD) ont remis les tests unitaires, appelés « tests du programmeur », au centre de l'activité de programmation.

## Extreme programming

**La méthode XP préconise d'écrire les tests en même temps, ou même avant la fonction à tester (Test Driven Development).**

Ceci permet de définir précisément l'interface du module à développer. Les tests sont exécutés durant tout le développement, permettant de visualiser si le code fraîchement écrit correspond au besoin.

## Utiliser des mocks

**Les mocks sont des objets permettant de simuler un objet réel de façon contrôlée ;** dans certains cas, l'utilisation de mock est primordial, pour un gain de temps de couverture de code, et de fiabilité des tests : 

## Test de validation

Le test de validation **permet de vérifier si toutes les exigences client décrites dans le document de spécification d'un logiciel, écrit à partir de la spécification des besoins, sont respectées.**

## Test de performance

Un test de performance est un test dont l'objectif est de déterminer la performance d'un système informatique. Cette définition est donc très proche de celle de test de charge où l'on mesure le comportement d'un système en fonction de la charge d'utilisateurs simultanés. 
## Test driven development

Le test-driven development (TDD) ou en français développement piloté par les tests est une technique de développement de logiciel **qui préconise d'écrire lestests unitaires avant d'écrire le code source d'un logiciel.**

## Relecture de code(code review)

Une autre méthode d'analyse statique, parmi les plus empiriques, **consiste à faire lire le code source d'une application par une personne expérimentée mais extérieure à l’équipe de développement.**


**outils**  gerrit,openstack

## Tests système

Les tests système de logiciel ou de matériel réfèrent à un processus de test d'un système intégré afin d'évaluer sa conformité aux exigences spécifiées.

**Les tests système appartiennent à la classe des tests de type boîte noire, et en tant que tels, ne devraient exiger aucune connaissance de la conception interne du code ou de la logique**



## Test de régression

est de régression : tests d’un programme préalablement testé, **après une modification, pour s’assurer que des défauts n’ont pas été introduits ou découverts dans des parties non modifiées du logiciel.**


