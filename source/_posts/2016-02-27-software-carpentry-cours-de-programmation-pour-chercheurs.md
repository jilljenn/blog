---
title: Software Carpentry, cours de programmation pour chercheurs
authors:
  - Jill-Jênn Vie
layout: post
published: true
permalink: /2016/02/27/software-carpentry-cours-de-programmation-pour-chercheurs/
categories:
  - Code
  - Méta
---

Je fais ma thèse à l'université Paris-Saclay. Parmi autres avantages, cela me permet d'être régulièrement spammé. En l'occurrence, j'ai pu découvrir l'existence du « ***Center for Data Science à Paris-Saclay*** : un projet pour encourager les collaborations et les synergies interdisciplinaires », organisant des événements tels que :

- une journée [Wikidata pour la science](http://www.meetup.com/fr-FR/SemanticCampParis/events/227054374/?a=socialmedia) ;
- un [Software Carpentry Workshop](http://www.datascience-paris-saclay.fr/fr/site/newsView/17) à l'[UNIC](https://www.unic.cnrs-gif.fr)[^1] Gif-sur-Yvette ;
- des compétitions data challenge (bientôt pour [Mangaki](http://mangaki.fr) ?).

 [^1]: Unité de neurosciences, information et complexité.

## Software Carpentry

C'est une organisation à but non lucratif qui vise à donner un bagage minimal de **cours de programmation pour les chercheurs** en science, ingénierie, médicine, etc. [Toutes leurs leçons](http://software-carpentry.org/lessons/) sont sur GitHub, en Creative Commons, ils ont [450 instructeurs à travers le monde](http://software-carpentry.org/team/), et je pense que je vais les rejoindre.

L'un des fondateurs est Greg Wilson, l'auteur de *Beautiful Code* et d'une [super vidéo sur le développement d'applications](http://vimeo.com/9270320). Je l'avais [rencontré en 2014](/2014/12/31/2014/) (cf. « Learning at Scale »), il m'a proposé d'écrire un chapitre de son livre donc j'ai codé [un convertisseur de slides de Markdown vers PostScript en moins de 500 lignes](https://github.com/aosabook/500lines/pull/63) (c'était le principe du livre), à partir de l'algorithme de Knuth et Plass : « [*Breaking Paragraphs into Lines*](http://www.cs.ust.hk/mjg_lib/bibs/DPSu/DPSu.Files/KnPl81.PDF) », 1981.

À l'époque, il m'avait mentionné qu'il écrivait des leçons de programmation en [Markdown](https://fr.wikipedia.org/wiki/Markdown) qu'il convertissait avec [pandoc](/2016/02/27/generateurs-de-pages-statiques/) avec d'autres instructeurs, et (si je me souviens bien), il avait plaisanté sur le fait que je pouvais également former des gens qui à leur tour formeraient d'autres personnes à l'algorithmique[^2].

 [^2]: Avant même de consulter cette footnote, vous avez compris qu'elle contiendrait le mot : « méta ».

Et là, en consultant la [liste des leçons qu'ils proposent](http://software-carpentry.org/lessons/), on voit de tout :

- [Comment fonctionne Git](http://swcarpentry.github.io/git-novice/) ou Mercurial
- [Programmer avec Python](http://swcarpentry.github.io/python-novice-inflammation/), R et MATLAB
- [Bases de données et SQL](http://swcarpentry.github.io/sql-novice-survey/)
- Et… la bonne blague : « [Instructor Training](http://swcarpentry.github.io/instructor-training/) », par Greg Wilson. Il est là, son cours méta :D

## Ateliers Python à l'ENS Cachan

L'année dernière, avec une bande de potes tirés des départements éco, méca, math, bio, socio et phy, on a <del>fait un barbecue</del> organisé une [initiation à la programmation en Python à l'ENS Cachan](http://tryalgo.org/atelier-python/). J'avais un financement de Google, avec leur programme *Google Student Ambassador* (principe : il suffisait de remplir un formulaire pour remporter un voyage de 3 jours tous frais payés à Dublin, plus des sous pour organiser des événements).

Au départ on était idéalistes, donc le principe était de trouver **toute l'algorithmique** enseignée dans chacun des départements :

- Pauline faisait de [l'alignement de séquences](https://fr.wikipedia.org/wiki/Plus_longue_sous-séquence_commune) de bases azotées en biologie.
- Fabrice faisait du [recuit simulé](https://fr.wikipedia.org/wiki/Recuit_simulé) en physique statistique ;
- Margot faisait des [colonies de fourmis](https://fr.wikipedia.org/wiki/Algorithme_de_colonies_de_fourmis) et des simulations de marché en éco-gestion ;
- Jordan faisait de l'optimisation d'assemblages par colonies de fourmis en génie mécanique ;

Mais finalement, on a simplement fait une introduction à Python, le samedi 16 mai 2015. Les gens étaient contents, voici [un compte rendu](http://tryalgo.org/2015/05/16/atelier-python-1/) :)

Mais ce genre d'initiative n'a d'intérêt que si c'est régulier, et que des gens sont prêts à devenir formateurs à leur tour… Tiens, c'est justement le principe de Software Carpentry.

## Club Algo de l'ENS Cachan

En parallèle, il se trouve qu'on est plusieurs à être férus de résolution de problèmes algorithmiques à l'ENS Cachan. Or, il y a [beaucoup de compétitions de programmation](http://tryalgo.org/events/). Genre, [vraiment beaucoup](http://jill-jenn.net/codeweek/4-competitions.html).

Donc, on s'est vus (presque) tous les jeudis. Il y avait deux groupes :

- les nouveaux, qui travaillaient sur [mes TP Caml](http://jill-jenn.net/tp) ou par exemple [ce TP de plus courts chemins dans les labyrinthes](http://tryalgo.org/tp4/) ;
- les avancés, qui résolvaient [des problèmes difficiles](http://tryalgo.org/problems/).

Préparer ces séances nous a permis avec Christoph Dürr d'avoir plein de matériau pour notre livre : « [**Programmation efficace : les 128 algorithmes qu'il faut avoir compris et codés en Python dans sa vie**](http://tryalgo.org) » qui sort le 1<sup>er</sup> mars 2016[^3].

 [^3]: HÉÉÉ, C'EST MARDI !!!

À présent qu'il y a moins de compétitions à l'horizon (si ce n'est le [Google Code Jam](https://code.google.com/codejam) qui commence le 8 mars), voici nos projets en chantier :

### 1. Devenir un vrai cours à l'ENS Cachan ?

Ce serait bien, car on ne maîtrise un algorithme qu'une fois qu'on l'a codé sans bug (il est super facile de rater un algorithme de [recherche dichotomique](https://fr.wikipedia.org/wiki/Dichotomie#Recherche_dichotomique) ou de [sac à dos](https://fr.wikipedia.org/wiki/Problème_du_sac_à_dos), par exemple).

### 2. Faire un site collaboratif pour tester ses implémentations d'algorithmes

Un peu comme [France-ioi](http://www.france-ioi.org), mais où les codeurs peuvent ajouter des jeux de tests, et où l'on peut consulter les implémentations des autres, et imprimer des notebooks PDF (c'est un détail, mais c'est utile lorsqu'on participe à certains concours).

Ce serait utile, car de plus en plus de professeurs enseignant l'informatique se demandent comment mettre en ligne un **correcteur automatique** des codes des élèves (aussi appelé **juge en ligne**). C'est compliqué car il faut permettre l'exécution de ces codes côté serveur, mais isoler l'exécution pour qu'un petit malin ne puisse pas casser le serveur à coups d'appels systèmes.

Il se trouve que Michel Blockelet a [déjà codé un juge en ligne](https://github.com/France-ioi/taskgrader) pour France-ioi, mais je pense qu'on peut encore en démocratiser l'utilisation.

Olivier Marty a commencé ce chantier, que nous appelons pour l'instant [Algopédia](https://github.com/jilljenn/algopedia).

### 3. Démystifier les algorithmes que l'on croise dans la vie de tous les jours

J'aimerais qu'on écrive des articles sur un code minimal qui résout un problème de la vie de tous les jours.

Tenez, par exemple, un problème banal comme [le rendu de monnaie](https://fr.wikipedia.org/wiki/Problème_du_rendu_de_monnaie) : « *Comment déterminer un nombre minimal de pièces réalisant un montant* ». On peut le creuser arbitrairement profond pour avoir plein de choses à dire :

- Si j'ai une quantité infinie de pièces d'un centime, je peux forcément rendre la monnaie. *(Non, sans déconner.)*
- Si j'ai un stock illimité d'euros et que je rends tant que c'est possible la pièce de plus grande valeur, je vais rendre la monnaie avec un nombre minimal de pièces. *(Ah bon ?)*
- Mais ça, ça marche avec les euros, mais pas avec un système monétaire quelconque. *(AH BON ? — Ben oui, regarde, essaie de rendre 6 avec un système monétaire ou tu n'as que des pièces de 4 3 1 ; tu vas rendre 4 + 1 + 1 alors qu'on peut rendre seulement 3 + 3.)*
- Et c'est beaucoup plus facile pour la machine de te dire si un système monétaire a des cas pénibles comme celui que je viens de citer, plutôt que de rendre la monnaie avec un nombre minimal de pièces. *(ATTENDS WUT)*

Ainsi, ces idées d'articles seraient :

- comment fonctionne un correcteur orthographique
- comment fonctionne la machine qui rend la monnaie
- comment fonctionne Google Maps (Dijkstra)
- comment fonctionne le pot de peinture dans Paint
- comment résoudre Sudoku (et là on explique que c'est comme le pot de peinture dans Paint et les gens seront @_@)
- comment tracer une forme sans lever le crayon (chemin eulérien)
- comment fonctionne [un optimiseur de billets d'avion](/2015/08/29/relaxations-pendant-les-vacances/) (Bellman-Ford)
- comment planifier une to-do list (graphe de dépendances, tri topologique)
- comment devrait fonctionner Meetic ou Admission Post-Bac (mariages stables, [prix Nobel d'Économie pour Shapley](http://www.lemonde.fr/economie/article/2012/10/15/nobel-les-americains-alvin-roth-et-lloyd-shapley-recompenses-pour-leurs-travaux-sur-les-marches_1775714_3234.html))
- comment fonctionne la recherche dans un texte

Clémence Réda a commencé à rédiger deux de ces articles. Coming soon!

En anglais, on peut citer les incroyables blogs :

- [What's new](https://terrytao.wordpress.com) du award-winning [Terence Tao](https://fr.wikipedia.org/wiki/Terence_Tao) ;
- [Math ∩ Programming](http://jeremykun.com) de Jeremy Kun, plus orienté programmation et mathématiques (oui, je sais, comme son nom l'indique).

## Software Carpentry à l'ENS Cachan ?

Bref. Mettez tout ça ensemble, et il y aura bientôt un workshop Software Carpentry à l'ENS Cachan :) Si vous êtes volontaires pour aider, [contactez-moi](mailto:vie@jill-jenn.net) !
