# ![](https://pbs.twimg.com/profile_images/426240683704209409/95FQxeT2_normal.png) Gulp #

## Présentation ##

Gulp est un outil qui vous aide à travers différentes tâches au moment de développements web. Il est souvent utilisé sur des tâches front tel que :

- Faire tourner un serveur Web
- Recharger automatiquement du navigateur web chaque fois qu'un fichier est enregistré
- Utilisation préprocesseurs comme Sass ou LESS
- Optimisation des assets tels que CSS, JavaScript et images

Ceci n'est pas une liste exhaustive de choses que Gulp peut faire. Vous pouvez même construire un générateur de site statique avec Gulp. Alors oui, Gulp est extrêmement puissant, mais vous devrez apprendre à utiliser Gulp si vous voulez créer vos propres processus de construction personnalisés.


## Pourquoi Gulp ? ##

Des outils comme Gulp sont souvent désignés comme des «outils de construction», parce qu'ils sont des outils pour exécuter les tâches pour la construction d'un site web. Les deux outils de construction les plus populaires en ce moment sont Gulp et Grunt. Mais il ya d'autres bien sûr. 

Il y a déjà plusieurs articles couvrant la différence entre Grunt et Gulp et pourquoi vous pourriez utiliser un par rapport à l'autre. Vous pouvez consulter ces articles  si vous êtes intéressé à en savoir plus. 

La principale différence est la façon dont vous configurez un flux de travail avec eux. Les Configurations de Gulp ont tendance à être beaucoup plus court et plus simple par rapport à Grunt. Gulp a aussi tendance à aller plus vite.

Pour faire simple, son point fort réside dans le fait qu’il utilise des streams (un flux de données - en mémoire) et qu’il limite au maximum l’utilisation de fichiers. Au point qu’il existe une police Gulp pour vous dire.

Dans la pratique cela évite d’avoir un gruntfile qui, si on imagine une task sass -> autoprefixer -> csso, passe 3 fois par des lectures/écritures sur le système de fichiers.

![](http://jaysoo.ca/images/grunt-flow-2.png)


Et du coup au lieu d’avoir un fichier de conf d’une soixantaine de lignes, on arrive à avoir quelque chose de concis (une vingtaine de ligne seulement).

![flux Gulp](http://jaysoo.ca/images/gulp-flow.png)

## Installation ##

Avant d'installer Gulp, vous devez avoir Node.js (Node) d'installer sur votre ordinateur. Si vous n'avez pas encore installé Node, vous pouvez le télécharger le package depuis le [site web](https://nodejs.org/en/).

Une fois Node installé, vous pouvez maintenant installé Gulp en exécutant la commande suivante:

```
$ sudo npm install gulp -g
```

> Note: Only Mac users need the sudo keyword. (if you don't want to use sudo, see this [article](https://docs.npmjs.com/getting-started/fixing-npm-permissions)). And remember the "$" in the code above just symbolizes the command prompt. That's not actually part of the command you run.

La commande d'installation NPM que nous utilisons ici est une commande qu'utilise Node Package Manager (npm) pour installer Gulp sur votre ordinateur.

Le drapeau *-g* dans la commande demande à npm d'installer Gulp globalement sur votre ordinateur, ce qui permet d'utiliser la commande gulp partout sur votre système.

Les utilisateurs MAC nécessitent le mot clé *sudo* car ils ont besoin des droits administrateur pour installer globalement gulp.


## Liens utiles ##

- [Site web de Gulp](http://gulpjs.com/)
- [Site web de Grunt](http://gruntjs.com/)


## Articles ##

- [Introduction Gulp(en)](http://www.sitepoint.com/introduction-gulp-js/)
- [Gulp pour débutant(en)](https://css-tricks.com/gulp-for-beginners/)
- [Retour d'experience](http://insertafter.com/fr/blog/retour_experience_gulp.html)