---
author: Nicolas Borboën <<ponsfrilus@gmail.com>>
title: Introduction à Git
date: February 15, 2021
---

# Qu'est-ce que Git ?

> Git est un logiciel de **gestion de versions** décentralisé. C'est un logiciel
  libre créé par Linus Torvalds, auteur du noyau Linux, et distribué selon
  les termes de la licence GPLv2. En 2016, il s’agit du logiciel de gestion
  de versions le plus populaire qui est utilisé par plus de douze millions de
  personnes.

<cite>Git, <https://fr.wikipedia.org/wiki/Git></cite>

<aside class="notes">
  Shhh, these are your private notes 📝

  * First use <kbd>s</kbd> for speaker view
  * Use <kbd>ctrl</kbd>+<kbd>click</kbd> to zoom
  * Use <kbd>b</kbd> and slide go black
  * Use <kbd>esc</kbd> to view all slide
</aside>


## Pourquoi utiliser Git

![comit_Strip](./img/Strips-_Old-650-final1.jpg){ width=55% }
<!-- credit image: https://www.commitstrip.com/fr/2013/11/05/git-svn-ou/ -->


##  Git est un logiciel de gestion de versions décentralisé.

![](./img/cathedral_vs_bazaar.png){ width=60% class=border }
<!-- credit image: http://techidiocy.com/understand-git-clone-command-svn-checkout-vs-git-clone/ -->


## Décentralisé vs centralisé

![](./img/svn-repo.png){ width=65% }

SVN, CVS, Perforce (centralisés) vs Git, Mercurial, Bazaar (décentralisés)


# Fonctionnement

> Le seul dossier un peu particulier créé par Git est un dossier **.git** (c’est
  un dossier caché situé à la racine du projet). Il contient l’historique des
  modifications des fichiers et la configuration de Git pour ce projet.

<cite><https://openclassrooms.com/fr/courses/1233741-gerez-vos-codes-source-avec-git></cite>


## Utilisation locale

> La plupart des opérations de Git ne nécessitent que des fichiers et ressources
  locaux [...] Git vous fera penser que les dieux de la vitesse ont octroyé
  leurs pouvoirs à Git.

