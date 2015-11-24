# Utiliser composer dans un projet

A travers ce tutoriel, nous allons créer un mini-projet utilisant Composer.

ce projet sera une simple page, qui écrit des logs, et pour cela, nous souhaitons utiliser le package monolog ( [https://github.com/Seldaek/monolog]() )

## Comment ça marche
Nous allons créer notre premier projet avec composer. Pour aller plus loin dans la démo, nous allons également utiliser le package mongodb-odm de doctrine. Pourquoi ? Il a plein de dépendance, il illustrera parfaitement cet article.

Comment marche Composer ? Vous insérez vos dépendances dans le fichier composer.json (cf [voir ici](composer/index.md)), ensuite exécutez :

```
composer install
```

Ce dernier va télécharger tout ce dont il a besoin pour que vos packages soient télécharger et fonctionnels. Cela veut dire qu’il va aussi télécharger des packages que vous n’avez pas demandé, mais qui sont nécessaire à l’exécution d’un package que vous avez demander.

Il crée alors un fichier *composer.lock*, qui contient les informations de l’ensemble des packages installés. Ce fichier se met à jour automatique, **et ne doit jamais être modifié manuellement**.

Vous pouvez mettre à jour vos packages avec la commande :

```
composer update
```

Celle-ci va alors fetcher les dernières mises à jour disponibles, tout ne respectant les dépendances.

Un des autres intérêts de composer, est qu’il permet de gérer les versions des dépendances. Rendons nous par exemple sur la page packagist du framework Symfony 2: [http://packagist.org/packages/symfony/framework-standard-edition]()

Vous remarquerez qu’il existe un certain nombre de versions disponibles. Et pour chaque version, vous pouvez voir les dépendances ( noté Requires ), et les versions de ces dernières. L’avantage de ce système, c’est la garantie d’avoir un environnement de travail avec des dépendances compatibles entre elles.

## Notre premier composer.json

Il est temps pour nous d’écrire notre premier composer.json . Il va de soit, que le contenu de ce fichier sera en fait un json (ndlr: un objet en notation javascript ). Pour rappel, nous allons utiliser les packages monolog et doctrine mongodb.

Vous pouvez recherchez l'existence des packages via la commande : 

```shell
composer search monolog
```

Vous aurez un résultat de ce type :

```

monolog/monolog Sends your logs to files, sockets, inboxes, databases and various web services
monolog/monolog Sends your logs to files, sockets, inboxes, databases and various web services
monolog/monolog
kdyby/monolog Integration of Monolog into Nette Framework
symfony/monolog-bundle Symfony MonologBundle
thinframe/monolog Monolog Application
symfony/monolog-bridge Symfony Monolog Bridge
stackify/monolog Stackify logs and errors for Monolog
kamisama/monolog-init Very basic and light Dependency Injector Container for Monolog
logentries/logentries-monolog-handler A handler for Monolog that sends messages to Logentries.com.
m6web/monolog-extra-bundle Provide extra features for Monolog
cakephp/monolog CakePHP Monolog Plugin
enlitepro/enlite-monolog Monolog integration to Zend Framework 2
flynsarmy/slim-monolog Monolog logging support Slim Framework
wazaari/monolog-mysql A handler for Monolog that sends messages to MySQL
kmelia/monolog-stdout-handler A handler for Monolog that sends messages to stdout (with color).

```

Pour avoir de plus amples informations sur un package, la commande suivante vous aidera :

```shell
composer info monolog/monolog
```

Vous aurez l'affichage suivant:

```
name     : monolog/monolog
descrip. : Sends your logs to files, sockets, inboxes, databases and various web services
keywords : log, logging, psr-3
versions : dev-master, 1.18.x-dev, 1.17.2, 1.17.1, 1.17.0, 1.16.0, 1.15.0, 1.14.0, * 1.13.1, 1.13.0, 1.12.0, 1.11.0, 1.10.0, 1.9.1, 1.9.0, 1.8.0, 1.7.0, 1.6.0, 1.5.0, 1.4.1, 1.4.0, 1.3.1, 1.3.0, 1.2.1, 1.2.0, 1.1.0, 1.0.2, 1.0.1, 1.0.0, 1.0.0-RC1
type     : library
license  : MIT
source   : [git] https://github.com/Seldaek/monolog.git c31a2c4e8db5da8b46c74cf275d7f109c0f249ac
dist     : [zip] https://api.github.com/repos/Seldaek/monolog/zipball/c31a2c4e8db5da8b46c74cf275d7f109c0f249ac c31a2c4e8db5da8b46c74cf275d7f109c0f249ac
names    : monolog/monolog, psr/log-implementation

autoload
psr-4
Monolog\ => src/Monolog

requires
php >=5.3.0
psr/log ~1.0

requires (dev)
aws/aws-sdk-php ~2.4, >2.4.8
doctrine/couchdb ~1.0@dev
graylog2/gelf-php ~1.0
phpunit/phpunit ~4.0
raven/raven ~0.5
ruflin/elastica 0.90.*
swiftmailer/swiftmailer ~5.3
videlalvaro/php-amqplib ~2.4

suggests
aws/aws-sdk-php Allow sending log messages to AWS services like DynamoDB
doctrine/couchdb Allow sending log messages to a CouchDB server
ext-amqp Allow sending log messages to an AMQP server (1.0+ required)
ext-mongo Allow sending log messages to a MongoDB server
graylog2/gelf-php Allow sending log messages to a GrayLog2 server
raven/raven Allow sending log messages to a Sentry server
rollbar/rollbar Allow sending log messages to Rollbar
ruflin/elastica Allow sending log messages to an Elastic Search server
videlalvaro/php-amqplib Allow sending log messages to an AMQP server using php-amqplib

provides
psr/log-implementation 1.0.0
```


Nous allons prendre les versions dev-master de monolog et de mongodb-odm. Voilà notre fichier composer.json :

```json
{
    "require": {
        "monolog/monolog": "dev-master",
        "doctrine/mongodb-odm": "dev-master"
    },
    "minimum-stability": "dev"
}
```

Une petite particularité, étant donné que nous utilisons des packages en développement, nous devons ajouter « minimum-stability »: « dev » , qui impose à composer : "tu peux prendre des dépendances qui sont en développement". 

Vous êtes prêt ? Alors vous pouvez lancer votre installation :

```shell
composer install # ou alors php composer.phar install si vous ne l'avez pas installer globalement
```

Et voilà, composer va contrôler si vous avez tout ce qu’il vous faut, puis télécharger les packages. 

Voilà ma sortie au jour d’aujourd’hui :

```
aosix@aosix-VirtualBox /var/www/composerDemo $ composer install
Installing dependencies
  - Installing monolog/monolog (dev-master)
    Cloning ae31045917db536eedee8c6b6abed5052d115763

  - Installing doctrine/common (dev-master)
    Cloning 329d90ab8d6ed4c0b422d631caa5594c77c12055

  - Installing symfony/console (dev-master)
    Cloning 3b66f1056f5ac37146d3b755964e8a43a205f2f5

  - Installing symfony/yaml (dev-master)
    Cloning 6b3eb66a7c4495dcaa35a64dd93c8ba8c29f35d8

  - Installing doctrine/mongodb (dev-master)
    Cloning fdf44d850d7482b2cea7a0793d46999641c68e4f

  - Installing doctrine/mongodb-odm (dev-master)
    Cloning 70521c1c654ef6a42a7e88ed9bb98f9d3fe9fc0c

monolog/monolog suggests installing mlehner/gelf-php (Allow sending log messages to a GrayLog2 server)
monolog/monolog suggests installing ext-amqp (Allow sending log messages to an AMQP server (1.0+ required))
Writing lock file
Generating autoload files
```

On voit qu’à partir de mes deux paquets initiaux, composer a téléchargé les dépendances nécéssaires, notamment pour le package mongodb-odm.

Maintenant, vous avez dans votre dossier un nouveau dossier appelé **vendor**, avec à l’intérieur, les différents packages téléchargés. On y trouve également un fichier ***autoload.php***, qui va nous permettre de charger super facilement nos classes. Nous allons l’exploiter dès maintenant.

## Utilisation des packages téléchargés

Nous allons finalement utilisé les packages téléchargés et pour faire au plus simple, nous utiliserons uniquement le package monoglog ( tout le monde n’a pas une base mongodb en local ). L’interêt est de voir l’utilisation de l’autoloader, qui permet d’utiliser vos classes sans inclure le fichier où est déclaré la classe, mais un fichier qui se charge de trouver pour vous les classes ( pas vraiment – en fait il faut que le package respecte la norme PSR-0, voir [https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md]() )

```php
<?php

require('vendor/autoload.php');


use Monolog\Logger;
use Monolog\Handler\StreamHandler;


// On test que le dossier logs existe, sinon on le crée
if(! (file_exists('logs') && is_dir('logs')))
        mkdir('logs',0775);


// Initialisation des loggers
$log = new Logger('test_logger');
// Ce logger enregistrera tous les messages, DEBUG étant le niveau le moins important
$log->pushHandler(new StreamHandler('logs/all.log', Logger::DEBUG));
// Ce logger enregistera tous les messages ayant un niveau supérieur ou égal à WARNING
$log->pushHandler(new StreamHandler('logs/min_warning.log', Logger::WARNING));



$log->debug('Message de debug');
$log->warn('Message de warning');
$log->emerg('Grosse Erreur !!!!');
```

Et voilà ! Je ne vais pas vous expliquer comment marche Monolog, c’est assez simple, et surtout ce n’est pas l’objectif de cet article.