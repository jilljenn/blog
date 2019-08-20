---
title: Générateurs de pages statiques
authors:
  - Jill-Jênn Vie
layout: post
published: true
permalink: /2016/02/27/generateurs-de-pages-statiques/
categories:
  - Code
  - Méta
---

Parce que **oui**, il y a autre chose dans la vie que WordPress.

Le saviez-vous ? Il est possible d'avoir un blog minimaliste (donc pas WordPress) sans payer aucun hébergement, sans pub, ni besoin d'installer des choses sur son ordinateur. Pour le savoir, sautez directement à « **Jekyll Now** » dans ce post ou [cliquez ici](http://www.jekyllnow.com) si vous êtes pressé.

**Update 18/04.** L'organisation Seed Development propose un éditeur de pages GitHub : [Prose.IO](http://prose.io/#about).

## Pourquoi WordPress m'a gonflé

1. J'en avais marre d'avoir des pages qui chargeaient lentement.
1. J'avais tout le temps des mises à jour de sécurité à faire.
1. J'avais énormément de spam dans les commentaires, ou alors il fallait que j'installe le plug-in Akismet.

## Octopress 2.0

Autant commencer par le moteur qui propulse ce blog. J'écris des posts sous la forme suivante, en [Markdown](https://fr.wikipedia.org/wiki/Markdown) :

    ---
    title: Générateurs de pages statiques
    authors:
      - Jill-Jênn Vie
    layout: post
    published: true
    permalink: /2016/02/26/generateurs-de-pages-statiques/
    categories:
      - Code
      - Méta
    ---

    Parce que **oui**, il y a autre chose dans la vie que WordPress.

    ## Pourquoi WordPress m'a gonflé

    1. J'en avais marre d'avoir des pages qui chargeaient lentement.
    1. J'avais tout le temps des mises à jour de sécurité à faire.
    1. J'avais énormément de spam dans les commentaires, ou alors il fallait que j'installe le plug-in Akismet.

    ## Octopress 2.0

    Autant commencer par le moteur qui propulse ce blog. J'écris des posts sous la forme suivante :

Et en tapant `rake generate`, tout le HTML est généré à partir de mes posts écrits en Markdown, même les regroupements de posts par catégorie. Je peux donc envoyer tout mon blog sur un serveur par FTP ou SSH.

L'avantage : c'est plus clean, je n'ai pas besoin d'écrire du PHP, et les pages s'affichent rapidement. Quelque chose que j'aime beaucoup avec Octopress, c'est son plug-in de footnotes[^1].

 [^1]: Reconnaissez que c'est mignon.

Le code ayant servi à obtenir ce résultat :

    Quelque chose que j'aime beaucoup avec Octopress, c'est son plug-in de footnotes[^1].

     [^1]: Reconnaissez que c'est mignon.    

## Jekyll

Octopress s'appuie sur [Jekyll](http://jekyllrb.com), un générateur de pages statiques écrit en Ruby.

Les gens derrière cet outil bossent pour la plupart à [GitHub](https://github.com), la plateforme *closed source* de projets *open source*.

### Jekyll Now

Un fan de Jekyll a rédigé un tutorial pour que quelqu'un de non technique puisse tester le système de blogs Jekyll. Je vous invite à y jeter un œil : [Jekyll Now](http://www.jekyllnow.com).

### Poole

En fait, ce qui est fantastique, c'est que la communauté derrière Jekyll est si grande qu'il y a plein de choses qui se sont construites par dessus.

Mark Otto ([@mdo](https://twitter.com/mdo)), le créateur de Bootstrap, a rassemblé une panoplie de fichiers CSS et de templates pour démarrer un projet Jekyll. Ça s'appelle [Poole](http://getpoole.com).

Deux exemples de blogs créés à partir de Poole :

- [Club-Méta](http://club-meta.fr), utilisant le thème Hyde ;
- [Digérateur](http://digerateur.xyz), utilisant le thème Lanyon.

### Octopress 3.0

L'auteur d'Octopress a voulu à nouveau réécrire une grosse partie de son code, mais la nouvelle version est supposée sortir bientôt… depuis 1 an, en fait.

En tout cas, sa version bêta a un thème sympa que j'ai utilisé pour un blog de voyage :

- [fly.jiji.cat](http://fly.jiji.cat)

## Pelican

[Pelican](http://getpelican.com), qui se veut être une[^2] anagramme de calepin, est un générateur de pages statiques écrit en Python.

Je me disais que Pelican serait mieux que Jekyll car plus léger et en Python. Mais ce que j'ai vu dans certains templates et dans le fonctionnement m'a semblé un peu sale (plein de variables globales, peu d'organisation).

**Fun fact:** l'auteur de Pelican utilise Jekyll pour [son propre blog](https://blog.notmyidea.org) xD

## Pandoc

[pandoc](http://pandoc.org) est un couteau suisse développé en Haskell par un prof de philosophie de l'université de Berkeley (oui oui) qui convertit tout vers tout, en particulier Markdown vers HTML, LaTeX, slides Beamer ou reveal.js, et même en `.docx`.

Vous pouvez [essayer pandoc en ligne](http://pandoc.org/try/) ou via [ce repo GitHub](https://github.com/jilljenn/trypandoc). Ça me semble un peu overkill pour créer un blog (en plus, il faut appliquer pandoc à toutes les pages), mais pourquoi pas. En tout cas, j'écrirai sûrement ma thèse avec, en Markdown, comme ces gens fous :

- [Tom Pollard](https://github.com/tompollard/phd_thesis_markdown)
- [Marco Sciaini](http://spatialrecology.org/replacingtex/)
- [Christopher Grainger](http://blog.cigrainger.com/2014/07/pandoc-markdown.html)

## Sphinx

Là, on est encore dans le détournement : utiliser un outil de documentation ([Sphinx](http://www.sphinx-doc.org)) pour faire des pages statiques. C'est ce que je fais actuellement pour [jill-jenn.net](http://jill-jenn.net) et je suis plutôt satisfait, car ça m'a permis d'organiser tout mon contenu sous la forme d'un arbre, et j'ai un module de recherche en JavaScript intégré (en bas de la colonne de gauche).

Pour les commentaires, si on ne souhaite pas utiliser Disqus (car un peu intrusif), on peut utiliser [Isso](http://posativ.org/isso/) (même si seulement sous Python 2.7 et un peu embêtant à configurer).

## Lektor

J'allais oublier le plus récent et important. Un générateur de pages statiques :

- facile à installer ;
- sans besoin d'utiliser la ligne de commande ;
- modifiable soit à partir des fichiers, soit à partir d'un **panneau admin** (!) ; 
- et ne requérant pas de compte GitHub.

Ce qui est bien, c'est que je peux l'installer à quelqu'un et cette personne peut devenir autonome.

Ça a été développé par [Armin Ronacher](http://lucumr.pocoo.org), le jeune développeur archiprolifique à l'origine de Jinja, Flask, Sphinx, [etc.](http://lucumr.pocoo.org/projects/).

Il a d'ailleurs un post où il explique pourquoi il a créé un *n*-ième générateur de pages statiques :

<blockquote class="twitter-tweet" data-lang="fr"><p lang="en" dir="ltr">Does the world need more static file generators? Yes. Introducing Lektor: a Static File CMS for Python. <a href="https://t.co/RmfNb3bQfP">https://t.co/RmfNb3bQfP</a></p>&mdash; Armin Ronacher (@mitsuhiko) <a href="https://twitter.com/mitsuhiko/status/678963561285177344">21 décembre 2015</a></blockquote> <script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

## Moralité

Si vous êtes tech, installez [Jekyll](http://jekyllrb.com), éventuellement via le thème [Lanyon de Poole](http://lanyon.getpoole.com) et si vous êtes en train de coder un site pour votre grand-mère, installez-lui [Lektor](https://www.getlektor.com).

## Zut, j'ai pas fini

Peut-être qu'un jour, j'aurai l'occasion d'essayer :

- [org-mode](http://orgmode.org), le module pour Emacs ;
- [Hugo](https://gohugo.io), codé en Go ;
- tous les autres générateurs sur [staticsitegenerators.net](https://staticsitegenerators.net).

 [^2]: Anagramme est un mot féminin, sans accent circonflexe ni trait d'union.
