# PHP Composer

![composer](https://getcomposer.org/img/logo-composer-transparent.png)

Dans cet article, vous allez voir la définition et l'installation de Composer. 

Vous pouvez également lire [cet article](composer/utiliser-composer.md), pour l'utiliser concrêtement dans un projet PHP.

## Qu'est-ce que PHP Composer

Si vous avez déjà écrit en PHP avant, vous avez probablement constaté qu'on a le sentiment de souvent réinventer la roue pour des tâches communes telles que l'authentification des utilisateurs, la gestion de base de données ou de la demande de routage. PHP dispose de frameworks matures qui ont déjà résolu tous ces problèmes, donc ça ne serait pas plus facile de récupérer des éléments de code dont nous avons besoin dans chaque framework?

Si vous vouliez débuter manuellement avec des fonctionnalités de Zend, Symfony ou Laravel, alors cela deviendrait très difficile à gérer. Chaque bibliothèque peut également avoir des dépendances, et ainsi vous finirez par vous perdre, surtout si vous êtes plusieurs à travailler sur votre projet.

C'est à ce moment là où le composer entre en jeu. Composer est un gestionnaire de dépendance pour PHP. Compositeur va gérer les dépendances dont vous avez besoin sur une base de projet. Cela signifie que composer va mettre toutes les bibliothèques requises(et leurs dépendances) en un seul endroit du endroit du projet.

Ce type de gestion des dépendances dans un projet ne sont pas un nouveau concept, et, en fait, une grande partie de Composer est en fait inspiré de la NPM de Node.js et Bundler de Ruby.

Vous pourriez également utiliser PEAR. PEAR est un gestionnaire de paquets PHP établie qui gravite autour de PHP depuis des années. Cependant, PEAR a été abandonnée par de nombreux développeurs PHP pour un certain nombre de raisons. Tout d'abord, une grande partie du code dans PEAR n'est pas à jour. Deuxièmement, PEAR vous oblige à installer le système de paquets, plutôt que sur une base de projet. Cela signifie que si vous avez déjà un projet qui repose sur un ensemble un peu plus âgés, vous êtes foutu.

## Installation de Composer

L'installation de Composer est vraiment très simple et tout peut être fait en ligne de commande.

Dans votre terminal préféré, lancez les commandes suivantes:

```shell
$ > curl -s https://getcomposer.org/installer | php
$ > sudo mv composer.phar /usr/local/bin/composer
```

La première commande télécharge le fichier composer.phar sur votre ordinateur. La seconde déplace le ficher composer.phar dans le dossier *bin* qui est accessible de façon globale sur le poste.


Maintenant, lancez la commande suivante:

```shell
$ > composer
```

> Si vous avez bien installé Composer, cette commande affichera une liste de commande disponible avec leurs descriptions.


## Utiliser Composer

Maintenant que vous avez Composer d'installé, vous pouvez l'utiliser pour mettre en place les packages obligatoires dans votre projet. Pour faire un fichier de configuration Composer, nous avons juste besoin de créer un fichier JSON **composer.json** à la racine du projet.

Par exemple, si tu veux utiliser Slim Framework, vous pouvez create le fichier composer.json suivant:

```json
{
  "require": {
    "slim/slim": "2.*"
  }
}
```

Pour installer Slim via Composer, vous pouvez lancer simplement la commande suivante à travers le terminal :

```shell
$ > composer install
```

Ceci va télécharger automatiquement Slim dans le projet dans le dossier : *vendor/slim/slim*.


## Autoloading

Maintenant que vous avez tous les différents packages, vous devez intégrer l'autoload dans votre projet.

Heureusement, Composer est également livré avec un fichier de chargement automatique, qui est capable d'autoloader les fichiers dans les projets que vous avez télécharger.

Pour utiliser l'autoloader de Composer, incluez dans le fichier bootstrap (index.php) de votre projet la ligne suivante:

```php
require 'vendor/autoload.php';
```

Maintenant, vous pouvez commencer à utiliser les nouvelles librairies sans s'inquiéter du chargement.

Par exemple:

```php
// Autoload
require 'vendor/autoload.php';

// Instantiate a Slim application
$app = new \Slim\Slim();

// Define a HTTP GET route
$app->get('/hello/:name', function ($name) {
    echo "Hello, $name";
});

// Run the Slim application
$app->run();

```


## Conclusion ##

La gestion des packages est clairement une bonne pratique pour les développements PHP. Des langues tels que Ruby ont montré comment il est incroyablement facile à utiliser des paquets au sein de projets communs, pouvant résoudre en une fois des problèmes, et vous pouvez arrêter de perdre du temps en tant que développeur en réinventant constamment la roue.

Tous les Frameworks populaires se sont déjà positionnés à utiliser Composer, et beaucoup de développeurs diffusent leur code via composer.

# Sites #

- [Site officiel](https://getcomposer.org/)
