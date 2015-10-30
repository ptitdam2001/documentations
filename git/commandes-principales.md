# Principales commandes #

## Configuration de GIT ##

Afin de vous éviter que Github vous demande tout le temps votre login/mot de passe github, il faut taper les commandes suivantes:

```shell
git config --global user.email [email enregistré sur github]
git config --global user.name '[Nom Prénom]'
```

Ou bien il faut créer une clé public SSH et l'enregistrer sur votre compte Github.

## Utilisation dans un projet ##

### Pour installer localement un projet, il faut cloner un projet : ###

```shell
git clone [url du repository] [nom du dossier de destination]
```

### Pour commiter des modifications, il est possible de le faire sous la forme de ligne de commandes, cela se passe en 3 étapes : ###

* mettre les fichiers dans le pool avant le commit/pusher

```shell
git add [chemin +nom du fichier ou . ]
```

* on commit les modification mais ce n'est pas encore par le serveur GIT
```shell
git commit -m "[message du commit]"
```

*  envoie un ou plusieurs commit sur le serveur GIT
```shell
git push origin [nom de la branche]
```

### Gestion des branches  : ###
* création de la branche
```shell
git branch [nom de la branche]
```

* on se met sur la nouvelle branche
```shell
git checkout [nom de la branche]
```

=> le paramètre -b à la commande git checkout permet d'executer en simultané les 2 commandes ci-dessus

* On initialise la branche sur le serveur, celle-ci est prête pour travailler dessus
```shell
git push origin [nom de la branche]
```

* Supprimer une branche
```shell
git branch -d [branche]
```

=> en remplaçant -d par -D, on force la suppression

* Renommer une branche
```shell
git branch -m [ancienne branche] [nouveau nom]
```

=> Renome la branche _ancienne_ (la branche courante si ancien est omis) en nouveau. Si nouveau existe, la commande échoue mais il est possible d'écraser nouveau en mettant -M à la place -m

### Mettre à jour sa branche en fonction de master ###

* Mettre à jour la branche locale en fonction de la branche sur le serveur GIT

```shell
git pull origin [nom de la branche]
```

* 2 possibilités de merge :

** Merge
```shell
git merge [branche]
```

=> fusionne la branche en paramètre dans la branche courante

```shell
git merge -s ours [branche]
```

=> Fusionne la branche en paramètre dans la branche courante mais en ignorant tous les changements qu'elle introduit, juste pour créer le point de parenté

** Rebaser sa branche en fonction de master, pour cela, il faut que le master local soit également à jour

```shell
git rebase master

//lorsqu'il y a des conflits, il faut les résoudre et continuer le rebase avec les commandes suivantes
git rebase --continue //valide les modifications
git rebase --skip //on ne prend pas en compte les modifications du commit
git rebase --abort // on annule le rebase
```

## Extraction de fichiers entre 2 commits ##

Cette commande permet de zipper tous les fichiers qui ont été commité entre 2 numéros de commit.
Par contre, il faut absolument se mettre de repertoire du projet.

```shell
git archive --output=/Users/damiensuhard/Desktop/patch.zip HEAD $(git diff --name-only HEAD~5 HEAD)
```

Pour l'exemple, ci-dessus, la sous-commande git diff --name-only HEAD~5 HEAD permet de lister les fichiers commité entre le dernier commit ( = HEAD) et le 5 commits plus tôt ( = HEAD~5).

## Supprimer les branches locales lorsque celles-ci sont mergées sur MASTER ##

```shell
git branch --merged master | grep -v "\* master" | xargs -n 1 git branch -d
```

## Divers ##

* Visualiser l'évolution des branches
```shell
git log --oneline --graph --decorate
```

# Documentation externe #

Pour la documentation (en français) : https://git-scm.com/book/fr/v1
