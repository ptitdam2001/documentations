# Bower
![](https://avatars1.githubusercontent.com/u/3709251?v=3&s=400)

## Description

Bower fait partie d'une panoplie de services de nouvelle génération destinés à automatiser un maximum de tâches à votre place. 

Le but de cet outil développé par l'équipe de Twitter est de gérer les dépendances de votre projet.

## C'est quoi, une dépendance ?

Lorsque vous débutez un nouveau projet, votre première tâche est de créer (ou de copier-coller) l'arborescence de vos fichiers et dossiers.

Votre mission suivante est d'aller visiter un par un les outils incontournables pour votre projet : jQuery, Modernizr, Bootstrap, etc. et d'installer les nouvelles versions de ces outils... ou alors de mettre à jour vos propres modules les uns après les autres.

Avouez que vous gagneriez du temps à ne plus vous soucier de ce genre de tâches répétitives quotidiennes.

Tous les outils tels que jQuery, Modernizr ou Bootstrap sont des dépendances que Bower va vous aider à installer en une ligne de code.

La liste des dépendances inscrites dans le registre de Bower est pour le moins impressionnante, et parmi lesquelles vous trouverez un bon nombre de célébrités :

- Twitter Bootstrap
- jQuery
- html5boilerplate
- font-awesome
- modernizr
- html5shiv
- normalize
- jQuery mobile
- grunt
- purecss
- angular
- zepto
- phonegap
- ionic

## Installation

Deux pré-requis sont nécessaires au bon fonctionnement de Bower :

- Node.js (et son manager NPM, Node Packaged Modules)
- Git

Votre console ouverte, l'installation de Bower s'exécute en une simple instruction :

```shell
npm install -g bower
```

## Utilisation

### Charger une dépendance

Nous allons à présent installer notre première dépendance. Il s'agira - au hasard - de KNACSS, le mini framework CSS.

Dans la console, positionnez-vous sur votre dossier de travail et exécutez simplement :

```shell
bower install knacss
```

L'ensemble du projet Github KNACSS, à sa dernière version, se verra automatiquement téléchargé et installé dans un dossier **bower_components** de votre projet ! 

Pour savoir quelles autres dépendances peuvent être ainsi automatiquement récupérées, il suffit de vérifier leur existence dans le répertoire de Bower.

Pour installer une dépendance dans une version précise, ce n'est guère plus compliqué. Il suffit de préciser la version souhaitée à la suite d'un dièse (#) :

```shell
bower install knacss#2.9.1
```

### Mettre à jour une dépendance

Pour mettre à jour une ou plusieurs dépendances de votre projet, l'ordre à donner est update :

```shell
bower update knacss
```

Il est également possible de gérer plusieurs dépendances à la fois.

Pour cela, la création d'un fichier **bower.json** contenant toutes les informations requises est nécessaire.

Voici un exemple-type de fichier JSON :

```json
{
    "name": "projet",
    "dependencies": {
        "knacss": "latest",
        "html5shiv": "latest",
        "box-sizing-polyfill": "latest",
        "modernizr": "latest",
        "jquery": "1.10.2"
    }
}
```

Pour en savoir plus sur la configuration du fichier bower.json, n'hésitez pas à consulter le site de [Bower](http://bower.io/docs/config/).

### Modifier le chemin par défaut

Le chemin par défaut d'installation des dépendances est **bower_components**.

Vous pouvez modifier cette destination en créant un fichier dédié que vous devrez nommer **.bowerrc** et qui se trouvera dans le voisinage de bower.json.

Voici un exemple de contenu de .bowerrc indiquant à Bower que les fichiers à gérer se trouvent dans le répertoire "inc" :

```shell
{
  "directory": "inc/"
}
```

### Enregistrer votre dépendance dans le répertoire de Bower

Chacun est libre d'ajouter son propre outil au sein du registre de Bower, sous deux conditions :

- il doit être à libre disposition sur Github
- un fichier bower.json doit être présent à la racine du projet

Voici à titre d'exemple le fichier bower.json décrivant la dépendance KNACSS :

```json
{
  "name": "KNACSS",
  "version": "2.9.1",
  "homepage": "http://www.knacss.com/",
  "authors": [
    "Raphaël GOETTER, Alsacreations"
  ],
  "description": "KNACSS is a minimalist, responsive and extensible style sheet to kick-start your HTML / CSS projects. It relies on common best practices and experience on the topic.",
  "main": "css/knacss.css",
  "keywords": [
    "css", "framework", "reset", "responsive", "rwd", "boilerplate", "workflow"
  ],
  "license": "WTFPL",
  "ignore": [
    "**/.*",
    "node_modules",
    "bower_components",
    "test",
    "less/knackLESS.zip",
    "tests",
    "README.md"
  ]
}
```

L'enregistrement à proprement parler passe par l'instruction bower register, suivi du nom de l'application et du chemin vers le fichier Git. Par exemple :

```shell
bower register knacss git@github.com:raphaelgoetter/KNACSS.git
```

Bower vous demande alors une validation, que vous acceptez et c'est fini : votre dépendance devrait à présent apparaître dans le répertoire de Bower.


## Conclusion

Bien que pratique et rapide, Bower n'en demeure pas moins un "simple" gestionnaire de dépendances : il n'est pas prévu pour construire des dossiers de projets complets, ni pour concaténer ou minifier des ressources. Pour ce genre d'aspirations, et pour aller plus loin, il vous faudra lorgner du côté d'autres outils tels que Yeoman ou Grunt.

## Sites

- [site officiel](http://bower.io)