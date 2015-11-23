#Installation d'un poste Mac de développement

## Préalable

Pour débuter sur Mac, il est nécessaire d'installer Hombrew via la commande suivante :

```shell
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```


> Plus informations sur [http://brew.sh/]()

## Mode d'emploi

- Télécharger le fichier installation.zip ([en cliquant ici](https://github.com/CareLabsSAS/documentation-interne/raw/master/poste/script/installation.zip))
- Décompresser le fichier
- Ouvrir un terminal
- aller sur le path du fichier (probablement avec la commande ``cd ~/Downloads``)
- lancer le script d'installation avec la commande : ``./install.sh``
- Suivre les indications du script

## Que fait le script?

Script Shell (bash) servant à installer tout le système dev pour les macs à ChequeSanté, Respectivement, entre les balises de commentaire, il y a:

- Recupération et stockage temporaire dans la variable "PASSWD" du mot de passe de la DB mysql, en read caché
- copie des fichiers temporaires dans /tmp
- installation des différents éléments nécessaires pour le dev
- creation du dossier Sites dans le home, vers lequel sont redirigés les virtualhosts
- Création du fichier mysql.sock nécessaire au fonctionnement de mysql
- Modification de php.ini pour contenir la bonne timezone ainsi que les bonnes limites
- Création de la db mysql dans le bon dossier
- Linkage symbolique des fichiers .plist dans /Users/{nom d'utilisateur}/Library/LaunchAgents et démarrage des services
- Modification du mdp root de la db mysql avec le mdp stocké (PASSWD)
- Modification des droits, puis du fichier /etc/hosts pour prendre en compte les différents domaines du site
- Creation du fichier utilisateur et mise en place dans /private/etc/apache2/users/
- Modification du fichier httpd.conf pour prendre en compte les hotes virtuels, le modules php5 et le mod_rewrite.
- ajout des parametre user dans httpd.conf
- création du dossier "config" et modification de ses droits dans /usr/local/Cella/phpmyadmin/{version_phpmyadmin}/share/phpmyadmin
- configuration des vhosts
- Installation de zsh et oh-my-zsh pour un terminal plus ergonomique
- Redemarrage de apache2