<cite>[Rudiments de Git (git-scm.com)](https://git-scm.com/book/fr/v1/Démarrage-rapide-Rudiments-de-Git#Presque-toutes-les-opérations-sont-locales)</cite>


## Les tripes de Git

* __objects__: stockage du contenu
* __tree__: répertoire
* __blob__: fichier (Binary Large OBject)
* __commit__: instantané
* __tag__: une étiquette pointant toujours sur un même commit
* __refs__: méchanisme interne pour représenter les branches et les tags

<cite><https://git-scm.com/book/fr/v1/Les-tripes-de-Git-Les-objets-Git></cite>


# Utilisation (pour démarrer)

* Initialisation d’un dépôt Git dans un répertoire existant<br>
  `$ git init`

* Récupération d'un dépôt distant dans un dépôt local<br>
  `$ git clone $URI`

<cite><https://git-scm.com/book/fr/v2/Les-bases-de-Git-Démarrer-un-dépôt-Git></cite>


## Utilisation (modifications dans le dépôt)

  * Placer de nouveaux fichiers sous suivi de version<br>
  `$ git add .`
  * Valider vos modifications<br>
  `$ git commit`
    * il ne concerne qu'une chose et une seule ;
    * il est le plus petit possible (tout en restant cohérent) (atomique).


<cite><https://git-scm.com/book/fr/v2/Les-bases-de-Git-Enregistrer-des-modifications-dans-le-dépôt></cite>


## Utilisation (état)

  * Vérifier l’état des fichiers<br>
    `$ git status`
  * Visualiser l’historique des validations<br>
    `$ git log .`
    * <https://coderwall.com/p/euwpig/a-better-git-log>

<cite><https://git-scm.com/book/fr/v2/Les-bases-de-Git-Visualiser-l'historique-des-validations></cite>


## Utilisation (avec d'autres personnes)

  * Envoyer ses modifications sur un serveur<br>
    `$ git push`
  * Récupérer des modifications depuis un serveur<br>
    `$ git pull`

<cite><https://git-scm.com/book/fr/v2/Les-bases-de-Git-Visualiser-l'historique-des-validations></cite>


# Branches

<!-- https://www.miximum.fr/blog/enfin-comprendre-git/ -->
![](./img/branches.png){ width=50% }<br>

  * Une branche n'est qu'une étiquette qui pointe vers un commit.
  * Elle permet d'avoir facilement des environnements de développement séparés (feature, bug fix).
  * Changer de branche modifie les fichiers dans votre répertoire de travail.

<cite><https://git-scm.com/book/fr/v1/Les-branches-avec-Git-Travailler-avec-les-branches></cite>


##  Utilisation (flow)

L'utilisation des branches peut être liée à des bonnes pratiques, par exemple :

  * <https://leanpub.com/git-flow/read>
  * <http://nvie.com/posts/a-successful-git-branching-model/>


## Utilisation (conflits)

Lors qu'un fichier est modifié par un autre utilisateur, ou que vous voulez
fusionner deux branches, il arrive qu'il soit nécessaire de résoudre des
conflits.

Afin de pouvoir résoudre les conflits visuellement, il existe des outils
adéquats, par exemple [Meld](http://meldmerge.org/). Pour définir l'outil
utilisé pour résoudre les conflits, utiliser la commande:
`$ git config merge.tool meld`


# Résumé

**Git de survie**

`git init` / `git clone`

`git add`, `git commit`

`git status` / `git diff` / `git log`

`git push` / `git pull`


## États

![](./img/areas.png)


## Relevant xkcd

![](./img/git_2x_xkcd1597.png){  width=35% }
<cite><https://xkcd.com/1597/></cite>


# Plateforme d'hébergement Git

Bien que l'utilisation de Git puisse être fait indépendament d'un service
d'hébergement, ces derniers apportent des fonctionnalités pratiques, notamment
dans le cadre du travail en équipe.


## Fonctionalités

  * visualisation des fichiers et des commits
  * édition en ligne
  * forks / pull request / merge request
  * issue tracker
  * CI/CD
  * wikis
  * social network pour développeurs


## Plateforme les plus connues

  * <https://github.com>
  * <https://gitlab.com>
  * <https://gitlab.epfl.ch>
  * <https://bitbucket.org>


# GUI

Git est fait pour être utilisé en ligne de commande. Cependant, il existe
plusieurs interface graphique pour l'utiliser :

  * `git instaweb --httpd=webrick`
  * `gitk`
  * [GitKraken](https://www.gitkraken.com)
  * [GitAhead](https://gitahead.github.io/gitahead.com/)
  * et plein d'autre : <https://git-scm.com/download/gui/>


## IDE

Git est intégrés à des IDE/éditeurs :

  * [Atom](https://atom.io/)
  * [VScode](https://code.visualstudio.com/)
  * [IntelliJ](https://www.jetbrains.com/idea/)
  * etc..


## Extras

Les programmes comme [Git Extras](https://github.com/tj/git-extras) ou
[gh cli](https://cli.github.com/) permettent de gagner beaucoup de temps.


# Pratique

![](./img/Alexander_Nestorov.gif)


## Installation

1. Installation git [doc](https://git-scm.com/book/fr/v2/Démarrage-rapide-Installation-de-Git)
2. Configuration de l'utilisateur [doc](https://git-scm.com/book/fr/v2/Démarrage-rapide-Paramétrage-%C3%A0-la-premi%C3%A8re-utilisation-de-Git)<br>
  `$ git config --global user.name "John Doe"`<br>
  `$ git config --global user.email johndoe@example.com`


## Pratique : initialiser un repo

  * Créer un dépôt local `$ git init` dans un répertoire
  * Manipulation:
    * création fichier, édition fichier ;
    * `$ git add fichier` "Staging aera"
    * `$ git commit -m "mon message de log" fichier` "Repository aera"
  * Utiliser `$ git status` entre les étapes


## Pratique : Créer un conflit

  * Modifier un fichier et le commiter
  * Création d'une branche sur le répertoire courant et switcher dessus
  `$ git checkout -b maBranche`
  * Editer les mêmes lignes du fichier dans la branche et le commiter
  * Retrouner sur la branche `master` : `$ git checkout master`
  * Fusionner `maBranche` dans `master` : `$ git merge maBranche`
  * Identifier le conflit avec `$ git status`
  * Résoudre le conflit, par exemple avec [Meld](http://meldmerge.org/)


## Pratique (conflits)

```
~/gitTest(branch:master) » git merge maBranche
Auto-merging fichier
CONFLICT (content): Merge conflict in fichier
Automatic merge failed; fix conflicts and then commit the result.
```
* Ouvrir l'outil de résolution de conflits :
  `$ git mergetool`
* Résoudre les conflits (le fichier central est le fichier final)
* Utiliser `$ git add fichier` et `$ git commit -m"Merge"`
  -> conflits résolus


## Pratique (conflits)

Utiliser une commande pour voir le graph des commits, par exemple :

  * `$ git log --graph` ou
  * `$ git log --graph --oneline --decorate --all`


# Conclusion

![](./img/version_all_the_things.jpg)


##

![](./img/in-case-of-fire-1-git-commit-2-git-push-3-leave-building2.png)


# Ressources [1]

* Starter Pack
  * Le site officiel : <https://git-scm.com/>
    * Les multiples clients : <https://git-scm.com/downloads>
    * Les pages de documentation : <https://git-scm.com/doc>
    * Le livre, en français : <https://git-scm.com/book/fr/>
  * [Juste un petit guide pour bien démarrer avec git. no deep shit ;)](http://rogerdudler.github.io/git-guide/)


## Ressources [2]

* Cours
  * [Learn Git in 7 minutes](http://www.codingdojo.com/blog/git-tutorial-for-beginners/)
    Un tutorial pour débutant avec une vidéo et une infographie.
  * [CodeSchool](https://www.codeschool.com/courses/try-git) / [GitTry](https://try.github.io)
    Les tutos officiels pour Git.
  * [Learn Git Branching](http://learngitbranching.js.org/)
    Un super site avec rendu visuel pour mieux comprendre le fonctionnement des branches.


## Ressources [3]

* Intro
  * <https://github.com/sdfepfl/git-basics>
  * <https://c4science.ch/source/git-demo/>
  * <https://noullet-gei.github.io/GIT/>


## Ressources [4]

* Divers
  * <http://think-like-a-git.net/>
  * <http://marklodato.github.io/visual-git-guide/index-fr.html>
  * <https://help.github.com/articles/git-and-github-learning-resources/>
  * <http://danielkummer.github.io/git-flow-cheatsheet/index.fr_FR.html>
  * <http://www.askaswiss.com/2016/01/12-useful-advanced-git-commands.html>
  * <https://www.miximum.fr/blog/enfin-comprendre-git/>
  * <https://moodle.insa-rouen.fr/pluginfile.php/87086/mod_resource/content/3/Git.pdf>


## Ressources [6]

* Awesome
  * <https://github.com/dictcp/awesome-git>
  * <https://github.com/git-tips/tips>


## Ressources [7]

* Cheat Sheets
  * <https://services.github.com/on-demand/downloads/fr/github-git-cheat-sheet.pdf>
  * <http://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf>
  * <https://github.com/arslanbilal/git-cheat-sheet>
  * <https://www.git-tower.com/blog/git-cheat-sheet/>
  * <https://www.atlassian.com/dms/wac/images/landing/git/atlassian_git_cheatsheet.pdf>
  * <http://www.cheat-sheets.org/saved-copy/git-cheat-sheet.pdf>


## Ressources [8]

* Infographie
  * [Learn Git in 7 minutes](http://www.codingdojo.com/blog/wp-content/uploads/Learn_Github_ArtEnhanced.jpg)
  * <https://github.com/aaasen/github_globe>


# À propos

Cette présentation a été faite dans le cadre des dojos de programmation
pour les apprentis informaticiens de l'[EPFL](http://www.epfl.ch). La
source est disponible sur le dépot [gitro — une petite introduction à
Git](https://github.com/epfl-dojo/gitro) <https://github.com/epfl-dojo/gitro>.
Elle est écrite en [MarkDown](https://daringfireball.net/projects/markdown/),
puis convertie en HTML avec [Pandoc](https://pandoc.org/) (et
[reveal.js](https://revealjs.com/)).


<!-- Use
  pandoc -t revealjs -V theme=simple -s -o myslides.html presentation-git.md && chromium "file://$(pwd)/myslides.html?print-pdf"

  pandoc -t revealjs -V theme=simple -V progress=true -V slideNumber=true -V spotlight=true --slide-level=2 -s -o myslides.html presentation-git.md && chromium "file://$(pwd)/myslides.html"

-->
<style>
  .reveal h1 { font-size: 2em; }
  .reveal h2 { font-size: 1.6em; }
  .reveal h3 { font-size: 1.4em; }
  .reveal h4 { font-size: 1.2em; }
  .reveal h5 { font-size: 1.1em; }
  .border { border: 1px solid #555; }
  .reveal blockquote { width: 100% }
  .reveal blockquote:before {
    display: block;
    padding-left: 10px;
    content: "\201C";
    font-size: 80px;
    position: absolute;
    left: -20px;
    top: -20px;
    color: #7a7a7a;
  }
  .reveal cite:before { content: "\2009 \2015 \2009"; }
  .reveal cite { font-size: 80%; }
  .reveal code {
    background-color: #eee;
    border-radius: 3px;
    font-family: courier, monospace;
    padding: 0 3px;
    font-size: 0.8em;
  }
</style>
